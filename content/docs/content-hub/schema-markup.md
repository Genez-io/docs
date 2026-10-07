# Schema Markup

Every article you generate comes with its **schema.org markup** — the
structured description that tells search engines and answer engines what the
page is, who wrote it, and what it is about.

---

## Why it matters

Prose tells a model what you say. Structured markup tells it what the page
*is*. Without it, an engine has to infer that a page is a product, a recipe,
a how-to or a review from the text alone, and it is often wrong.

Markup also decides whether a page is eligible for a rich result. A product
page without one cannot show a price or a rating, however good the page is.

---

## Using it

Open an article and you can read its markup, copy it, or edit it.

Paste it into your CMS as a JSON-LD block in the page's `<head>`. If your CMS
has a structured-data field, paste it there.

---

## Editing it

The generated markup is a starting point, and you will sometimes know things
Genezio does not. Edit it directly on the article.

The editor tells you when something is missing for a rich result — for a
product, for instance, Google also wants `offers`, `review` or
`aggregateRating` before the page is eligible. That saves finding out from a
search console weeks later.

---

## From another tool

An MCP client can read and edit an article's schema markup, so a correction
can be made in the middle of the conversation where you spotted the problem.
See [Genezio over MCP](../mcp/index.html).
