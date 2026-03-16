# Introspector Agent

The **Introspector Agent** is a Genezio Agent type focused on understanding how AI systems describe a specific brand.

It is used for brand explanation and positioning analysis, not for organic visibility measurement.

---

## How It Works

For an Introspector Agent topic:

* the scenario explicitly includes the target brand
* Genezio runs a multi-step conversation about that brand
* prompts explore use cases, fit, strengths, and limitations

Example scenario:

```
Sarah has heard about HubSpot from a colleague and wants to understand what it actually does before evaluating it. She wants to know what types of teams use it, what its main strengths are, and whether it has any notable limitations.
```

From this scenario, Genezio generates conversational messages such as:

> **User query:** ***What is HubSpot mainly used for? What kind of teams typically use it?***

> **User query:** ***What are HubSpot's main strengths compared to other tools in its category?***

> **User query:** ***Are there any common limitations or complaints about HubSpot?***

---

## Typical Use Cases

Introspector Agent conversations help teams analyze:

* how AI systems explain a brand's category and value
* recurring strengths or weaknesses in brand narratives
* consistency of brand framing across AI engines

---

## Visibility KPI Impact

Introspector Agent conversations are **excluded** from Brand Visibility calculations because the brand name is already present in the prompt.

Including these conversations would inflate visibility results.

---

## Why It Still Matters

Even though it is excluded from visibility KPIs, this agent is valuable for:

* narrative quality review
* positioning audits
* messaging consistency analysis

---

## Related Pages

* [Core Concepts -> Statements](../core-concepts/statements.html)
* [Core Concepts -> Brand Visibility](../core-concepts/brand-visibility.html)
* [Core Concepts -> Conversations](../core-concepts/conversations.html)
