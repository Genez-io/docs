# CDN Log Integration

**CDN log analysis** turns your own server-side access logs into a picture of how answer engines actually use your website — which pages they fetch, when they fetch them, and whether that lines up with the pages they end up citing.

It complements Genezio's citation data with first-party evidence straight from your own infrastructure. Log ingestion is arranged **on request, per customer** — see [Requesting Log Ingestion](#requesting-log-ingestion) below.

---

## Why It Matters

Citation tracking tells you which of your pages show up in AI answers. Your logs tell you the other half of the story: what answer engines are doing on your site in the first place.

There are two distinct behaviours in those logs, and separating them is the whole point.

### 1. Training crawls

Answer engines crawl the web to build and refresh the models behind their answers. Your logs show **which of your pages they visit for training purposes** — which parts of your site have been absorbed into what the model knows, and which have been passed over.

### 2. Real-time answer enrichment

This is the more valuable signal. Answer engines also fetch pages **in real time, in the middle of answering a specific question**, to enrich that answer with current information.

When you see a page accessed this way, you're watching your content get pulled into a live answer as it's being written. That tells you which pages are actively load-bearing for AI answers right now — a fundamentally different and more actionable thing than "this page was crawled at some point."

### Questions this answers

* Are answer engines crawling my most important content, or ignoring it?
* Which pages get fetched in real time to support live answers?
* Which high-value pages do AI bots never visit?
* Which pages get crawled often but are never cited?

Because it draws on your own server logs, this is direct, first-party evidence — not an estimate.

---

## Pairing With GA4

Log data is most useful when read **alongside your Google Analytics (GA4) data**.

Your CDN logs show what the answer engines did — the crawls and the real-time fetches. GA4 shows what humans did. Corroborating the two gives you a much fuller understanding of how answer engines consume the content you publish, and what happens to the people who arrive as a result of it.

---

## What Gets Ingested

Genezio ingests your **CDN or web server access logs** — the standard logs your CDN or origin already records for every request:

* the URLs and paths that were requested
* the user agents identifying who made each request, including AI crawlers
* the timing of each request, which is what makes real-time answer enrichment visible

These are the same logs your infrastructure team can typically export from your CDN or web server. No special instrumentation is required.

---

## What Genezio Analyzes

Raw logs are long lists of individual requests, which tell you very little on their own. Genezio does the analysis and reports back on three things.

### Clustering by keyword

Genezio **clusters** your log entries by keyword, grouping requested paths into themes — so activity is reported at the level of topics rather than single URLs. The same logs can be clustered more than one way when a different perspective is useful.

### Crawler breakdown

Genezio produces a **crawler breakdown** identifying which bots and crawlers are hitting your site, with particular emphasis on **AI crawlers** — the crawlers answer engines use to fetch content.

This separates answer-engine traffic from search engines, scrapers, and ordinary visitors.

### AI-crawler traffic vs. citations

The most valuable analysis connects the two halves of the story: **AI-crawler traffic against your citations**, checking whether the pages answer engines fetch line up with the pages that actually get cited in AI answers.

This is where the gaps surface — important pages answer engines ignore, or pages they fetch heavily but never cite.

---

## Requesting Log Ingestion

CDN log ingestion is **not self-serve**. It is arranged on demand for each customer.

1. **Contact Genezio** and tell us you want your CDN or server logs ingested.
2. Genezio works with you and your infrastructure team on how the logs are delivered.
3. Genezio analyzes the data and provides you with **custom reports** built from your CDN and GA4 data — showing what answer engines crawl, what they fetch in real time, and how that compares with the pages they cite.

---

## Related Pages

* [Citations](../core-concepts/citations.html)
* [Insights -> Actionable Insights](../insights/actionable-insights.html)
