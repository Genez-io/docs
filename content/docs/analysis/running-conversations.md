# Running Conversations

This guide explains how Genezio runs conversations and how the results are generated.

Conversations are the core mechanism Genezio uses to measure how AI systems talk about your brand and your competitors.

---

## Conversation Execution

Genezio runs conversations automatically on a **daily schedule**.

Each day, the system executes:

* every **scenario**
* for every selected **LLM engine**

This means that if you have:

* 10 scenarios
* 4 LLM engines selected

Genezio will run **40 conversations per day**.

Each of these conversations is stored and analyzed independently.

---

## Persona Influence

Every conversation is influenced by the **persona** associated with the topic.

Each topic in Genezio has a specific persona assigned to it. When a conversation runs:

* the AI interaction is written **as that persona**
* the conversation is executed in the **persona's language**
* the interaction is run **from the persona's geographic location**

This ensures that the AI system responds as if a real user from that context asked the question. Different personas may receive different answers from the same AI system.

For example, a student, a startup founder, and a corporate buyer asking about the same product category may receive different recommendations.

---

## Why Conversations Run Daily

AI systems evolve continuously. Their answers may change because:

* models are updated
* sources on the web change
* new content appears
* the retrieval system changes

Running conversations daily allows Genezio to track how answers evolve over time and detect changes in **AI Visibility**.

---

## What Happens During a Conversation

When a conversation runs, Genezio performs several steps:

1. The system selects a **scenario**.
2. The conversation is executed against a selected **LLM engine**.
3. Genezio captures the full response from the AI system.
4. The response is analyzed and structured data is extracted.

This analysis produces several key signals used throughout the platform.

---

## Data Extracted from Conversations

Each conversation exposes multiple layers of analysis.

### Query Fanouts

The additional searches the AI system performs internally while constructing an answer.

Query fanouts reveal how the AI system explores the topic.

---

### Citations

The webpages (sources) referenced by the AI system when generating the answer.

These sources help explain where the information in the response came from.

---

### Statements

Atomic claims extracted from the AI response.

Statements allow Genezio to analyze how brands are described and compare narratives across conversations.

---

### Competitors

Brands mentioned in the same response as your brand are automatically detected and tracked as competitors.

---

### SWOT Analysis (Comparer Agent Conversations)

For **Comparer Agent topics**, Genezio generates an additional analysis layer.

When the AI response compares brands, Genezio extracts information that can be structured as a **SWOT analysis**:

* Strengths
* Weaknesses
* Opportunities
* Threats

This helps reveal how AI systems position competing brands relative to each other.

---

## Inspecting Conversations

Each conversation can be inspected in the **Conversation Detail View**.

This view allows you to see:

* the full interaction with the AI system
* the prompts sent to the model
* the responses generated
* detected query fanouts
* extracted citations
* extracted statements

This transparency allows teams to understand exactly **why a brand appeared or did not appear in an AI answer**.

---

## Re-running Conversations

Conversations are normally executed automatically each day.

However, they can also be re-run when:

* a scenario is updated
* a new scenario is added
* a topic is modified

This allows you to quickly test new scenarios and observe how AI systems respond.

---

## Next Steps

To understand the structure of the data extracted from conversations, see:

* [Core Concepts -> Query Fanouts](../core-concepts/query-fanouts.html)
* [Core Concepts -> Citations](../core-concepts/citations.html)
* [Core Concepts -> Statements](../core-concepts/statements.html)

These pages explain how Genezio converts AI responses into structured insights.
