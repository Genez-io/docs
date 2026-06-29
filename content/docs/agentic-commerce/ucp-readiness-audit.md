# UCP Readiness Audit

The **UCP Readiness Audit** checks whether your website is ready to be consumed by AI shopping agents. It crawls your store's setup for the Universal Commerce Protocol (UCP), scores how prepared you are, and runs the same check against your tracked competitors so you can benchmark agent-readiness side by side.

If you're new to the concept, start with [Agentic Commerce Readiness](agentic-commerce-readiness.html) for the why. This page covers the how: what the audit checks, how scoring works, and how to run it.

---

## Why It Matters

AI shopping agents can only recommend and buy from stores they can read. The audit turns "are we ready?" from a guess into a concrete, repeatable score — and shows you exactly which parts of your UCP setup are holding you back. Because it also scores your competitors, you can see whether being more agent-ready is an advantage you can win or a gap you need to close.

---

## What It Checks

The audit looks at three things, in order of how an agent actually encounters your store:

1. **Manifest completeness.** The audit crawls your site's `/.well-known/ucp` manifest — the entry point agents use to discover your store. It checks that the manifest exists and that it contains the information an agent needs to proceed.
2. **Catalog feed quality.** From the manifest, the audit follows the link to your product/catalog feed and evaluates whether the feed is available and whether its data is complete enough for an agent to compare and select products.
3. **Live-endpoint probes.** The audit then probes the live endpoints referenced by your setup to confirm they're reachable and responding, since an agent needs working endpoints to check details and take action.

Together these mirror the path an agent takes: find the manifest, read the catalog, hit the endpoints.

---

## How Scoring Works

The audit scores your store against a defined rule set, labeled **U1 through U7**. These rules map to the three areas above:

* rules covering **manifest presence and completeness**,
* rules covering **catalog feed availability and quality**,
* and rules covering **live endpoint reachability**.

Each rule contributes to an overall readiness score. The result is surfaced on a dedicated UCP page in the dashboard as a **readiness card**, which summarizes where you stand and highlights the rules you're failing so you know what to fix first.

---

## How to Run It

1. Open the **UCP** page in the Genezio dashboard.
2. Make sure your brand's website is set correctly — the audit crawls the live site, so the URL needs to point to your real store. You can check or update this under **Settings -> Brand Details**.
3. Run the audit. Genezio crawls the manifest, follows the catalog feed, and probes the live endpoints.
4. Review the **readiness card** for your overall score and the U1–U7 rule breakdown.

You don't have to run it every time by hand. The audit **re-runs automatically after you edit your website**, so the score reflects your latest changes without extra effort.

---

## Score History and Drift

The audit keeps a **score history**, so you can see how your readiness changes over time. This drift tracking is useful for catching regressions — for example, if a site change accidentally breaks your manifest or takes an endpoint offline, the readiness score will drop and you'll see it in the history rather than discovering it when agents stop recommending you.

---

## Benchmarking Competitors

The audit doesn't just score your brand. It runs the same checks against the **competitors you track in Genezio**, so you can compare agent-readiness directly.

This lets you answer questions like:

* Are my competitors already UCP-ready while I'm not?
* Is agent-readiness an advantage I can claim before they do?
* Which specific rules are my competitors passing that I'm failing?

For more on how Genezio identifies and tracks the brands you're compared against, see [Competitors](../core-concepts/competitors.html) and [Competitor Insights](../insights/competitor-insights.html).

---

## Related Pages

* [Agentic Commerce Readiness](agentic-commerce-readiness.html) — the concept and why agent-readiness matters
* [Competitors](../core-concepts/competitors.html) — how Genezio tracks the brands you're benchmarked against
* [Competitor Insights](../insights/competitor-insights.html) — compare your brand to competitors across AI answers
* [Knowledge Base](../core-concepts/knowledge-base.html) — the source of truth Genezio builds about your brand
* [Improve AI Visibility for an E-commerce Brand](../tutorials/improve-ai-visibility-for-an-ecommerce-brand.html) — a practical walkthrough for e-commerce teams
