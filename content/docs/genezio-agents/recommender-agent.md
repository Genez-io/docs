# Recommender Agent

The **Recommender Agent** is a Genezio Agent type that simulates recommendation-seeking behavior in multi-step AI conversations.

It is designed for scenarios where a persona is trying to find a specific solution that fits their needs and constraints.

---

## How It Works

For a Recommender Agent topic:

* the scenario defines the user situation and goal
* Genezio generates a sequence of prompts from that scenario
* the AI conversation runs across multiple turns

Example scenario:

```
John's team of three has been tracking leads in a spreadsheet but they are losing follow-ups as inbound volume grows. They need a simple CRM that integrates with Gmail and costs under $50/user/month.
```

From this scenario, Genezio generates conversational messages such as:

> **User query:** ***I run a small startup and we've been tracking leads in a spreadsheet, but it's not working anymore. What CRM tools would you recommend for a team of three?***

> **User query:** ***We need something that integrates with Gmail and stays under $50 per user per month. Which of those would fit?***

---

## Typical Use Cases

Recommender Agent conversations are useful when you want to evaluate:

* recommendation frequency for your brand
* how your brand is positioned against competitors
* how recommendations change after follow-up constraints

---

## KPI Impact

Recommender Agent conversations are a core input to:

* **AI Recommendations** - percentage of Recommender Agent conversations where your brand is recommended
* **Brand Visibility** - included because brands are selected by the AI, not forced by prompt wording

---

## Multi-Step Behavior

Multi-step flow makes this agent useful for realistic buyer journeys:

* initial broad recommendation
* filtering by budget, features, or team size
* shortlisting alternatives

---

## Related Pages

* [Introduction -> What KPIs Are We Measuring](../introduction/what-kpis-are-we-measuring.html)
* [Core Concepts -> Topics](../core-concepts/topics.html)
* [Core Concepts -> Conversations](../core-concepts/conversations.html)
