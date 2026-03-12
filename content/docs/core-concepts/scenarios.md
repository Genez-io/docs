# Scenarios

In Genezio, a **scenario** represents a realistic situation in which a persona is trying to achieve a goal related to a specific topic.

Scenarios are the **starting point for every conversation** that Genezio runs with an AI system.

While topics define the general subject area, scenarios describe **the concrete situation that leads a user to ask questions**.

---

## Topics vs Scenarios

It is important to distinguish between topics and scenarios.

A **topic** defines the subject area being analyzed.

Example topic:

```
CRM for startups
```

A **scenario** describes a realistic situation involving the persona.

Example scenario:

```
The persona is a founder of a small SaaS startup with two co-founders. They recently started getting inbound leads and need a simple way to track contacts and follow up with potential customers.
```

From this scenario, Genezio generates one or more prompts that are sent to the AI system during the conversation.

---

## How Scenarios Are Used

Every conversation run by Genezio begins with a scenario.

The process works as follows:

1. A **persona** defines who the user is (language, location, context).
2. A **topic** defines the subject area.
3. A **scenario** defines the situation and the persona's goal.
4. Genezio generates **prompts (messages)** from that scenario.
5. Those prompts are sent to the AI engine during the conversation.

This structure ensures that conversations are grounded in **realistic user contexts rather than abstract prompts**.

---

## Scenario Structure

A scenario describes the **situation and goal** the persona is experiencing.

The **persona context is implicit** in the scenario because every scenario belongs to a **topic**, and every topic is associated with a **persona**.

This means the persona's:

* role or profile
* language
* geographic location

are already defined before the scenario is executed.

The scenario itself therefore focuses on the **user's situation and objective**, while the persona provides the broader context for how the conversation should be conducted.

### Situation

The circumstances that led the user to search for a solution.

Example:

* receiving the first sales leads
* preparing for a marathon
* comparing banking options

### Goal

What the persona wants to achieve.

Example:

* find a CRM
* choose a running shoe
* open a bank account

Because the persona already defines *who the user is* and *where they are located*, the scenario focuses on *why they are asking the question*.

This separation allows Genezio to reuse scenarios across realistic persona contexts while keeping conversations grounded in specific goals.

---

## Example Scenario

Topic:

```
CRM for startups
```

Persona:

* Startup founder
* Located in San Francisco
* Language: English

Scenario:

```
John runs a small SaaS startup with two co-founders. They have recently started receiving inbound leads and need a simple way to track potential customers and follow up.
```

From this scenario, Genezio may generate prompts such as:

> **User query:** ***What CRM would you recommend for a small SaaS startup?***

and follow-ups such as:

> **User query:** ***Which of these tools is easiest for a team of three people?***

The scenario provides the **context**, while the prompts represent the **actual messages sent to the AI system**.

---

## Scenarios and Genezio Agents

Scenarios are used differently depending on the Genezio Agent type.

### Prompter Agent

For **Prompter Agent topics**, the scenario itself becomes the prompt.

The text is sent **exactly as written** to the AI system and the interaction is **single-turn**.

### Recommender Agent

For **Recommender Agent topics**, the scenario defines the starting situation. Genezio generates multiple prompts during the conversation to simulate a realistic recommendation flow.

### Introspector Agent

For **Introspector Agent topics**, the scenario places the persona in a situation where they want to understand a specific brand.

Genezio generates prompts that explore:

* what the brand does
* who it is designed for
* its strengths and weaknesses

### Comparer Agent

For **Comparer Agent topics**, the scenario describes a situation where the persona is evaluating multiple brands.

Genezio generates prompts that compare those alternatives and analyze their differences.

---

## Why Scenarios Matter

Scenarios allow Genezio to simulate **real user behavior**.

In the real world, people rarely ask generic questions like "best CRM". Instead, they ask questions based on their situation.

For example:

* a founder looking for their first CRM
* a teenager looking for a debit card
* a runner preparing for a marathon

By modeling these situations, Genezio can analyze how AI systems respond to **realistic user needs and contexts**.

---

## Next Steps

To see how scenarios turn into interactions with AI systems, continue with:

* [Core Concepts -> Conversations](./conversations.html)

This page explains how Genezio executes conversations and analyzes the responses generated by AI engines.
