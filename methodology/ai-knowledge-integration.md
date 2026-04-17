---
title: AI knowledge integration patterns
tags: [methodology, llm, claude, ai-knowledge-work, knowledge-management, active]
created: 2026-04-17
aliases: [ai-integration, llm-integration-patterns, rag-patterns]
---

# AI Knowledge Integration Patterns

> The patterns we use to integrate this knowledge base with LLM-powered workflows — so the vault isn't just a place humans read, it's an active substrate for AI-assisted thinking, drafting, and decision-making.

## Summary

If [Second Brain](./second-brain.md) is the workflow and the [LLM Wiki](./llm-wiki.md) is the structural form, this note is the **integration layer** — the recurring patterns for plugging the vault into LLM-driven work. They build on the [Claude Brain methodology](./claude-brain.md) but apply to any LLM (Claude, GPT, local models) and any retrieval mechanism (RAG, MCP, tool-use, manual paste).

The patterns are arranged by *who initiates the read*: a human asking the LLM, an agent acting autonomously, or the LLM contributing back into the vault.

## Pattern catalogue

### A. Human-initiated patterns

#### A1 — Context Pack

The human selects a handful of vault notes (a MOC + 2–3 concepts) and pastes them into the LLM as the working context for a session.

- **When:** drafting, brainstorming, ad-hoc research where retrieval quality matters more than recall.
- **Vault assets used:** [MOCs](../maps/index.md), [evergreen concepts](../concepts/index.md).
- **Why it works:** the human curates what's relevant; the LLM reasons over a small, high-signal set.
- **Anti-pattern:** pasting the whole vault. Token waste, attention dilution.

#### A2 — Distillation Pair

The human captures a long source ([resource](../resources/index.md)), and the LLM produces a [progressive summarization](./progressive-summarization.md) draft (executive summary + bolded essentials). The human edits before merging.

- **When:** clearing a backlog of long captures during the [weekly review](./daily-weekly-review.md).
- **Vault assets used:** [progressive-summary template](../templates/progressive-summary-template.md).
- **Why it works:** distillation is mechanical enough for the LLM, judgement-loaded enough that the human still owns the merge.
- **Anti-pattern:** auto-merge. The point of distillation is the human's judgement about what *resonates*; an unreviewed AI summary is just a longer source.

#### A3 — Concept Extraction

While reading a long note with the LLM, ask "*what are the three load-bearing ideas worth their own concept notes?*" Each candidate becomes a draft for [concepts/](../concepts/index.md), which the human reviews and edits.

- **When:** a [resource](../resources/index.md) is too dense to leave un-distilled.
- **Vault assets used:** [concept template](../templates/concept-template.md).
- **Why it works:** the LLM is good at "find the atomic ideas"; the human is good at "is this idea worth a permanent home?"

### B. Agent-initiated patterns

#### B1 — Self-Context Bootstrap

A new agent session reads, in order: `CLAUDE.md` → role playbook → `.agent_context/issue_context.md` → `.agent_context/project_state.md` → `.agent_context/dependencies.md` → relevant [methodology/](./index.md) docs. No human prompt required.

- **When:** every agent session start. See [Claude Brain methodology](./claude-brain.md).
- **Vault assets used:** all of `.agent_context/`, [methodology/index.md](./index.md).
- **Why it works:** the agent walks the same documented entry path every time, so its first decisions are grounded in *what was true last session*.

#### B2 — MOC-First Retrieval

Before pulling individual notes, the agent reads the relevant [MOC](../maps/index.md) to scope what's available. Only then does it deep-read individual concepts.

- **When:** the question spans a topic, not a single concept.
- **Vault assets used:** [maps/](../maps/index.md).
- **Why it works:** MOCs are hand-curated read-orders. They're more reliable than embedding similarity for "what should I read first?"

#### B3 — Provenance Verification

Before acting on a remembered fact, the agent verifies it against the vault or git state.

- **When:** the agent is about to recommend a file, function, flag, or decision.
- **Vault assets used:** the live filesystem; `git log`.
- **Why it works:** memory is a snapshot in time; the vault is the source of truth.
- **Anti-pattern:** "the memory says X exists" is treated as proof. It isn't.

### C. LLM-contributed patterns (write-back)

#### C1 — Distilled Capture

The LLM, asked to summarise a meeting or thread, produces a note in the [knowledge capture template](../templates/knowledge-capture-template.md) shape — frontmatter, summary, key ideas, action items — and the human commits it.

- **When:** post-meeting, post-thread, post-call.
- **Vault assets used:** [templates/](../templates/index.md).
- **Why it works:** the LLM does the structural lift; the human owns the judgement about what to keep.

#### C2 — Backlink Maintenance

The LLM scans for orphaned notes, broken links, and missing backlinks (per [link maintenance](../maps/link-maintenance.md)) and proposes a patch.

- **When:** monthly review, after a folder restructure, after a batch import.
- **Vault assets used:** [maps/link-maintenance.md](../maps/link-maintenance.md), the link graph.
- **Why it works:** mechanical, exhaustive, easy to verify in a diff.

#### C3 — Skill Extraction

When the LLM has just walked through a recurring procedure, ask "*write this as a skill*." The output is a candidate file for the team's skill library.

- **When:** you find yourself explaining the same procedure twice.
- **Vault assets used:** the skill format from [Claude Brain methodology](./claude-brain.md).
- **Why it works:** the procedure is freshest right after running it; the LLM has the trace in context.

### D. Cross-cutting patterns

#### D1 — Frontmatter as Filter

Use frontmatter (`tags`, `aliases`, `created`) as the primary filter when querying the vault — both for humans and for retrieval pipelines. A bounded vocabulary makes "find everything tagged `methodology`" reliable.

- **Vault enforcement:** the [tags/](../tags/index.md) folder is hand-maintained for exactly this reason.

#### D2 — Two-Reader Editing

When editing any note, imagine two readers: a human teammate and a future LLM session. If the page is hard for either, fix it. Most edits that help one help the other.

- **Tension cases:** in-jokes (good for human, opaque to LLM); rigid templated structure (good for LLM, can feel sterile to human). Optimise for the LLM and let the human warmth come from prose, not structure.

#### D3 — Citation Round-Trip

When the LLM uses a vault note to answer a question, the answer should cite the note path. When a vault note is sourced from an LLM session, it should cite the prompt or transcript. Closed loop.

## Choosing the right pattern

| If you're trying to... | Use |
|---|---|
| Get an LLM to draft a doc with vault context | A1 Context Pack |
| Clear a backlog of long captures | A2 Distillation Pair |
| Spin atomic concepts out of a long source | A3 Concept Extraction |
| Bootstrap an agent for autonomous work | B1 Self-Context Bootstrap |
| Answer a topic-spanning question | B2 MOC-First Retrieval |
| Avoid acting on stale memory | B3 Provenance Verification |
| Capture a meeting with structure | C1 Distilled Capture |
| Repair link rot | C2 Backlink Maintenance |
| Codify a recurring procedure | C3 Skill Extraction |

## Failure modes

- **Pattern soup.** Mixing patterns mid-session (start as a Context Pack, drift into Concept Extraction, never finish either). Pick one per session; finish it.
- **Skip provenance.** Once an LLM-generated draft is merged without a citation, the vault loses the chain of custody. Always cite back.
- **No human in the merge loop.** Auto-committing LLM output erodes the *resonance filter* that makes Second Brain work — the vault fills with plausible noise.
- **MOC bypass.** Retrieving by embedding similarity alone, ignoring the curated MOC, misses the team's hand-built read-order.

## Related

- Methodologies: [Second Brain](./second-brain.md), [LLM Wiki](./llm-wiki.md), [Claude Brain](./claude-brain.md), [Progressive summarization](./progressive-summarization.md), [Knowledge capture workflow](./knowledge-capture-workflow.md)
- Concepts: [Evergreen notes](../concepts/evergreen-notes.md), [Zettelkasten method](../concepts/zettelkasten-method.md)
- Templates: [Knowledge capture template](../templates/knowledge-capture-template.md), [Progressive summary template](../templates/progressive-summary-template.md)
- Maps: [Methodology MOC](../maps/methodology.md), [Knowledge Management MOC](../maps/knowledge-management.md), [Link maintenance](../maps/link-maintenance.md)
- Tags: [#ai-knowledge-work](../tags/ai-knowledge-work.md), [#llm](../tags/llm.md), [#claude](../tags/claude.md), [#methodology](../tags/methodology.md)

## Open questions

- Should agents write directly to the vault, or always via a PR a human reviews?
- How do we measure pattern adoption — count `[ASK_AGENT]` and `[HANDOFF]` blocks across sessions?
