# API Documentation

The Genezio API gives your own systems the same data the dashboard shows: how
visible your brand is in AI answers, who is cited, what competitors are doing,
and the content you create from it.

Use it to put Genezio numbers on your own dashboard, to export results into a
warehouse, or to let another tool start work in Genezio without anybody
opening a browser.

---

## Where it lives

Every endpoint sits under:

```
https://app.genezio.ai/customer/v1
```

The machine-readable description of every endpoint is published at:

```
GET https://app.genezio.ai/customer/v1/openapi.json
```

That document is a standard OpenAPI file. Most HTTP clients and code
generators read it directly, so you can produce a typed client in your own
language instead of writing requests by hand. It is always current: it is
generated from the same routes that serve your requests.

---

## What you can reach

**Your brand and its setup** — brands, topics and the prompts under them,
personas, competitors, tracked URLs, knowledge bases, brand settings, topic
tags, and brand groups.

**What the answer engines said** — conversations, citations, web searches,
products that appeared in shopping answers, sentiment and perceptions, and the
fact check of a brand.

**Your numbers** — visibility and recommendation, visibility by topic,
visibility inside a single prompt, and the SWOT of your brand and of each
competitor.

**Content** — articles, briefs, templates and content analyses.

**The Business Scorecard** — read the goals on your board and change them.

**Connected data** — what Google Search Console reports for your brand, and
the e-commerce audit.

Only the answer engines your plan includes are returned, so what you read
matches what you are paying for.

---

## Before you start

1. An **owner** of the account creates an API key under
   **Settings → API Keys**. See [Authentication](authentication.html).
2. Decide which brands the key may read. A key can be limited to some brands
   of the account rather than all of them.
3. Keep within [the rate limit](rate-limits.html) of 200 requests a minute.
4. Read [Errors](errors.html) so your code reacts to a stable code rather than
   to a sentence that may be reworded.

---

## A first request

```bash
curl https://app.genezio.ai/customer/v1/brands \
  -H "X-API-Key: gnz-your-key-here"
```

The answer lists the brands the key is allowed to see. From a brand id you can
reach everything else: its topics, its conversations, its citations and its
numbers.
