# Product Visibility

**Product Visibility** extends Genezio from the brand level down to the individual product level. Until now, Genezio answered *"how do AI assistants talk about my brand?"* Shopping and Product Visibility answers a sharper question: *"how do AI assistants talk about my products?"*

This matters because answer engines increasingly don't stop at naming a brand. They name a **specific product** — a model number, a SKU, a variant — and that named product is the one the shopper goes on to buy.

---

## Brand-Level vs. Product-Level Visibility

[Brand Visibility](../core-concepts/brand-visibility.html) tells you whether your company shows up in the answer. Product Visibility tells you *which of your products* shows up.

The difference is the difference between:

* **Brand-level:** "For running shoes, the AI mentions your brand in most answers." Good — but it doesn't tell you which shoe.
* **Product-level:** "When it mentions your brand, it names last season's model, not the one you're currently promoting."

Two brands can have identical brand visibility and completely different commercial outcomes, because one has its hero product named in the answer and the other has a discontinued line named instead. Product-level data is where that gap becomes visible.

---

## Why It Matters for Marketers

* **The named product wins the sale.** When an AI assistant recommends a specific product, the shopper's consideration set often collapses to what was named. Being the brand in the answer is no longer enough.
* **You find out which products AI actually knows.** Your catalog and the products answer engines talk about are rarely the same list. Product Visibility shows you the real overlap.
* **Launches and campaigns become measurable at the product level.** You can see whether the product you're actively pushing has started appearing in AI answers — or whether an older model is still absorbing the attention.
* **Competitive comparisons get concrete.** Instead of "we're losing share in this category," you get "we're losing on this specific product against this specific competitor product."

---

## How Products Get Into Genezio

This is the question every marketer asks first, so it's worth being explicit.

Products are **auto-detected from AI conversations only**. Genezio reads the conversations it already runs against answer engines and discovers the products those engines actually mention.

There is:

* **No catalog upload**
* **No product feed**
* **No site crawl**
* **No manual product entry**

The practical consequence: the product list you see is not your catalog — it is the set of products AI systems are actually talking about. If a product never appears in an AI answer, it will not appear in Genezio. That absence is itself a finding, and usually an actionable one.

---

## The Metrics

Product-level metrics use the **same formulas as the brand-level KPIs**, simply scoped to a single product instead of the whole brand.

For reference, the brand-level definitions are:

```
AI Visibility %      = conversations where it appears / total eligible conversations
AI Recommendations % = conversations where recommended / conversations where visible
```

Scoped to a product, these become:

* **Product Visibility** — how often this product appears in eligible conversations. The reach number.
* **Product Recommendation** — of the conversations where this product appears, how often it is actually recommended. The conversion number.
* **Share of Voice** — how much of the conversation belongs to this product relative to the competing products in the same space.

Because the formulas are identical to the brand KPIs, everything you already know about reading those numbers carries over. See [Insights -> Your KPIs Explained](../insights/your-kpis-explained.html) for the full explanation, and [Insights -> Share of Voice](../insights/share-of-voice.html) for how share is interpreted.

A useful pairing: high Product Visibility with low Product Recommendation means AI knows the product but doesn't advocate for it. Low visibility with high recommendation means it wins when it's mentioned — it just isn't mentioned often enough.

---

## Availability

Shopping and Product Visibility is an **enterprise feature**. It is switched on for a brand by the **Genezio team**, based on your contract.

There is no self-serve toggle in the interface. If you want product-level tracking enabled for your brand, ask the Genezio team and they will turn it on. Once enabled, the shopping pages appear in your navigation and products begin to be detected from the conversations Genezio runs.

---

## What You Can Do Once It's On

* **[Shopping Overview](shopping-overview.html)** — the dashboard: the three metrics, Top 10 product leaderboards, trend charts, period-over-period change, and a total-retailers card.
* **[Products](products.html)** — the full list of products Genezio has detected for your brand.
* **[Product Details](product-details.html)** — a drawer with the detail view for a single product.
* **[Merchants and Retailers](merchants-and-retailers.html)** — which retailers AI associates with your products.

Conversation transcripts are also product-aware: products are tagged and highlighted in the text, and tables and maps render inline, so you can see exactly how a product was framed in the answer.

---

## Related Pages

* [Shopping Overview](shopping-overview.html)
* [Products](products.html)
* [Merchants and Retailers](merchants-and-retailers.html)
* [Core Concepts -> Brand Visibility](../core-concepts/brand-visibility.html)
* [Insights -> Your KPIs Explained](../insights/your-kpis-explained.html)
* [Insights -> Share of Voice](../insights/share-of-voice.html)
