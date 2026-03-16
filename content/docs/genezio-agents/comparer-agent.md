# Comparer Agent

The **Comparer Agent** is a Genezio Agent type used to evaluate how AI systems compare multiple brands in the same conversation.

It is designed for competitive positioning analysis.

---

## How It Works

For a Comparer Agent topic:

* the scenario names two or more brands
* Genezio runs a multi-step comparison conversation
* prompts ask for differences, tradeoffs, and best-fit recommendations

Example scenario:

```
Alex is evaluating HubSpot and Pipedrive for his sales team of five. He needs a CRM that is easy to onboard, has good reporting, and works well with their existing email workflow. He wants to understand the key differences before making a decision.
```

From this scenario, Genezio generates conversational messages such as:

> **User query:** ***I'm comparing HubSpot and Pipedrive for a sales team of five. What are the main differences between the two?***

> **User query:** ***Which one is easier to onboard for a small team with no CRM experience?***

> **User query:** ***How do they compare on reporting and email integration?***

---

## Typical Use Cases

Comparer Agent conversations help teams understand:

* which competitor is favored in side-by-side comparisons
* how AI systems frame strengths and weaknesses per brand
* what objections or limitations are repeatedly mentioned

---

## What You Can Learn from Comparer

Using Comparer, you can:

* See how AI engines frame your brand against specific competitors
* Compare recommendation and visibility rates side by side
* Identify the strengths and weaknesses AI associates with each brand
* Generate SWOT-style insights to guide your competitive content strategy

The result is a clear view of where you're winning, where you're losing, and what narratives are driving the difference.

---

## KPI Impact

Comparer Agent conversations **do not count toward AI Recommendations or AI Visibility**. Because the brand names appear in the prompt, including them would distort the metrics.

Instead, the Comparer is a **competitive analysis tool**. It consumes the brand-level KPIs that Genezio has already calculated from Prompter and Recommender conversations, and uses them alongside head-to-head AI conversations to show how your brand stacks up against specific competitors.

---

## Related Pages

* [Core Concepts -> Competitors](../core-concepts/competitors.html)
* [Core Concepts -> Brand Visibility](../core-concepts/brand-visibility.html)
* [Conversation Analysis -> Running Conversations](../analysis/running-conversations.html)
