# Why do LLM results change?

Because answer engines are not deterministic. The same question asked twice
produces different wording, and sometimes different brands.

That is a property of the medium, not a fault in the measurement.

---

## What causes the variation

**Sampling.** Models generate probabilistically. Two runs of an identical
prompt take different paths.

**Retrieval.** Engines that search before answering may retrieve different
sources on different days, because the web changed or the retriever ranked
differently.

**The engines themselves change.** Models are updated, prompts are tuned,
retrieval is rebuilt. These are not announced, and they can move a whole
category at once.

---

## How to measure anything in a medium that moves

**Read trends, not readings.** A single run is an estimate. A direction over
several runs is a finding. See
[Trend Tracking](../dashboards/trend-tracking.html).

**Keep the questions fixed.** Changing scenarios between runs means you are
measuring two different things. Keep a stable set and change it deliberately.

**Check competitors moved too.** If everyone shifted at once, the engine
changed, not you. This single check prevents most wasted investigations.

**Run enough.** More conversations per topic means less noise per reading.

---

## When a change is real

Sustained over several runs, confined to specific topics rather than
everything, and explicable in the citations: a source appeared or disappeared.
When those three line up, something genuinely changed.
