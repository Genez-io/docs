# Statements

In Genezio, a **statement** is an individual claim extracted from an AI-generated answer.

When an AI system responds to a question, the response usually contains several claims about products, brands, or categories. Genezio breaks these responses down into smaller units called **statements** so they can be analyzed in a structured way.

Statements help answer questions such as:

* What exactly did the AI say about a brand?
* Was the statement positive, neutral, or negative?
* Which source supports the claim?
* Which competitors are mentioned in the same context?

By converting AI responses into statements, Genezio makes it possible to analyze AI-generated content at a much more granular level.

---

## Why Statements Are Important

AI responses are often long paragraphs that combine multiple ideas. Without breaking them apart, it is difficult to analyze how brands are represented.

For example, an AI assistant might produce an answer like:

> Popular CRM tools for startups include HubSpot, Pipedrive, and Zoho CRM. HubSpot is known for its strong marketing automation features, while Pipedrive focuses on simple sales pipeline management.

This response actually contains several distinct claims. Genezio extracts them as separate statements such as:

* HubSpot is a CRM tool used by startups
* Pipedrive is a CRM tool used by startups
* Zoho CRM is a CRM tool used by startups
* HubSpot is known for marketing automation
* Pipedrive focuses on pipeline management

Each of these becomes an individual **statement** that can be analyzed independently.

---

## Statement Attributes

Each statement extracted by Genezio contains several pieces of structured information.

### Text

The actual claim made in the AI response.

Example:

```
HubSpot is known for strong marketing automation features.
```

---

### Brand References

The brands mentioned in the statement.

A single statement may reference one or multiple brands.

Example:

```
HubSpot and Salesforce are widely used CRM platforms.
```

---

### Sentiment

Genezio evaluates whether the statement describes the brand positively, negatively, or neutrally.

Possible values include:

* Positive
* Neutral
* Negative

This allows users to understand not only how often their brand appears, but also **how it is described**.

---

### Supporting Citations

Statements are often linked to one or more **citations (sources)** that the AI system used when generating the claim.

This makes it possible to trace a statement back to the webpage that influenced it.

---

## Statements Across Conversations

Statements are extracted from every conversation that Genezio runs with AI systems.

By aggregating statements across many conversations, Genezio can identify patterns such as:

* common claims made about a brand
* recurring strengths and weaknesses
* frequently mentioned competitors
* differences in how AI systems describe the same brand

This helps organizations understand the **narrative that AI systems associate with their brand**.

---

## Statements in the Interface

In Genezio, statements can be explored in the **conversation detail view** and across aggregated analysis views.

Users can inspect:

* the original AI response
* the extracted statements
* the associated citations
* the brands mentioned in each claim

This transparency allows teams to see exactly how AI systems are describing products and companies.

---

## Statements and Insights

Statements form the foundation for several higher-level insights in Genezio.

They contribute to metrics such as:

* AI Recommendations
* AI Visibility
* Share of Voice
* Sentiment analysis
* Competitive positioning

By structuring AI responses into statements, Genezio transforms unstructured AI answers into data that can be measured and analyzed.

---

## Next Steps

To understand how statements and citations combine to measure brand presence, see:

* [Insights -> Visibility Score](../insights/ai-visibility-score.html)
* [Insights -> Share of Voice](../insights/share-of-voice.html)

These pages explain how Genezio turns conversation data into measurable AI visibility metrics.
