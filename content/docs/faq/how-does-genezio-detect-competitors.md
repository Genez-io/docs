# How does Genezio detect competitors?

From the answers themselves. Genezio reads every conversation for brands named
as alternatives to you, and collects them across runs.

See [Extracting Competitors](../analysis/extracting-competitors.html) for the
mechanics.

---

## Why not just use a list?

You can — competitors you add are tracked regardless. But a list alone would
miss the useful part.

The brands an answer engine puts beside you are not always the ones you compete
with commercially. Engines surface brands by how well sources support them, so
the list often contains a name your sales team would not recognise.

That is a finding, not an error. A brand that exists in AI answers today tends
to show up in deals later.

---

## Why does a brand appear that is not a competitor?

Three common causes:

- **Adjacent categories.** An engine answering broadly may name tools that
  solve a neighbouring problem.
- **Parent or sibling brands.** A product named alongside its own parent
  company.
- **Name collisions.** A brand whose name is also a common word gets
  over-counted.

Remove these. They distort
[Share of Voice](../dashboards/share-of-voice.html), which divides the
conversation among whoever is on the list.

---

## How often should the list be reviewed?

Quarterly is enough for most categories. The set of brands engines treat as
alternatives drifts, and a list fixed at setup slowly stops describing the
market you are actually in.
