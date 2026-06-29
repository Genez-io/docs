# CDN Log Integration

**CDN log analysis** lets you upload your own server-side access logs to Genezio and see exactly which pages AI crawlers are fetching from your site — then compare that against the pages AI engines actually cite in their answers.

This turns your raw CDN and web server logs into a clear picture of how AI answer engines discover, crawl, and use your content. It complements Genezio's citation data with first-party evidence straight from your own infrastructure.

---

## Why It Matters

Citation tracking tells you which of your pages show up in AI answers. CDN log analysis tells you the other half of the story: what AI crawlers are actually fetching in the first place.

Together, they help you answer questions like:

- Are AI engines crawling my most important content, or ignoring it?
- Which high-value pages do AI bots never visit?
- Which pages get crawled often but are never cited?
- Is my crawl budget going to the content I care about?

Because it draws on your own server logs, this is direct, first-party evidence — not an estimate. It gives you a ground-truth view to pair with the citation insights elsewhere in Genezio.

---

## What You Can Upload

You upload your **CDN or web server access logs** — the standard logs your CDN or origin server already records for every request:

- The URLs and paths visitors and bots requested
- The user agents identifying who made each request (including AI crawlers)

These are the same logs your infrastructure team can typically export from your CDN or web server. No special instrumentation is required.

---

## How It Works

### Clustering by keyword

Raw logs are long lists of individual URLs, which are hard to read on their own. Genezio **clusters** your log entries by keyword, grouping requested paths into themes so you can see traffic at the level of topics rather than single URLs.

You can run **multiple clusterings** on the same logs — cluster them one way, save it, then cluster them another way for a different perspective. Saved clusterings stay available so you can revisit or compare them later.

### Crawler breakdown

Genezio produces a **crawler breakdown** that identifies which bots and crawlers are hitting your site, with particular emphasis on **AI crawlers** — the crawlers AI answer engines use to fetch and index content for their responses.

This shows you who is actually visiting, separating AI engine crawlers from search engines, scrapers, and ordinary traffic.

### AI-crawler traffic vs. citations

The most valuable view connects the two halves of the story: Genezio analyzes **AI-crawler traffic against your citations**, checking whether the pages AI crawlers are fetching line up with the pages that actually get cited in AI answers.

This is where gaps surface — important pages AI bots ignore, or pages they crawl heavily but never cite — so you know where to focus.

---

## Reading the Results

When reviewing your CDN log analysis, look for:

- **Coverage gaps** — high-value pages that AI crawlers rarely or never fetch.
- **Crawled-but-not-cited pages** — content AI bots fetch but that never appears in answers, which may signal a content or relevance issue.
- **Crawler mix** — how much of your bot traffic comes from AI engines versus other crawlers.
- **Theme-level patterns** — using your keyword clusters to see which content areas get the most AI-crawler attention.

---

## How to Get Started

1. Go to **Settings -> Integrations** and open CDN Log Integration.
2. Upload your CDN or web server access logs.
3. Run a clustering to group the requested paths by keyword, and save it. Run additional clusterings if you want a different view of the same logs.
4. Review the crawler breakdown to see which AI crawlers are visiting, then open the AI-crawler-traffic-vs-citations analysis to spot coverage and citation gaps.

You can also explore all of this through the [Geo Assistant](../geo-assistant/geo-assistant.html) — most CDN log operations are exposed as assistant tools, so you can simply ask about your CDN log clusters, crawler breakdown, and how crawl activity compares to your citations.

---

## Related Pages

- [Citations](../core-concepts/citations.html)
- [Geo Assistant](../geo-assistant/geo-assistant.html)
