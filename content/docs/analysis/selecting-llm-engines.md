# Selecting LLM Engines

This guide explains how to choose which AI systems Genezio will use when running conversations.

Genezio can execute scenarios across multiple **LLM engines** (AI assistants). Running conversations across different engines allows you to understand how your brand appears across the AI ecosystem.

---

## Where to Configure LLM Engines

To select which engines Genezio should use:

1. Open your **Brand** in Genezio.
2. Go to **Settings**.
3. Open **Brand Details**.
4. Locate the **LLM Engines** section.

From here you can enable or disable the engines you want Genezio to use when running conversations.

---

## Available Engines

Depending on your plan and platform availability, Genezio may support engines such as:

* ChatGPT
* Claude
* Gemini
* Perplexity
* Google AI Overview

Each engine may produce different answers, citations, and brand mentions.

For most engines, Genezio runs conversations **through the same user interface that a human would use**. In other words, the system interacts with the LLM the same way a normal user would when typing questions in the product interface. This approach helps reproduce real-world AI interactions as closely as possible.

Some engines can also be run **API-only**. In these cases, conversations are executed directly through the provider's API rather than through a user interface.

Running conversations across multiple engines helps provide a more complete picture of your **AI Visibility**.

---

## When Changes Take Effect

Changes to selected LLM engines do not affect conversations immediately.

Genezio runs conversations in **daily batches**.

When you modify the engine selection:

* the change is saved immediately
* new conversations using the updated engine list will start in the **next daily batch**

This means that changes will typically become visible **the following day**, once the next batch of conversations has been executed.

---

## Why Engine Selection Matters

Different AI systems may:

* recommend different brands
* cite different sources
* interpret questions differently

By selecting multiple engines, you can compare how your brand appears across the AI landscape.

---

## Next Steps

To understand how conversations are executed across AI systems, see:

* [Core Concepts -> Conversations](../core-concepts/conversations.html)

This page explains how Genezio runs scenarios against different AI engines and analyzes the responses.
