# Brand Visibility

In Genezio, **Brand Visibility** measures how often your brand appears in AI-generated answers.

It answers a simple question:

**When users ask AI assistants questions related to your category, how often does your brand show up?**

Brand Visibility is expressed as a **percentage of conversations where the brand is mentioned**.

---

## What Brand Visibility Represents

When Genezio runs conversations with AI systems, the responses may or may not include your brand.

Examples:

* Your brand is recommended in the answer
* Your brand appears in a comparison
* Your brand is mentioned alongside competitors

If the brand appears anywhere in the response, that conversation counts as a **visible occurrence**.

If the brand does not appear, the conversation counts as **not visible**.

---

## How Brand Visibility Is Calculated

Brand Visibility is calculated as:

```
Brand Visibility = (Conversations where the brand appears / Total eligible conversations) x 100
```

Example:

* Total conversations analyzed: 100
* Conversations mentioning the brand: 78

Brand Visibility:

```
78%
```

This means the brand appears in **78% of AI-generated answers** for the analyzed topics.

---

## Which Conversations Are Included

Not all Genezio Agent types contribute to Brand Visibility.

Genezio only includes conversations where the AI system **chooses the brands on its own**, without being biased by the prompt.

Therefore, only the following Genezio Agent types are used:

### Prompter Agent

Prompter Agent conversations ask a direct discovery question.

Example:

> **User query:** ***What CRM should a startup use?***

The AI system decides which brands to mention.

---

### Recommender Agent

Recommender Agent conversations simulate a user asking for recommendations.

The AI system selects which brands to suggest based on the scenario.

---

### Excluded Agent Types

Some agent types are **excluded** from Brand Visibility because the brand name appears in the prompt itself.

These include:

**Introspector Agent**

Example:

> **User query:** ***What is HubSpot used for?***

**Comparer Agent**

Example:

> **User query:** ***HubSpot vs Salesforce***

Including these would artificially inflate visibility because the brand is already part of the prompt. Note that Comparer conversations **do count toward AI Recommendations** — see [Brand Recommendation](brand-recommendation.md).

---

## Accuracy and Sample Size

Brand Visibility is calculated using an **accuracy model**.

Instead of relying on a fixed number of conversations, Genezio analyzes the **most recent conversations until a reliable accuracy threshold is reached**.

By default, Genezio calculates visibility using the latest conversations until the estimate reaches a **90% accuracy level**.

This ensures that the visibility percentage is reliable and trustworthy.

---

## Accuracy Range

Because Brand Visibility is estimated from a sample of conversations, the result includes an **accuracy range**.

For example:

```
Brand Presence: 78%
Accuracy range: 54% - 100%
Accuracy level: 90%
```

This means that based on the analyzed conversations, Genezio is **90% confident** that the true visibility of the brand falls within that range.

As more conversations are executed, the range typically becomes narrower and the estimate becomes more precise.

---

## Why Brand Visibility Matters

Brand Visibility provides a high-level signal of how AI systems perceive a brand within a category.

A higher visibility score generally means:

* the brand is frequently recommended
* the brand appears in comparison lists
* the brand is strongly associated with the topic

A lower score may indicate that competitors dominate AI-generated answers.

---

## Brand Visibility Over Time

Genezio tracks Brand Visibility continuously as new conversations are executed.

This allows teams to observe trends such as:

* increasing visibility after publishing new content
* competitors gaining or losing presence
* changes in how AI systems interpret a category

Monitoring visibility over time helps organizations understand how their presence evolves across AI platforms.

---

## Next Steps

To understand how visibility compares across brands, see:

* [Insights -> Share of Voice](../insights/share-of-voice.html)

This page explains how Genezio compares brand visibility across competitors within the same topic.
