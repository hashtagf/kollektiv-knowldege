---
title: LLM Wiki methodology
tags: [methodology, llm, ai-knowledge-work, knowledge-management, active]
created: 2026-04-17
aliases: [llm-wiki, ai-friendly-wiki]
---

# LLM Wiki Methodology

> A wiki structured so that an LLM (and a human) can both read it well: atomic pages, explicit cross-links, machine-readable frontmatter, and a stable sense of *where one idea ends and the next begins*.

## Summary

A traditional wiki is optimised for **human serendipity** — long pages, prose, in-context digressions. An LLM Wiki is optimised for **machine retrieval** — short pages, predictable structure, links that resolve cleanly, metadata an embedding model can use. The two goals usually align (humans also benefit from cleaner pages), but they diverge in three places: page length, link style, and what belongs in metadata.

Why bother? Because the same vault increasingly serves three readers:

1. **You** browsing in Obsidian.
2. **A teammate** opening it on GitHub.
3. **An LLM** retrieving chunks via RAG, MCP, or tool-use to answer a question.

The third reader has different ergonomics and is the one most easily broken by sloppy structure.

## Key principles

### 1. Atomic pages with stable shape

Every page is *one idea*, with predictable section headers (`Summary`, `Key ideas`, `Example`, `Related`, `Open questions`). The shape lets an LLM:

- Pull just the `Summary` for a 1-line answer.
- Pull `Summary + Key ideas` for a 1-paragraph answer.
- Pull the whole page for an in-depth answer.

This vault's [concept template](../templates/concept-template.md) follows that shape.

### 2. Self-contained pages — no in-context digressions

A page must be readable on its own. Don't write *"as discussed above in the Frontend MOC"* — link to it explicitly. LLMs retrieve in chunks; "above" doesn't exist when the chunk is presented in isolation.

### 3. Explicit, resolvable links

- Use **relative paths** (`../concepts/zettelkasten-method.md`) over wiki-links — they resolve in any markdown renderer and survive being read out of context.
- Link the **first mention** of every other vault concept on the page. Don't make the LLM (or the reader) guess what's a defined term.
- Avoid "click here"; use the destination's title as the link text so retrieval surfaces meaningful anchors.

### 4. Frontmatter as machine metadata

YAML frontmatter is the page's structured metadata layer. Keep it predictable:

```yaml
---
title: ...           # Human-readable name; primary retrieval key
tags: [...]          # Bounded vocabulary (see tags/index.md)
created: YYYY-MM-DD  # ISO date for sorting / freshness
aliases: [...]       # Other names the same idea goes by
---
```

When an embedding model indexes the vault, this metadata becomes part of the searchable surface — undisciplined frontmatter erodes retrieval.

### 5. Bounded tag vocabulary

Tags are *not* free text. We maintain the [tags/](../tags/index.md) folder by hand precisely so the vocabulary stays small. An LLM that asks "what's tagged `methodology`?" needs to find a known answer, not a sprawl of synonyms.

### 6. Define-before-use

Every term that has its own page should be linked at first mention on every page that uses it. This lets a retrieval system follow the link graph one hop further when the user's question is ambiguous.

### 7. Distil aggressively

LLM context windows are finite and embeddings degrade at length. A page distilled per [progressive summarization](./progressive-summarization.md) — with a short executive summary on top — punches above its weight in retrieval.

### 8. Provenance is non-negotiable

Every claim that didn't originate inside the vault gets a link to its [resource](../resources/index.md). LLMs hallucinate confidently; a vault without provenance compounds the problem.

## What an LLM-friendly page looks like

Concretely, this vault's [zettelkasten-method.md](../concepts/zettelkasten-method.md) is the model:

- ~50 lines, focused on one concept
- Predictable headers
- Frontmatter with title, tags, created, aliases
- Backlinks section (so the LLM sees the *inbound* graph from the page itself)
- Open questions (signals what is *not* known)

## What breaks LLM retrieval

| Anti-pattern | Why it breaks retrieval |
|---|---|
| 5,000-word kitchen-sink page | The retrieval chunker slices mid-thought; embeddings lose specificity. |
| Unlabelled section headers (`Other`, `Misc`) | Useless as anchors — the LLM can't tell what's inside. |
| Free-text tags (`#design`, `#designs`, `#designing`) | Tag vocabulary explodes; "find me everything tagged X" stops working. |
| Implicit references ("see the doc Sarah sent") | Nothing to follow. |
| Date-named files (`2026-04-17.md`) **as the only address** | Fine for dailies; broken for evergreens. |
| Markdown without frontmatter | The page has no machine-readable metadata. |

## How this vault implements it

| LLM Wiki principle | Where it lives here |
|---|---|
| Atomic pages | [concepts/](../concepts/index.md), [methodology/](./index.md) |
| Stable shape | [templates/](../templates/index.md) |
| Bounded tags | [tags/](../tags/index.md) — hand-maintained |
| Maps as start-here pages | [maps/](../maps/index.md) |
| Provenance | Every concept ends in `## Sources` linking to [resources/](../resources/index.md) |
| Distillation | [progressive-summarization.md](./progressive-summarization.md) |

## How LLM Wiki differs from a "regular" wiki

- **Regular wiki:** long pages are fine; readers scroll.
- **LLM wiki:** long pages chunk poorly; *split aggressively*.

- **Regular wiki:** tags are folksonomic — anyone adds any tag.
- **LLM wiki:** tags are a controlled vocabulary; new tags are intentional acts.

- **Regular wiki:** "see above" is acceptable.
- **LLM wiki:** every reference is a link, because chunks travel.

## Related

- Methodologies: [Claude Brain methodology](./claude-brain.md), [AI knowledge integration patterns](./ai-knowledge-integration.md), [Second Brain](./second-brain.md)
- Concepts: [Zettelkasten method](../concepts/zettelkasten-method.md), [Evergreen notes](../concepts/evergreen-notes.md)
- Maps: [Methodology MOC](../maps/methodology.md), [Knowledge Management MOC](../maps/knowledge-management.md)
- Vault meta: [Link maintenance](../maps/link-maintenance.md), [Graph view](../maps/graph-view.md)
- Tags: [#llm](../tags/llm.md), [#ai-knowledge-work](../tags/ai-knowledge-work.md), [#methodology](../tags/methodology.md)

## Open questions

- Should each page carry an explicit "intended audience" field (`audience: [human, llm]`) so retrieval can filter on it?
- Where do we draw the line on frontmatter — adding fields hurts readability, omitting them hurts retrieval.
