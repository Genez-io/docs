# Errors

Every error from the API comes back in one shape, whatever went wrong:

```json
{
  "error": {
    "code": "invalid_api_key",
    "message": "The API key is not valid.",
    "request_id": "01JD8Z…"
  }
}
```

---

## Read the code, not the message

`code` is stable. Compare it with a constant in your own code, and it will
keep meaning the same thing. A new case gets a new code rather than changing
an existing one.

`message` is written for a person reading a log. It can be reworded at any
time, so no program should branch on it.

`request_id` identifies that single request. Quote it when you contact
support and the exact call can be found.

---

## Common codes

| HTTP | Code | What happened |
|---|---|---|
| 401 | `invalid_api_key` | The key is missing, wrong, or withdrawn. |
| 403 | `forbidden` | The key is valid but not allowed this brand or action. |
| 404 | `not_found` | No such record, or not one this key may see. |
| 422 | `validation_error` | Something in the request is wrong. |
| 429 | `rate_limited` | Over [the rate limit](rate-limits.html). |

---

## Validation errors

A `validation_error` carries a `details` list with one item per field, so you
can show a person exactly which value to correct instead of a general failure.

---

## A note on brands a key may not see

A key limited to some brands is answered `404` for a brand outside its list,
not `403`. The key learns nothing about what else the account holds.
