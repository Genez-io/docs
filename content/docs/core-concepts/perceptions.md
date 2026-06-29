# Perceptions

In Genezio, a **perception** is an individual claim extracted from an AI-generated answer about a brand, product, or category.

When an AI system responds to a question, the response usually contains several claims. Genezio breaks these responses down into smaller units called **perceptions** so each claim can be evaluated on its own — because together, these claims are how answer engines *perceive* and describe your brand to buyers.

> **Note:** Perceptions were previously called **Statements**. The concept is the same — the name now better reflects that these claims represent how AI systems perceive your brand.

Perceptions help answer questions such as:

* What exactly did the AI say about a brand?
* Is the claim correct or incorrect?
* Which source supports the claim?
* Which competitors are mentioned in the same context?

By converting AI responses into perceptions, Genezio makes it possible to verify whether answer engines are telling the truth about your brand — and to track the narrative they associate with it.

---

## Why Perceptions Are Important

AI responses are often long paragraphs that combine multiple ideas. Without breaking them apart, it is difficult to tell which claims are accurate and which are not.

For example, an AI assistant might produce an answer like:

> Popular CRM tools for startups include HubSpot, Pipedrive, and Zoho CRM. HubSpot is known for its strong marketing automation features, while Pipedrive focuses on simple sales pipeline management.

This response actually contains several distinct claims. Genezio extracts them as separate perceptions such as:

* HubSpot is a CRM tool used by startups
* Pipedrive is a CRM tool used by startups
* Zoho CRM is a CRM tool used by startups
* HubSpot is known for marketing automation
* Pipedrive focuses on pipeline management

Each of these becomes an individual **perception** that can be evaluated for accuracy against what your brand actually does.

---

## Perception Accuracy

The most important thing about a perception is whether it is **correct or incorrect**.

Answer engines make claims about brands all the time — and those claims shape how buyers perceive you. Some claims are accurate. Others are outdated, misleading, or simply wrong.

Examples:

* *"Zara is a fast fashion brand"* → **Correct**
* *"Gucci is a fast fashion brand"* → **Incorrect**
* *"HubSpot offers a free CRM tier"* → **Correct**
* *"Pipedrive includes built-in marketing automation"* → **Incorrect**

When an answer engine makes an incorrect claim about your brand, it can mislead buyers and cost you recommendations. When it makes a correct claim, it reinforces your positioning.

### How Accuracy Is Determined

To evaluate whether a perception is correct or incorrect, Genezio compares it against your **[Knowledge Base](knowledge-base.html)** — a brand-specific source of truth you set up once in **Brand Settings**.

The Knowledge Base typically includes:

* product descriptions and capabilities
* pricing and plans
* target audience and use cases
* competitive differentiators
* any other official brand guidelines

By comparing AI-generated claims against your Knowledge Base, Genezio can flag perceptions that misrepresent your brand — giving you a clear view of where answer engines are getting it right and where they are getting it wrong.

### Grounded Perceptions

When a Knowledge Base is in place, every perception extracted from a conversation gets a **grounded** badge showing whether it could be verified — and how. The badge has three states:

* **Grounded-correct** — the perception matches what your Knowledge Base says is true
* **Grounded-incorrect** — the perception contradicts your Knowledge Base
* **Not grounded** — the perception couldn't be verified against your Knowledge Base either way

A tooltip on the badge explains what each state means in context.

The badge turns a list of perceptions into a triage queue: scan the grounded-incorrect ones first (these are answer engines actively misrepresenting your brand), then work through the not-grounded ones (gaps in either your Knowledge Base or in how your messaging is documented publicly). Grounded-correct perceptions are the wins — proof that the narrative answer engines have about you matches the truth.

Every brand gets a Knowledge Base from day one (the brand's website is crawled in automatically when the brand is created), so the grounded layer is active immediately. How much it can verify depends on how much truth your Knowledge Base covers — see [Knowledge Base](knowledge-base.html) for what to add.

---

## Perceptions and Their Sources

Every perception can be traced back to the **sources** that produced it. This is one of the most useful things you can do with a perception: see *why* the AI said what it said.

When you open a perception, Genezio shows the **citation paragraphs** (the exact passages from cited webpages) that back the claim, with the **matching text highlighted**. That lets you jump from "the AI says we're hard to set up" straight to the third-party page that planted that idea — so you know exactly where to focus a correction or outreach effort.

The link works in both directions:

* **From a perception** → see the sources (citation paragraphs) that support it, with matched text highlighted.
* **From a citation** → see all the perceptions derived from that source.
* **By citation domain** → view the perceptions associated with a specific domain, so you can tell which websites are shaping your narrative.

Genezio also distinguishes between sources that are **explicitly cited** by the answer engine and brands or pages that are merely **mentioned**, so you can separate the references the model actually leaned on from passing mentions.

See [Citations](citations.html) for how sources are captured and classified.

---

## Other Perception Attributes

### Text

The actual claim made in the AI response.

Example:

```
HubSpot is known for strong marketing automation features.
```

---

### Brand References

The brands mentioned in the perception.

A single perception may reference one or multiple brands.

Example:

```
HubSpot and Salesforce are widely used CRM platforms.
```

---

### Supporting Citations

Perceptions are linked to one or more **citations (sources)** that the AI system used when generating the claim.

This makes it possible to trace a perception back to the webpage that influenced it — and understand why the AI made a particular claim.

---

## Perceptions Across Conversations

Perceptions are extracted from every conversation that Genezio runs with AI systems, and they are generated in your **brand's own language**, so reports read naturally for local markets.

By aggregating perceptions across many conversations, Genezio can identify patterns such as:

* recurring claims made about a brand — correct or incorrect
* common inaccuracies that need to be addressed
* frequently mentioned competitors
* differences in how AI systems describe the same brand

This helps organizations understand the **narrative that AI systems associate with their brand** — and whether that narrative is accurate.

---

## Perceptions in the Interface

In Genezio, perceptions can be explored in the **conversation detail view** and across aggregated analysis views. Lists of perceptions can be **sorted** to bring the most relevant claims to the top.

Users can inspect:

* the original AI response
* the extracted perceptions
* the accuracy of each claim
* the associated citations, with the supporting paragraphs highlighted
* the brands mentioned in each claim

This transparency allows teams to see exactly what AI systems are saying about their brand — and whether it is true.

---

## Perceptions and Insights

Perceptions form the foundation for several higher-level insights in Genezio.

They contribute to:

* AI Recommendations — incorrect claims can reduce your recommendation rate
* AI Visibility — inaccurate descriptions affect how often answer engines surface your brand
* Share of Voice — the accuracy of claims shapes competitive positioning
* Competitive positioning — understanding which claims favor you vs. competitors
* [AI Perception Summary](../insights/ai-perception-summary.html) — the overall, AI-generated narrative of how your brand is perceived

By structuring AI responses into perceptions and evaluating their accuracy, Genezio transforms unstructured AI answers into data that can be measured, verified, and acted on.

---

## Next Steps

To understand how perceptions and citations combine to measure brand presence, see:

* [Insights -> Visibility Score](../insights/ai-visibility-score.html)
* [Insights -> Share of Voice](../insights/share-of-voice.html)
* [Insights -> AI Perception Summary](../insights/ai-perception-summary.html)

These pages explain how Genezio turns conversation data into measurable AI visibility metrics.
