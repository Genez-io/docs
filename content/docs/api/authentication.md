# Authentication

Every request to the Genezio API carries an API key. A key belongs to your
account, not to a person, so it keeps working when somebody leaves the team.

---

## Creating a key

Only an **owner** of the account can create one.

1. Open **Settings → API Keys**.
2. Create a key and give it a name you will recognise later, such as
   `warehouse-export` or `agency-dashboard`.
3. Choose which brands it may read.
4. Copy the key. It is shown once.

A key starts with `gnz-`, which makes it easy to recognise in a log or a
secrets store and to spot if it is ever pasted somewhere it should not be.

---

## Using a key

Send it in the `X-API-Key` header:

```bash
curl https://app.genezio.ai/customer/v1/brands \
  -H "X-API-Key: gnz-your-key-here"
```

A missing or wrong key is answered with `401` and the code `invalid_api_key`.

---

## Limiting a key to some brands

A key does not have to see the whole account. When you create it you can list
the brands it may read, and every request made with it is held to that list —
a brand outside it is answered as if it did not exist.

This matters most for agencies and for teams that run several brands in one
account:

- Give a client's own dashboard a key for that client's brand only.
- Give a reporting job a key for the brands in that report.
- Keep a key with the whole account for your internal tooling alone.

If a key leaks, what it exposes is bounded by the brands you chose.

---

## How many keys you get

The number of keys an account may hold comes from its plan. Plans start with
none, so if **Settings → API Keys** offers no button to create one, the API is
not part of your plan yet — talk to your account manager.

---

## Keeping keys safe

- Store a key as a secret in your deployment, never in a repository.
- Give each system its own key, so you can withdraw one without stopping the
  others.
- Withdraw a key the moment the system that used it is retired.

Every write made with a key is recorded in the audit log with the name of the
key and the address it came from, so you can always answer "what changed this,
and from where".
