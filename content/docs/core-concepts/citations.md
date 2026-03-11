# Citations

In Genezio, **citations** represent the external webpages that an AI system references when generating an answer. In many AI interfaces these are also referred to as **sources**.

When AI assistants such as ChatGPT, Claude, Gemini, Perplexity, or Google AI Overview produce responses, they often rely on information retrieved from the web. Some systems explicitly show these references as links or numbered sources. Genezio captures and analyzes these references as **citations**.

Citations help explain:

* where the information in the answer came from
* which websites influence AI-generated responses
* why certain brands appear in answers

---

## What a Citation Represents

A citation corresponds to a **specific webpage or document** that influenced an AI-generated answer.

Examples of common citation types include:

* a product or service page
* a comparison article
* a review site
* a documentation page
* a regulatory or research source

Each referenced URL becomes a **citation** recorded by Genezio.

---

## Citations vs Sources

Different AI systems use different terminology. Some interfaces display links as **citations**, while others label them as **sources**.

In Genezio, both terms refer to the same concept: the webpages that contributed information used by the AI system when generating its answer.

---

## Domain Grouping

A single website may appear in many conversations across different pages. To simplify analysis, Genezio can **group citations by domain**.

For example, instead of analyzing dozens of individual URLs from the same website, Genezio can aggregate them under a single domain such as:

```
example.com
```

Domain grouping helps users quickly identify:

* which websites influence AI answers the most
* which publications dominate a topic
* which domains frequently mention competitors

This makes it easier to analyze the overall **influence of a website**, rather than focusing only on individual pages.

---

## Citation Attributes

Each citation in Genezio includes several attributes that help analyze its role in AI responses.

### URL

The exact webpage referenced by the AI system.

---

### Occurrences

The number of conversations in which the citation appears.

Higher occurrence counts often indicate that a source strongly influences AI answers for that topic.

---

### Sentiment

Genezio analyzes how the brand is described in the context of the citation.

Possible classifications include:

* Positive
* Neutral
* Negative

This helps identify whether sources portray a brand favorably or critically.

---

## Automatic Citation Classification

Genezio automatically **classifies citations** to help users understand the type of source influencing AI responses.

These classifications appear directly in the citation interface.

### Source Ownership

Genezio determines whether a citation belongs to the analyzed brand, a competitor, or a neutral third party.

Examples include:

* First Party
* Competitor Owned
* Third-Party Editorial

---

### Source Category

Genezio identifies the type of content where the citation appears.

Examples include:

* Blog / Article
* Review (Editorial)
* Review (User-Generated)
* Comparison / Vs Page
* Listicle / Best-Of
* News Article
* Press Release
* Documentation / Knowledge Base
* Case Study
* Research Paper / Report

---

### Website Type

The broader category of the website hosting the content.

Examples include:

* Industry / Trade Publication
* Government / Regulatory
* Academic / Research
* Aggregator / Marketplace
* Social / UGC Platform
* Other

---

## Auto-Clarification of Citations

Genezio automatically **enriches and clarifies citations** by analyzing each source and assigning these classifications.

This process helps users quickly understand:

* whether a citation belongs to a competitor
* whether the source is editorial, a review, or a product page
* whether the source is first-party or third-party

Instead of manually inspecting every link, users can immediately see the role and type of each source directly in the citation list.

---

## Citations in the Conversation View

Citations can be inspected in the **conversation detail view**.

In this view, Genezio displays:

* the AI response
* the citations (sources) referenced by the AI system
* the associated query fanouts
* detected brand mentions

This transparency allows users to see exactly **which sources contributed to a specific AI answer**.

---

## Why Citation Analysis Matters

Citation analysis helps organizations understand the **information landscape influencing AI systems**.

By identifying which sources appear most frequently, teams can:

* understand which websites shape AI responses
* identify influential publications in their category
* detect sources mentioning competitors
* discover opportunities to improve visibility

---

## Next Steps

To understand how citations interact with other extracted signals, see:

* [Core Concepts -> Statements](./statements.html)
* [Insights -> Visibility Score](../insights/ai-visibility-score.html)
* [Insights -> Share of Voice](../insights/share-of-voice.html)

These pages explain how Genezio converts AI responses into measurable visibility insights.
