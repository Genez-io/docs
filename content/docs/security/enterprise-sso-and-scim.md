# Enterprise SSO and SCIM

**Enterprise SSO** lets your team sign in to Genezio through your own identity provider — Okta, Microsoft Entra ID, OneLogin, Ping, or any SAML 2.0 IdP. **SCIM provisioning** goes a step further and makes your IdP the source of truth for who has a Genezio account and what they can do.

Both are arranged **per customer, with the Genezio team** — they are not self-serve. This page covers what you need to do, what Genezio does, and the behaviour to expect once it's live.

---

## What You Get

**Single sign-on (SAML)** — your people sign in with your corporate credentials, under your own MFA and session policies. No separate Genezio password to manage.

**SCIM provisioning** — when someone joins the right group in your IdP, their Genezio account is created automatically. When they leave, their access is removed. No manual invitations, no orphaned accounts after offboarding. Roles are then set in Genezio by an account Owner — see [Roles](#roles-are-assigned-in-genezio-not-in-your-idp).

Most organizations want both. They solve different problems:

* **SSO** answers *"is this person who they say they are?"*
* **SCIM** answers *"should this person have an account, and what can they do with it?"*

---

## The One Thing to Know First

**SSO does not create accounts.** Signing in successfully proves identity — it does not grant access to your Genezio account. A first-time user who authenticates through your IdP but has no Genezio account and no pending invitation will be turned away with a message telling them they need an invitation.

So a user has to exist in Genezio first, created either by **SCIM** or by an **invitation from an account Owner**. If you roll out SSO without SCIM, plan on inviting every user by hand.

---

## How Setup Works

Ask your Genezio representative to start the process. On our side we:

* register your **email domains** and create the identity-provider connection for your organization
* send you the two values you need to set up the SAML application in your IdP — the **Identifier (Entity ID)** and the **Reply URL (Assertion Consumer Service URL)**
* **enable SCIM** on your account

Until SCIM is enabled, the **SCIM** entry stays hidden in your account settings.

Then, on your side:

1. **Configure SAML** in your IdP using those two values, and send us your IdP's SAML metadata XML.
2. **Test with one pilot user** who already has a Genezio account or a pending invitation.
3. **Connect SCIM** using a token you generate in Genezio, and provision that same pilot user.
4. **Check for email conflicts** before provisioning everyone — see [Troubleshooting](#troubleshooting).
5. **Provision your team**, then have an Owner set anyone who needs more than the default Member role.
6. **Test offboarding** — deactivate a test user and confirm their access is gone.

---

## Connecting Your Identity Provider

Setting up SSO is a two-way exchange. Genezio sends you two values; you send us one file.

**What Genezio gives you.** Create a standard SAML 2.0 application in your IdP and enter these:

| Value | Also called |
|---|---|
| **Identifier (Entity ID)** | Audience URI, SP Entity ID |
| **Reply URL (Assertion Consumer Service URL)** | ACS URL, Single sign-on URL |

Both are specific to your organization's connection, so use the ones we send you rather than copying them from another tenant.

**What you send back.** Export your IdP's **SAML metadata XML** and send it to your Genezio representative. We use it to complete the federation on our side — nothing happens until we have it, so this is usually the step that holds up a rollout. If your IdP can only give you a metadata URL, tell us and we'll work from that.

**Send email as an attribute.** Email is required — as the NameID in `emailAddress` format, an explicit email attribute, or both. Display name is optional but recommended; without it, Genezio uses the part of the email before the `@`.

**The email must match exactly.** Genezio compares the address your IdP returns against the address the user typed on the sign-in page. Case doesn't matter, but anything else does — an alias, a UPN that differs from the mail attribute, or a legacy domain will fail the sign-in. Make sure the attribute you send is the address your users think of as their work email.

**Give us every domain.** SSO is keyed to email domains, so include secondary and acquired-company domains. Each domain maps to one identity provider; a single domain can't be split across two.

**Sign-in starts at Genezio.** Users go to the Genezio sign-in page and enter their work email, and Genezio routes them to your IdP from there. IdP-initiated launches aren't supported — if you want a tile in your app catalog, make it a bookmark pointing at the Genezio sign-in page.

---

## Turning On Automatic Provisioning

You'll need the **Owner** role and SCIM enabled on your account.

1. Go to **Settings -> SCIM**.
2. Create a token, giving it a name you'll recognise later (e.g. "Okta production") and an optional expiry.
3. **Copy the token straight away** — it's shown once and can't be retrieved afterwards. Only the first few characters stay visible, so you can tell tokens apart.
4. Paste the token and the base URL shown alongside it into your IdP's provisioning settings, using bearer-token authentication.

Tokens can be **rotated** (new secret, same name and expiry, old one dead immediately), **disabled and re-enabled**, or **deleted permanently**. Each token works for exactly one Genezio account and can only act on the users it provisioned — treat it as a high-value credential and keep it in your IdP's secret store.

> Disabling or deleting a token stops provisioning, but it doesn't remove anyone's access. To offboard people, deprovision them through your IdP first, then remove the connection.

### Roles Are Assigned in Genezio, Not in Your IdP

**SCIM groups are not supported.** Genezio's SCIM implementation covers the user lifecycle only — creating, updating, deactivating, and removing people. It does not expose a Group resource, so your IdP cannot push groups or assign roles.

**Every user SCIM creates arrives as a Member.** To give someone a different role, an account Owner changes it in the Genezio dashboard under **Users**. Role changes are an in-app action; there's no way to drive them from your IdP.

Genezio has three account roles:

| Role | What they can do |
|---|---|
| **Owner** | Full control — manage brands, invite and remove users, change roles, billing |
| **Member** | Collaborator with access to the data; can invite others, but can't create or delete brands |
| **Viewer** | Read-only — can see reports and data, but can't change anything |

In practice this means provisioning and permissions are separate jobs: your IdP decides *who* has an account, and an Owner decides *what* they can do. For most teams that's a one-time step per person, since Member is the right role for the majority of users.

### Connector Settings

Genezio implements SCIM 2.0, so any standards-compliant connector works. A few things to configure:

* **Leave group and role provisioning switched off.** Genezio advertises only the User resource, so there's nothing for a group push to talk to. Watch out for Microsoft Entra ID, which enables group mapping by default — turn it off.
* **Turn off bulk operations and sorting** — provisioning happens one user at a time.
* **Keep filters simple** — only single-attribute equality filters are supported.
* **Don't sync passwords** — SCIM users authenticate through your IdP, not with a Genezio password.

Entra's provisioning validator will flag bulk, sort, and etag as unsupported. That's expected and doesn't block anything.

---

## What Happens When Someone Leaves

Deactivating a user in your IdP (or deleting them) removes their Genezio account membership and all of their permissions immediately. If Genezio was their only account, their active session is revoked too. Someone who also belongs to a different Genezio account keeps their access there.

One limitation to be aware of: **SSO doesn't switch off password sign-in**. Enabling SSO gives your users an additional way in — it doesn't remove a password they already set, and it doesn't stop them using it. Genezio has no setting to enforce SSO-only sign-in for a domain today. If that's a hard requirement for your security review, raise it with us before you plan the rollout; it would need work on our side rather than a configuration change.

---

## Troubleshooting

| What you see | What it means | What to do |
|---|---|---|
| "SSO is not configured for this email domain" | The domain isn't registered or has been disabled | Ask Genezio to register or re-enable it |
| "You need an invitation before signing in with SSO" | Sign-in worked, but there's no Genezio account for this person | Provision them via SCIM, or have an Owner invite them |
| "Does not match the email you entered" | Your IdP returned a different address than the user typed | Align your IdP's email attribute with the user's work email |
| "Your SSO session expired" | A stale sign-in, usually from several open login tabs | Close the other tabs and try again |
| SCIM: invalid or expired token | The token is wrong, disabled, or past its expiry | Rotate the token and update your IdP |
| SCIM: SCIM is not enabled for this account | The token is valid but the feature isn't switched on | Contact Genezio |
| SCIM: user already exists in another account | This email belongs to a user in a different Genezio account | Contact Genezio support to detach it |
| Your IdP reports failures pushing groups | Genezio has no Group resource — group provisioning isn't supported | Switch group provisioning off in your connector; set roles in Genezio under **Users** |
| SCIM entry missing from Settings | SCIM isn't enabled yet, or you're not an Owner | Contact Genezio, and check your role |

**Watch out for the email conflict.** People who signed up for Genezio on their own before your enterprise rollout will already own an account under their work email, and provisioning them will fail. Audit for these and clear them with Genezio support before you provision everyone.

---

## What to Send Genezio

To get set up quickly, have these ready:

- [ ] Every email domain your users sign in with
- [ ] Which identity provider you use
- [ ] Your IdP's **SAML metadata XML** (this is the one we can't proceed without)
- [ ] The attribute you'll send as email, confirmed to match users' work emails
- [ ] The Genezio account SCIM should manage, and its Owner's email

---

## Related Pages

* [Getting Started -> Sign-in and SSO Options](../getting-started/sign-in-and-sso-options.html)
* [Core Concepts -> Users](../core-concepts/users.html)
