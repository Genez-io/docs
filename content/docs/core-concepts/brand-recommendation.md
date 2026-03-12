# Brand Recommendation

In Genezio, **Brand Recommendation** measures how often AI engines actively recommend your brand when users ask for a solution.

It answers the most important question for any marketing team:

**When users ask AI assistants to recommend a product or service in your category, how often is your brand the one they suggest?**

Brand Recommendation is expressed as a **percentage of recommendation-focused conversations where the brand is recommended**.

---

## What Brand Recommendation Represents

When Genezio runs conversations that simulate users looking for recommendations, the AI engine may or may not recommend your brand.

Examples of being recommended:

* The AI names your brand as a top choice
* The AI lists your brand among its recommended solutions
* The AI suggests your brand as a good fit for the user's specific needs

If the brand is actively recommended in the response, that conversation counts as a **recommendation**.

If the brand is not recommended — even if it's mentioned in passing — it does not count.

---

## How Brand Recommendation Is Calculated

Brand Recommendation is calculated as:

```
Brand Recommendation = (Conversations where the brand is recommended / Conversations where the brand is visible) x 100
```

The denominator is not all conversations — it's only the ones where your brand actually appeared. This means Brand Recommendation measures your **conversion rate from visibility to recommendation**.

Example:

* Conversations where your brand appeared (visible): 74
* Of those, conversations where your brand was recommended: 34

Brand Recommendation:

```
46%
```

This means that when AI engines mention your brand, they recommend it **46% of the time**. The remaining 54% are conversations where your brand appeared but wasn't the suggested choice.

---

## Which Conversations Are Included

Brand Recommendation is measured using conversations where the AI engine **decides which brands to recommend on its own**, based on the user's needs.

The following Genezio Agent types contribute to Brand Recommendation:

### Recommender Agent

Recommender Agent conversations simulate a user asking for recommendations through a multi-step conversation. The AI engine selects which brands to suggest based on the scenario and follow-up constraints.

Example:

> **User query:** ***Recommend CRM tools for early-stage startups with a small sales team.***

---

### Comparer Agent

Comparer Agent conversations ask the AI engine to compare specific brands and often conclude with a recommendation for the user's situation.

Example:

> **User query:** ***Compare HubSpot and Salesforce for a 20-person startup.***

---

### Excluded Agent Types

Some agent types are **excluded** from Brand Recommendation because they don't ask for a recommendation:

**Prompter Agent** — Asks a general discovery question without requesting a specific recommendation.

**Introspector Agent** — Asks about a specific brand directly, so there is no recommendation decision.

---

## Why Brand Recommendation Matters

Brand Recommendation is the closest metric to a **buying decision** in AI search.

When a user asks an AI assistant *"What should I use?"* and the AI recommends your brand, that's the equivalent of a trusted advisor pointing a buyer your way.

A higher recommendation score means:

* AI engines trust your brand as a strong match for users' needs
* Your brand is actively suggested ahead of competitors
* Users who rely on AI for purchase decisions are being directed to you

A lower score means competitors are being recommended instead — and you're losing deals before the buyer even visits your website.

---

## Brand Recommendation vs. Brand Visibility

These two metrics work together but measure different things:

| | Brand Recommendation | Brand Visibility |
| --- | --- | --- |
| **What it measures** | Of the conversations where you're visible, how often are you recommended? | How often your brand appears at all in AI answers |
| **Denominator** | Conversations where brand appeared | All eligible conversations |
| **Which conversations** | Recommender + Comparer | Prompter + Recommender |
| **Why it matters** | Your conversion rate from presence to purchase intent | Measures overall brand presence and awareness |
| **Business analogy** | Conversion rate — of the people who see you, how many choose you | Brand awareness — how many people have heard of you |

A brand can have high visibility (mentioned often) but low recommendation rate (rarely the suggested choice). That gap is your priority — it means AI engines know about you but don't trust you enough to recommend you.

---

## Brand Recommendation Over Time

Genezio tracks Brand Recommendation continuously as new conversations are executed.

This allows teams to observe trends such as:

* increasing recommendations after publishing better comparison content
* competitors gaining or losing recommendation share
* changes in how AI engines evaluate your brand against alternatives

Monitoring recommendations over time helps you see the direct impact of your marketing work on AI-driven purchase decisions.

---

## Next Steps

To understand the broader metric of how often your brand appears in AI answers, see:

* [Brand Visibility](brand-visibility.md)

To see how recommendation rates compare across competitors, see:

* [Insights -> Share of Voice](../insights/share-of-voice.html)
