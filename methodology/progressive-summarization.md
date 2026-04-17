---
title: Progressive summarization
tags: [methodology, second-brain, knowledge-management, active]
created: 2026-04-17
aliases: [progressive-summary, layered-highlights]
---

# Progressive Summarization

> Distil a captured note in **layers** so future-you can grasp it at any zoom level — full text, bolded sentences, highlighted essentials, or a one-paragraph executive summary.

## Summary

Progressive summarization is the *Distil* stage of the [CODE method](./code-method.md). It assumes you'll re-encounter a note many times in many states of attention — sometimes you have 30 seconds, sometimes 30 minutes — and a well-distilled note serves all of them. Instead of re-summarising from scratch each visit, you add a *layer* each time: bolds, then highlights, then an executive summary, then (optionally) a remix.

The key discipline is **lazy distillation** — you add a layer only when re-reading the note for an actual purpose, not pre-emptively. That way the layers concentrate on the parts that have proved useful, not on the parts that *seemed* important when you first captured them.

## The five layers

| Layer | What it is | When to add it |
|---|---|---|
| 1. Captured text | Source material as you saved it | At capture |
| 2. **Bold** | The load-bearing sentences | First re-read with intent |
| 3. ==Highlight== of bolds | The essentials *within* the bolds | Second re-read with intent |
| 4. Executive summary | 1–3 sentences at the top of the note | When the note will inform output |
| 5. Remix | Reworded into your own framing — a new evergreen note | When you reach for it from a project |

> Convention in this vault: layer 3 uses Obsidian's `==highlight==` syntax. GitHub renders it as plain text but Obsidian shows it highlighted; either way, the layering survives.

## A worked example

### Layer 1 — captured

```markdown
The trick is not to capture more, but to capture less and surface
it better. Most knowledge bases die not from too few notes but from
too many low-resonance ones. The discipline is selectivity at the
moment of capture, and lazy summarisation afterwards. You should be
able to re-find the gist of any note in about five seconds, regardless
of when you wrote it.
```

### Layer 2 — bolds

```markdown
The trick is not to capture more, but to capture less and surface
it better. **Most knowledge bases die not from too few notes but
from too many low-resonance ones.** The discipline is **selectivity
at the moment of capture, and lazy summarisation afterwards**. You
should be able to **re-find the gist of any note in about five
seconds, regardless of when you wrote it.**
```

### Layer 3 — highlight of bolds

```markdown
The trick is not to capture more, but to capture less and surface
it better. **Most knowledge bases die not from too few notes but
from too many ==low-resonance ones==.** The discipline is
**==selectivity at the moment of capture==, and ==lazy summarisation==
afterwards.** You should be able to **re-find the gist of any note
in about ==five seconds==, regardless of when you wrote it.**
```

### Layer 4 — executive summary (added at top)

```markdown
> **TL;DR:** PKM systems fail from low-resonance noise, not too few
> notes. Capture selectively; distil lazily; aim for 5-second
> re-comprehension.
```

### Layer 5 — remix (a new evergreen note that cites the source)

A new file like `concepts/resonance-as-capture-filter.md`:

```markdown
# Resonance as a capture filter

A capture decision is a **bet on future-you's attention**. Filter at
the source, not at retrieval — the cheapest layer to skip is the one
that never enters the vault.

Source: [progressive-summarization.md](../methodology/progressive-summarization.md)
```

## A second example — distilling a meeting note

### Layer 1

```markdown
Discussion on the design-system v2 cutover. Tom worried about the
Storybook migration timeline. Priya pointed out that the consumer
of the design system is the marketing site team, who release on a
two-week cadence — so any breakage there blocks marketing for two
weeks at minimum. Decision: phase the cutover by component family,
not in one big-bang release. Owner: Priya. Target: end of Q3.
```

### Layer 2 — bolds

```markdown
Discussion on the design-system v2 cutover. Tom worried about the
Storybook migration timeline. Priya pointed out that **the consumer
of the design system is the marketing site team, who release on a
two-week cadence — so any breakage there blocks marketing for two
weeks at minimum.** **Decision: phase the cutover by component
family, not in one big-bang release.** Owner: Priya. Target: end of Q3.
```

### Layer 3 — highlight

```markdown
Priya pointed out that **the consumer of the design system is the
==marketing site team==, who release on a ==two-week cadence== — so
any breakage there blocks marketing for ==two weeks== minimum.**
**Decision: ==phase the cutover by component family==, not in one
big-bang release.**
```

### Layer 4 — executive summary

```markdown
> **TL;DR:** Marketing's two-week release cadence makes any DS v2
> breakage costly. Decision: phased cutover by component family,
> Priya owning, end of Q3.
```

### Layer 5 — remix

The reasoning extracts as an evergreen in [concepts/](../concepts/index.md):

```markdown
# Phased cutovers when consumer release cadence is slow

When a downstream consumer ships on a long cadence, a big-bang
release amortises poorly: a single bug freezes them for the full
cadence. Phase the cutover at the granularity that matches their
release unit (per component, per route).

Source: meeting note 2026-04-17 — design-system v2 cutover
```

## Rules of thumb

- **Bold sparingly.** If half the paragraph is bold, the bolds aren't doing work. Aim for ~10–20% of the text.
- **Don't add a layer "just to be thorough."** Each layer should answer a question you actually have.
- **Remix is the goal.** Layers 2–4 are scaffolding for layer 5 — the new evergreen note that lives in [concepts/](../concepts/index.md).
- **Cite back.** A remix without a backlink to its source loses its provenance.

## Apply it in this vault

- Use the [progressive-summary template](../templates/progressive-summary-template.md) when distilling a long [resource](../resources/index.md).
- Distil during the [weekly review](./daily-weekly-review.md), not in the moment of capture.
- A fully-distilled remix usually graduates from `resources/` to [concepts/](../concepts/index.md) as an [evergreen note](../concepts/evergreen-notes.md).

## Related

- Methodologies: [Second Brain](./second-brain.md), [CODE method](./code-method.md), [Knowledge capture workflow](./knowledge-capture-workflow.md)
- Concepts: [Evergreen notes](../concepts/evergreen-notes.md), [Zettelkasten method](../concepts/zettelkasten-method.md)
- Templates: [Progressive summary template](../templates/progressive-summary-template.md), [Knowledge capture template](../templates/knowledge-capture-template.md)
- Maps: [Methodology MOC](../maps/methodology.md), [Knowledge Management MOC](../maps/knowledge-management.md)
- Tags: [#second-brain](../tags/second-brain.md), [#methodology](../tags/methodology.md), [#knowledge-management](../tags/knowledge-management.md)

## Open questions

- Should layer 3 highlights survive into the remix, or get stripped?
- For LLM-consumed notes (see [LLM Wiki methodology](./llm-wiki.md)), is the executive summary worth more than the bolds?
