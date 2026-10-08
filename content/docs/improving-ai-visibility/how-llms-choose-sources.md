# How LLMs Choose Sources

An answer engine answering a question about your category is doing retrieval
before generation: finding material, judging it, and composing from what it
trusts. Understanding that order explains most of what you can do about it.

---

## What gets retrieved

Retrieval matches on substance, not on brand. A page is found because it
contains the vocabulary of the question and answers it directly — see
[Query Fanouts](../core-concepts/query-fanouts.html).

This is why a smaller brand with one genuinely useful page can outrank a large
one with none.

---

## What gets trusted

Of what is retrieved, engines prefer sources that look like evidence:

- **Independent beats self-published.** A brand describing itself is weak
  evidence. A third party describing it is stronger. This is the single
  largest factor most teams underuse.
- **Specific beats general.** A page answering one question thoroughly beats a
  page touching twenty.
- **Consistent beats contradictory.** When sources disagree about you, engines
  hedge or pick the one with more support.

---

## What gets quoted

Engines lift passages. A page can be retrieved and trusted and still contribute
nothing, because no paragraph stands alone as an answer.

This is the most common and most fixable failure. See
[Structuring Content for LLMs](structuring-content-for-llms.html).

---

## What this means for you

In order of leverage:

1. **Be quotable** on questions you already rank for.
2. **Earn independent mentions** where buyers already look.
3. **Cover the questions you are absent from**, chosen by commercial value.
4. **Keep your facts consistent** everywhere they appear.

There is no submission, no ranking factor to game and nobody to appeal to. The
work is being the best available source for a question.
