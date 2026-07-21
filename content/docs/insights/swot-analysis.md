# SWOT Analysis

Genezio automatically extracts a **SWOT analysis** (Strengths, Weaknesses, Opportunities, Threats) from Comparer conversations — showing how AI systems position your brand against the specific competitors you compete with.

SWOT is generated from the language answer engines use when comparing brands head-to-head: which strengths they highlight, which weaknesses they raise, where competitors look more favorable, and where your brand has room to gain ground.

---

## Selecting Which Competitors to Compare Against

For every topic, you can pick the exact set of competitors that the Comparer Agent should evaluate your brand against.

This selection is made **at the topic level** and is used when Genezio auto-generates Comparer scenarios for that topic. Instead of comparing your brand against any brand that happens to surface in AI answers, Comparer scenarios target the specific competitors you care about.

Choosing the right competitors per topic gives you a focused, decision-useful SWOT — one that reflects the actual market you're competing in for that subject area.

---

## SWOT in the Conversation Drawer

When you open a Comparer-type conversation in the **conversation drawer**, Genezio displays an inline SWOT analysis directly in the view.

The SWOT shows:

* **Strengths** — what answer engines say your brand does well versus the competitors in the conversation
* **Weaknesses** — limitations or objections answer engines raise about your brand
* **Opportunities** — areas where competitors are vulnerable or where AI positioning is unstable
* **Threats** — areas where competitors are framed more favorably than your brand

The same SWOT is also aggregated and shown at the **scenario** and **topic** level, so you can move from a single conversation up to the broader competitive picture without losing the underlying evidence.

---

## SWOT Comparison View

For an overall view across your full competitive landscape, Genezio provides a dedicated **SWOT Comparison** view, available from the menu under **Competitors -> SWOT**.

The redesigned view is built around a **brand-vs-competitor picker**: choose your brand and the competitor you want to examine, and the comparison reframes around that pairing. Instead of reading every SWOT at once, you work through the matchups that actually matter to you.

Each comparison opens with an **AI-written overview** — a short written summary of how the two stack up — so you get the conclusion first and then dig into the four quadrants for the detail behind it. It's the fastest way to answer "how are we doing against them?" without interpreting a grid yourself.

The view covers a SWOT analysis for:

* your brand
* each of your tracked competitors

Seeing SWOTs side by side helps you spot patterns — recurring strengths competitors share, weaknesses unique to your brand, and opportunities where no competitor is currently positioned well.

**Competitor logos** are shown throughout the SWOT views, making the comparison faster to scan — you can recognize each brand at a glance instead of reading down a list of names.

---

## Opening SWOT From Anywhere

SWOT is no longer just a destination you navigate to. **Wherever a competitor appears in Genezio, you can open its SWOT as a drawer** in place — without losing the view you were working in.

Alongside the SWOT, that drawer surfaces:

* **the competitor's own products** — the products answer engines associate with them
* **co-mentioned products** — the products that get named alongside them, including yours

That turns a competitor from a name in a list into a full picture: how AI frames them, what they're known for selling, and which products they're being weighed against. These tie into the product-level data in [Shopping](../shopping/products.html).

---

## Sources Behind Each SWOT Point

Every SWOT point can be traced back to the evidence that produced it. For each strength, weakness, opportunity, or threat, Genezio can surface the **citation paragraphs (sources)** that back it — the actual passages from the webpages answer engines drew on — with the **matching text highlighted**.

This means you can move from a high-level claim ("competitors are framed as more affordable") straight to the exact webpage passage that produced it, without guessing where the framing came from.

It's the same source-tracing already available for [perceptions](../core-concepts/perceptions.html), now applied to your competitive SWOT — so every strength, weakness, opportunity, and threat is auditable down to the source paragraph.

---

## How SWOT Is Generated

SWOT insights are derived from **Comparer Agent** conversations only. Because Comparer conversations name brands explicitly in the prompt, answer engines respond with direct head-to-head framing, which is the signal Genezio needs to extract Strengths, Weaknesses, Opportunities, and Threats.

Prompter, Recommender, and Introspector conversations do not contribute to SWOT — those agents are designed for unbranded discovery and brand-perception measurement, not direct comparison.

---

## Related Pages

* [Genezio Agents -> Comparer Agent](../genezio-agents/comparer-agent.html)
* [Core Concepts -> Competitors](../core-concepts/competitors.html)
