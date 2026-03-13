# Statements

In Genezio, a **statement** is an individual claim extracted from an AI-generated answer.

When an AI system responds to a question, the response usually contains several claims about products, brands, or categories. Genezio breaks these responses down into smaller units called **statements** so each claim can be evaluated for accuracy.

Statements help answer questions such as:

* What exactly did the AI say about a brand?
* Is the claim correct or incorrect?
* Which source supports the claim?
* Which competitors are mentioned in the same context?

By converting AI responses into statements, Genezio makes it possible to verify whether AI engines are telling the truth about your brand.

---

## Why Statements Are Important

AI responses are often long paragraphs that combine multiple ideas. Without breaking them apart, it is difficult to tell which claims are accurate and which are not.

For example, an AI assistant might produce an answer like:

> Popular CRM tools for startups include HubSpot, Pipedrive, and Zoho CRM. HubSpot is known for its strong marketing automation features, while Pipedrive focuses on simple sales pipeline management.

This response actually contains several distinct claims. Genezio extracts them as separate statements such as:

* HubSpot is a CRM tool used by startups
* Pipedrive is a CRM tool used by startups
* Zoho CRM is a CRM tool used by startups
* HubSpot is known for marketing automation
* Pipedrive focuses on pipeline management

Each of these becomes an individual **statement** that can be evaluated for accuracy against what your brand actually does.

---

## Statement Accuracy

The most important thing about a statement is whether it is **correct or incorrect**.

AI engines make claims about brands all the time — and those claims shape how buyers perceive you. Some claims are accurate. Others are outdated, misleading, or simply wrong.

Examples:

* *"Zara is a fast fashion brand"* → **Correct**
* *"Gucci is a fast fashion brand"* → **Incorrect**
* *"HubSpot offers a free CRM tier"* → **Correct**
* *"Pipedrive includes built-in marketing automation"* → **Incorrect**

When an AI engine makes an incorrect claim about your brand, it can mislead buyers and cost you recommendations. When it makes a correct claim, it reinforces your positioning.

### How Accuracy Is Determined

To evaluate whether a statement is correct or incorrect, Genezio relies on your **brand knowledge base** — the information you provide about your brand, products, and positioning.

This may include:

* product descriptions and capabilities
* pricing and plans
* target audience and use cases
* competitive differentiators
* any other brand guidelines

By comparing AI-generated claims against your brand knowledge, Genezio can flag statements that misrepresent your brand — giving you a clear view of where AI engines are getting it right and where they are getting it wrong.

---

## Other Statement Attributes

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

### Supporting Citations

Statements are often linked to one or more **citations (sources)** that the AI system used when generating the claim.

This makes it possible to trace a statement back to the webpage that influenced it — and understand why the AI made a particular claim.

---

## Statements Across Conversations

Statements are extracted from every conversation that Genezio runs with AI systems.

By aggregating statements across many conversations, Genezio can identify patterns such as:

* recurring claims made about a brand — correct or incorrect
* common inaccuracies that need to be addressed
* frequently mentioned competitors
* differences in how AI systems describe the same brand

This helps organizations understand the **narrative that AI systems associate with their brand** — and whether that narrative is accurate.

---

## Statements in the Interface

In Genezio, statements can be explored in the **conversation detail view** and across aggregated analysis views.

Users can inspect:

* the original AI response
* the extracted statements
* the accuracy of each claim
* the associated citations
* the brands mentioned in each claim

This transparency allows teams to see exactly what AI systems are saying about their brand — and whether it is true.

---

## Statements and Insights

Statements form the foundation for several higher-level insights in Genezio.

They contribute to:

* AI Recommendations — incorrect claims can reduce your recommendation rate
* AI Visibility — inaccurate descriptions affect how often AI engines surface your brand
* Share of Voice — the accuracy of claims shapes competitive positioning
* Competitive positioning — understanding which claims favor you vs. competitors

By structuring AI responses into statements and evaluating their accuracy, Genezio transforms unstructured AI answers into data that can be measured, verified, and acted on.

---

## Next Steps

To understand how statements and citations combine to measure brand presence, see:

* [Insights -> Visibility Score](../insights/ai-visibility-score.html)
* [Insights -> Share of Voice](../insights/share-of-voice.html)

These pages explain how Genezio turns conversation data into measurable AI visibility metrics.
