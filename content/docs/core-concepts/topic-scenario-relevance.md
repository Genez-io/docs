# Topic / Scenario Relevance

In Genezio, **Topic / Scenario Relevance** measures how well a scenario captures a real decision context where brands are discussed by AI systems.

Every **scenario** and **topic** has a Relevance score expressed as a percentage.

This score helps answer an important question:

**When this scenario is executed, do AI systems actually talk about brands in this category?**

If AI responses frequently mention your brand or competitors, the scenario is considered highly relevant. If responses rarely mention any brands, the scenario is likely poorly framed or unrelated to how users actually ask questions.

---

## What Relevance Represents

Relevance measures the percentage of conversations where **either your brand or one of your competitors appears**.

It is calculated as:

```
Topic / Scenario Relevance = (Conversations mentioning your brand or competitors / Total conversations) x 100
```

Example:

* Conversations executed: 50
* Conversations where at least one brand appears: 40

Relevance:

```
80%
```

This means that in 80% of the conversations generated from that scenario, the AI system mentioned at least one relevant brand.

---

## Why Topic / Scenario Relevance Matters

A scenario is meant to simulate a realistic user situation where someone is evaluating products or services.

If AI responses do not mention **any brands**, the scenario may not represent a realistic discovery question.

For example, a vague or poorly framed scenario might lead the AI system to give general advice without recommending products.

In such cases, the scenario provides little value for competitive analysis.

Relevance helps identify these cases.

---

## Interpreting Relevance Scores

### High Relevance (Near 100%)

A relevance score close to **100%** indicates that the scenario consistently triggers brand discussions.

This usually means the scenario is well written and accurately reflects how users ask AI assistants for recommendations.

These scenarios are ideal for measuring **Brand Visibility** and competitive positioning.

---

### Moderate Relevance

A mid-range relevance score indicates that brands appear in some responses but not consistently.

This may suggest that:

* the scenario could be clearer
* the question is somewhat generic
* the AI system sometimes answers without recommending products

---

### Low Relevance

A low relevance score indicates that AI systems rarely mention any brands in responses.

This usually means the scenario should be improved.

Possible issues include:

* the scenario is too abstract
* the question does not imply product discovery
* the user goal is not clearly defined

Improving the scenario can significantly increase its usefulness for analysis.

---

## Scenario-Level vs Topic-Level Relevance

Relevance is calculated at two levels.

### Scenario Relevance

Each scenario has its own relevance score based on the conversations generated from that scenario.

### Topic Relevance

Topic relevance is the **average relevance of its scenarios**.

This helps users understand whether a topic overall is producing meaningful conversations where brands are discussed.

---

## Relevance and Scenario Quality

Relevance is also a useful indicator of **scenario quality**.

A well-designed scenario should:

* clearly describe a user situation
* include a realistic goal
* naturally lead to product recommendations

When these conditions are met, AI systems typically respond with brand suggestions, leading to higher relevance scores.

---

## Improving Relevance

If a scenario has low relevance, it can often be improved by making the user's goal more explicit.

Instead of vague prompts such as:

```
Tell me about customer management.
```

A stronger scenario might describe a concrete situation such as:

```
The persona runs a small startup and needs a tool to manage incoming sales leads and follow up with potential customers.
```

This type of situation is more likely to trigger brand recommendations.

---

## Why Topic / Scenario Relevance Is Important

Relevance ensures that the conversations used to measure AI visibility actually represent **realistic decision-making scenarios**.

Without relevance filtering, analysis could include conversations where no brands appear, which would make visibility metrics less meaningful.

By monitoring relevance, teams can continuously refine scenarios and improve the quality of their AI visibility analysis.

---

## Next Steps

To understand how brand mentions inside relevant conversations contribute to visibility metrics, see:

* [Core Concepts -> Brand Visibility](./brand-visibility.html)

This page explains how Genezio measures how often your brand appears in AI-generated answers.
