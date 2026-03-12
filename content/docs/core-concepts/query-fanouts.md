# Query Fanouts

In Genezio, **query fanouts** represent the additional searches that an AI system performs internally while answering a question.

When a user asks a question, modern AI systems rarely rely on a single query. Instead, they expand the original question into multiple related searches in order to gather more information.

These additional searches are called **follow-up searches (or query fanouts)**.

Understanding query fanouts is important because they strongly influence:

* which sources are retrieved
* which brands appear in answers
* which citations are generated

---

## Why Query Fanouts Exist

User questions are often broad or ambiguous. A single search query may not retrieve enough information for the AI system to generate a useful answer.

To improve the quality of responses, the AI system expands the original question into several related queries that explore the topic from different angles.

For example, the question:

> **User query:** ***What CRM should a startup use?***

may internally expand into searches such as:

* best CRM for startups
* startup CRM comparison
* HubSpot vs Pipedrive for startups
* affordable CRM tools for small teams

Each of these searches retrieves different documents that the AI system can use when constructing its response.

---

## Where Query Fanouts Come From

The exact search infrastructure used by most AI systems is **not publicly documented**. Outside the companies building these systems, no one knows precisely which search engines or indexes are used to retrieve information.

However, based on public statements, research papers, and observed behavior, it is widely believed that AI systems rely on a **combination of sources**, such as:

* major web search engines (such as Google or Bing)
* internal search tools built by the AI provider
* open web content databases

In practice, this means that when an AI system generates fanout queries, those queries may be executed across several different search tools before content is returned to the model.

Because these systems are constantly evolving, the exact sources used may differ between AI platforms and may change over time. What matters for your content strategy is that **your content needs to be discoverable across multiple search channels**, not just one.

---

## How Query Fanouts Influence AI Answers

Query fanouts determine which documents are retrieved during the information gathering stage.

Those documents influence:

* the brands mentioned in the answer
* the sources cited
* the claims included in the response

For example, if a fanout query retrieves comparison articles that mention specific products, those products are more likely to appear in the generated answer.

Because of this, query fanouts are one of the strongest signals shaping **AI Recommendations and Visibility**.

---

## Query Fanouts in Genezio

Genezio detects and extracts query fanouts generated during conversations with AI systems.

For each conversation, Genezio analyzes:

* the additional queries the AI system explores
* how those queries relate to the original prompt
* which sources are retrieved for each query

This allows teams to see **what the AI system actually searched for** when answering a question.

---

## Example

Original prompt:

> **User query:** ***What CRM should a startup use?***

Detected fanout queries might include:

* **Query fanout:** *best CRM for startups*
* **Query fanout:** *CRM tools for SaaS startups*
* **Query fanout:** *HubSpot vs Pipedrive*
* **Query fanout:** *startup CRM pricing comparison*

These queries reveal how the AI system expands the original question in order to build a response.

---

## Why Query Fanouts Matter

Analyzing fanout queries helps organizations understand:

* how AI systems interpret a topic
* which questions influence AI-generated answers
* which sources shape the information landscape
* where content opportunities exist

For example, if fanout queries frequently include topics that your brand does not address in its content, this may indicate an opportunity to improve visibility.

---

## Query Fanouts vs Keywords

Traditional SEO focuses on optimizing pages for specific keywords.

Query fanouts reflect a broader concept: **how AI systems explore a topic**.

Instead of relying on a single keyword, AI systems examine multiple related queries before generating an answer.

Understanding this set of queries provides deeper insight into how AI systems build their responses.

---

## Query Fanouts in the Conversation View

In Genezio, query fanouts can be inspected in the **conversation detail view**.

This view shows:

* the original prompt
* the detected fanout queries
* the sources retrieved for those queries
* the final AI response

This transparency allows users to understand how an AI system arrived at a specific answer.

---

## Next Steps

To understand how sources retrieved through fanout queries influence answers, see:

* [Core Concepts -> Citations](./citations.html)
* [Core Concepts -> Statements](./statements.html)

These pages explain how Genezio extracts structured information from AI responses.
