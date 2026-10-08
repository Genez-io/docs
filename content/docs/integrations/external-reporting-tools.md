# External Reporting Tools

Most teams want Genezio numbers alongside everything else they report —
in Looker Studio, a BI tool, a warehouse or a client dashboard.

---

## The route

The [API](../api/index.html) is how Genezio data reaches another tool. It
serves the same numbers the dashboard shows: visibility and recommendation,
visibility by topic, share against competitors, citations, conversations,
sentiment and perceptions, and the Business Scorecard.

A typed client can be generated from the OpenAPI document rather than written
by hand — see the [API overview](../api/index.html).

---

## A workable pattern

1. Create an API key, scoped to the brands that report needs. See
   [Authentication](../api/authentication.html).
2. Pull on a schedule that matches how often you run conversations. Pulling
   hourly when you run weekly adds noise, not freshness.
3. Store the readings with their dates, so you can show direction rather than
   a single figure.
4. Stay inside [the rate limit](../api/rate-limits.html) — 200 requests a
   minute per key — and give each system its own key.

---

## What to put on a shared dashboard

Direction, not a single number. A visibility figure with no trend and no
competitor beside it invites a question nobody can answer.

The three that travel well: your visibility over time, your position against
named competitors on the same questions, and progress on whichever
[Business Scorecard](../scorecard/index.html) goals the team agreed.

---

## What not to build

Avoid rebuilding the conversation reader elsewhere. The value of a Genezio
number is that you can open the answers underneath it, and an export strips
that. Report the numbers outside; investigate inside.
