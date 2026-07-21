# Enterprise SSO (SAML) & SCIM Provisioning — IT Administrator Guide

**Audience:** IT / identity administrators at a Genezio customer who need to connect Genezio to their identity provider (Okta, Microsoft Entra ID, OneLogin, Ping, or any SAML 2.0 IdP).

This guide covers what you configure on **your** side, what **Genezio** configures on ours, and the exact behavior you should expect. Both features are enabled per-customer by Genezio — read [Section 1](#1-before-you-start) before scheduling the work.

---

## 1. Before you start

Neither feature is self-serve. Contact your Genezio representative to begin; the following must happen on the Genezio side first.

| What Genezio must do | Needed for | Why you can't do it yourself |
|---|---|---|
| Register your **email domain(s)** and create a **Keycloak IdP alias** for your organization | SAML SSO | Domain→IdP mapping is platform-level configuration, with no customer-facing API or UI |
| Give you the **SP metadata URL** for your alias | SAML SSO | The URL contains your unique alias |
| Enable **SCIM provisioning** on your account | SCIM | Deliberate opt-in, enabled manually per vetted enterprise account |

Until SCIM has been enabled for your account, the **SCIM** entry is hidden in **Settings** and token creation returns `403`.

**Plan for both, in this order.** They solve different problems and SSO alone is not sufficient:

* **SAML SSO** answers *"is this person who they say they are?"* — authentication only.
* **SCIM** answers *"does this person get an account, and what can they do?"* — provisioning and deprovisioning.

Genezio does **not** do just-in-time (JIT) user creation from a SAML assertion. A user who authenticates successfully but has no Genezio user record and no pending invitation is **rejected** at sign-in. Users must exist first, created either by SCIM or by a manual invitation from an account Owner. If you deploy SSO without SCIM, plan to invite every user manually.

---

## 2. How Enterprise SSO works

Genezio does not act as a SAML Service Provider directly. A **Keycloak identity broker**, operated by Genezio, sits between your IdP and the application:

```
Your IdP  ──SAML 2.0──▶  Genezio Keycloak broker  ──OIDC──▶  Genezio API  ──▶  app session
```

**What this means for you:** you configure a standard SAML 2.0 application in your IdP whose ACS (Assertion Consumer Service) endpoint points at the **Keycloak broker**, not at `api.genezio.ai`. Everything downstream of the broker is Genezio's concern.

### 2.1 Sign-in flow (SP-initiated)

1. The user opens the Genezio sign-in page and enters their **work email**.
2. Genezio checks the email's domain against its registered SSO domains. If there is no match, SSO is not offered and the user sees a normal password form.
3. On a match, the user is redirected to Keycloak (OIDC authorization code flow with PKCE `S256`), which immediately brokers to your IdP using the alias configured for your domain.
4. Your IdP authenticates the user and posts a SAML assertion back to Keycloak.
5. Keycloak returns an authorization code to Genezio, which exchanges it and reads the user's `email` and `name`.
6. Genezio re-validates the email's domain, matches it against the address the user originally typed, and issues an application session.

**Only SP-initiated sign-in is supported.** The flow always begins at the Genezio sign-in page. An IdP-initiated tile in your app catalog should be configured as a bookmark/link to the Genezio sign-in URL rather than as a SAML IdP-initiated launch.

### 2.2 What you configure in your IdP

Create a SAML 2.0 application using the SP metadata URL Genezio gives you. **Genezio provides this URL on request** — it is unique to your organization's broker alias, so ask your Genezio representative for it during setup rather than constructing it yourself.

Most IdPs (Okta, Entra) can import the URL directly and fill in Entity ID, ACS URL, and expected bindings automatically. If your IdP requires manual entry, open the URL and take the values from the returned XML.

**Required attributes:**

| Attribute | Requirement | Notes |
|---|---|---|
| Email | **Required** | Must arrive as the `email` claim after Keycloak's mapping. Send it as the NameID (`emailAddress` format) and/or an explicit email attribute. |
| Display name | Recommended | Maps to `name` or `preferred_username`. Falls back to the local part of the email if absent. |

**Email must be exact.** Genezio matches the address the user types on the sign-in page against the address your IdP returns. Comparison is case-insensitive (both are lowercased), but a mismatch of any other kind — an alias, a UPN that differs from the mail attribute, a legacy domain — fails the sign-in with a "does not match" error. Make sure the attribute you send is the same address your users know as their work email and the same one used for their Genezio account.

**Domain scoping.** SSO is keyed to email domains. Provide Genezio with every domain your users sign in with, including secondary and acquired-company domains. Each domain maps to exactly one IdP; a single domain cannot be split across two identity providers.

### 2.3 Behavior you should know about

* **No JIT provisioning.** A first-time SSO user with no invitation is rejected (`sso_user_not_found`) with a message telling them they need an invitation. This is intentional — authentication does not imply authorization to an account.
* **SSO does not disable password login.** Linking SSO adds SAML as an auth provider on the user record; it does not remove an existing password. There is currently **no enforcement setting to require SSO** and block password sign-in for your domain. If your policy requires this, raise it with Genezio — it needs a platform-side change.
* **Profile names sync on every sign-in.** If your IdP's display name changes, Genezio updates it at the next login.
* **SSO endpoints are rate-limited.** Bulk automated sign-in testing may hit limits; coordinate load tests with Genezio.

---

## 3. SCIM 2.0 provisioning

Genezio implements a SCIM 2.0 service provider (RFC 7644) for user lifecycle management. Once connected, your IdP is the source of truth for who has access.

### 3.1 Connection details

| Setting | Value |
|---|---|
| **Base URL** | Displayed in the app when you create a token — copy it exactly. Genezio can also provide it on request. |
| **Authentication** | HTTP Header / OAuth Bearer Token |
| **Token** | Generated in Genezio (see below) |
| **Content type** | `application/scim+json` |

**Generating the token** (requires the account **Owner** role, and SCIM enabled on your account by Genezio):

1. Sign in to Genezio as an account Owner.
2. Go to **Settings -> SCIM**.
3. Create a token, giving it a recognizable name (e.g. "Okta production") and an optional expiry in days.
4. **Copy the token immediately.** Only a SHA-256 hash is stored; the plaintext is displayed exactly once and cannot be retrieved again. Only the first 8 characters remain visible in the UI for identification.
5. Paste the token and the base URL into your IdP's provisioning configuration.

Token management supports **rotate** (issues a new secret, invalidates the old one immediately, keeps the same name and expiry), **disable/enable** (reversible revocation), and **delete** (permanent).

> Deleting or disabling a token stops provisioning. It does **not** deprovision anyone — users it created keep their access. To remove access, deprovision through your IdP first, then delete the connection.

### 3.2 Supported operations

| Resource | Operations |
|---|---|
| `/ServiceProviderConfig`, `/ResourceTypes`, `/Schemas` | `GET` (discovery) |
| `/Users` | `GET` (list, paginated, filterable), `POST` |
| `/Users/{id}` | `GET`, `PUT`, `PATCH`, `DELETE` |
| `/Groups` | `GET` (list), `POST` (resolves an existing role group) |
| `/Groups/{id}` | `GET`, `PATCH` |

**Not supported** — configure your IdP accordingly:

* **Bulk operations** — provisioning is one request per user.
* **Sorting** and **ETags**.
* **Password sync / `changePassword`** — SCIM-created users get an unusable random password and authenticate through your IdP.
* **Complex filters.** Only single-attribute equality is supported: `userName eq "value"` and `externalId eq "value"` for Users, `displayName eq "value"` for Groups. `maxResults` is 200; default page size is 100.

### 3.3 Users

**Creating.** `userName` should be the user's work email. If `userName` is not email-shaped, Genezio falls back to the primary (or first) address in `emails`. A valid email is required.

* New users are created with the **Member** role unless a group assignment says otherwise (see [3.4](#34-groups-and-roles)).
* Creating a user with `active: false` records the mapping but grants **no** account access. Access is granted when they are later set active.
* `externalId` is supported and must be unique within a connection.
* The SCIM `id` returned for a user is their Genezio user id.

**Deactivating** (`active: false` via `PATCH` or `PUT`) removes the user's account membership and all associated permissions. Their session is force-revoked **only if Genezio was their last remaining account** — a user who also belongs to another Genezio account keeps their session there.

**Deleting** (`DELETE /Users/{id}`) removes membership and the SCIM mapping. Functionally equivalent to deactivation for access purposes.

**Conflict you will likely hit:** if an email already belongs to a user in a *different* Genezio account, provisioning is rejected with `409 uniqueness`. This most often affects people who signed up for Genezio independently before the enterprise rollout. Resolution requires Genezio support to detach the existing user — build a step for it into your rollout plan and audit for these before go-live.

### 3.4 Groups and roles

SCIM Groups map onto Genezio's fixed account roles. **Arbitrary groups from your IdP are not supported.**

| Group `displayName` | Genezio role |
|---|---|
| `owner` | Full control of the account: billing, members, brand creation |
| `member` | Standard operator: view and edit brand data |
| `viewer` | Read-only |

The name must match exactly (lowercased). Pushing a group named `Genezio-Admins` fails with `400`; create groups named exactly `owner`, `member`, and `viewer` in your IdP, or map your existing groups to those names in your provisioning configuration.

* Adding a member to a role group assigns that role (and moves them if they held another).
* Removing a member from a role group **removes their account access entirely** — it does not demote them to a lower role. If you intend a demotion, add them to the target role group; the role is updated in place.
* Role groups cannot be created or deleted. `DELETE` on one returns `400`.
* Group membership operations only affect users **this SCIM connection provisioned**. Users invited manually are ignored by group pushes.

### 3.5 IdP-specific notes

**Okta** — Use "SCIM 2.0 Test App (Header Auth)" or the SCIM section of your existing SAML app. Enable Create, Update, and Deactivate. Under Push Groups, push groups named `owner` / `member` / `viewer`.

**Microsoft Entra ID** — Use the non-gallery application's Provisioning tab with Tenant URL and Secret Token. The `members[value eq "..."]` remove syntax and Entra's string-valued `primary` flags are both handled. Entra's provisioning validator will report `bulk`, `sort`, and `etag` as unsupported; this is expected and does not block provisioning.

**OneLogin / Ping / others** — Any RFC 7644-compliant connector works given the constraints in [3.2](#32-supported-operations). Disable bulk and sorting; restrict filters to equality.

---

## 4. Recommended rollout

1. **Scoping call with Genezio.** Provide your email domains and IdP type. Genezio creates the Keycloak alias and enables SCIM on your account.
2. **Configure SAML** in your IdP from the SP metadata URL. Verify the email attribute.
3. **Test SSO with one pilot user** who already has a Genezio account or a pending invitation. Confirm sign-in end to end.
4. **Configure SCIM** with a token from the app. Provision the same pilot user and confirm they appear with the expected role.
5. **Audit for conflicts.** Identify anyone whose work email already exists in another Genezio account and resolve with Genezio support before bulk provisioning.
6. **Bulk provision** by assigning your role groups.
7. **Test deprovisioning** — deactivate a test user and confirm their access is gone.
8. **Document the invitation fallback** for your help desk: SSO alone cannot create a user, so a user missing from SCIM needs either a group assignment or an Owner-issued invitation.

---

## 5. Troubleshooting

| Symptom | Meaning | Fix |
|---|---|---|
| "SSO is not configured for this email domain" | The domain is not registered, or is registered but disabled | Ask Genezio to register/enable the domain |
| `sso_user_not_found` — "You need an invitation before signing in with SSO" | Authentication succeeded, but no Genezio user and no pending invite | Provision via SCIM, or have an Owner send an invitation |
| `sso_email_mismatch` — "does not match the email you entered" | The IdP returned a different address than the user typed | Align the IdP's email attribute with the user's known work email |
| "Your SSO session expired" | Stale broker session, usually from multiple open login tabs | Close other tabs, wait, retry |
| SCIM `401 Invalid or expired bearer token` | Token is wrong, disabled, or past its expiry | Rotate the token and update the IdP |
| SCIM `403 SCIM is not enabled for this account` | Valid token, but SCIM has not been enabled for the account | Contact Genezio |
| SCIM `409 already exists in another account` | The email belongs to a user in a different Genezio account | Genezio support must detach the existing user |
| SCIM `400 Only role groups (owner, member, viewer) are supported` | A group with a non-role name was pushed | Rename the group or remap it |
| SCIM `400 Unsupported filter` | The connector sent a filter more complex than `attr eq "value"` | Restrict the connector's filter configuration |
| SCIM entry not visible in **Settings** | SCIM has not been enabled for your account, or you are not an Owner | Contact Genezio; verify your role |

---

## 6. Security summary

For your security review:

* SCIM tokens are stored only as SHA-256 hashes; plaintext is shown once at creation and never retrievable.
* Tokens support optional expiry, immediate rotation, and reversible disabling.
* Every SCIM token is scoped to exactly **one** account. It cannot read or modify users outside it, and cannot act on users it did not provision.
* SCIM endpoints bypass the application's JWT/RBAC layer by design and authenticate solely via the bearer token — treat it as a high-value credential and store it in your IdP's secret store.
* The SAML flow uses OIDC authorization code with PKCE (`S256`) between Genezio and the broker, and validates the state parameter, token issuer, audience, and signature.
* Deactivation revokes account membership and permissions immediately; sessions are revoked when the user has no remaining Genezio account.
* SSO and account-management actions (logins, role changes, member removal) are written to Genezio's audit log.

---

## 7. Information to send Genezio

To speed up setup, gather:

- [ ] All email domains your users sign in with
- [ ] IdP product and version (Okta, Entra ID, OneLogin, …)
- [ ] Your IdP's SAML metadata (URL or XML)
- [ ] The attribute you will send as email, and confirmation it matches users' known work email
- [ ] The Genezio account that should receive SCIM (name and Owner email)
- [ ] Whether you require password sign-in to be blocked for your domain (currently needs a platform-side change)

---

## Related Pages

* [Getting Started -> Sign-in and SSO Options](../getting-started/sign-in-and-sso-options.html)
* [Core Concepts -> Users](../core-concepts/users.html)
