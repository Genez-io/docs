# Selecting Answer Engines

This guide explains how to choose which AI systems Genezio will use when running conversations.

Genezio can execute scenarios across multiple **answer engines** (AI assistants). Running conversations across different engines allows you to understand how your brand appears across the AI ecosystem.

---

## Where to Configure Answer Engines

To select which engines Genezio should use:

1. Open your **Brand** in Genezio.
2. Go to **Settings**.
3. Open **Brand Details**.
4. Locate the **Answer Engines** section.

From here you can enable or disable the engines you want Genezio to use when running conversations.

---

## Available Engines

Genezio currently supports the following answer engines:

* GPT-5.4
* GPT-4.1
* GPT-4o Mini
* ChatGPT
* GPT-4o Search Preview
* Google AI Overview
* Perplexity
* Claude
* Google AI Mode
* Google Gemini
* Microsoft Copilot
* DeepSeek
* Grok

Each engine may produce different answers, citations, and brand mentions.

The underlying models are periodically refreshed as providers ship updates (for example, the Gemini models were upgraded to a newer Flash Lite generation), so results reflect current model behavior.

For most engines, Genezio runs conversations **through the same user interface that a human would use**. In other words, the system interacts with the answer engine the same way a normal user would when typing questions in the product interface. This approach helps reproduce real-world AI interactions as closely as possible.

Some engines can also be run **API-only**. In these cases, conversations are executed directly through the provider's API rather than through a user interface.

Running conversations across multiple engines helps provide a more complete picture of your **AI Recommendations and Visibility**.

---

## Customizing Which Engines You Run

Brands can now **customize which answer engines they run against**. Instead of a fully self-serve subscription that locked everyone into the same engine list, you choose the **engine mix that fits your brand** — focusing your attention and spend on the AI systems your audience actually uses.

On top of the brand-level selection, Genezio supports **per-topic LLM filtering**. Individual topics can **override** which engines they run against, so a specific topic can run on a narrower or different set of engines than the brand default.

This gives marketers two levels of control:

* **Brand level** — set the default engine mix that matters most for your brand.
* **Topic level** — narrow or change the engines for individual topics, so you can concentrate effort on the engines that matter for each topic.

For example, you might run your full engine set across your core topics, but limit an experimental or region-specific topic to just the one or two engines that are relevant there.

---

## When Changes Take Effect

Changes to selected answer engines do not affect conversations immediately.

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

This page explains how Genezio runs scenarios against different answer engines and analyzes the responses.
