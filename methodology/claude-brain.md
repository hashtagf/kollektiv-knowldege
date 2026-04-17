---
title: Claude Brain methodology
tags: [methodology, claude, ai-knowledge-work, knowledge-management, active]
created: 2026-04-17
aliases: [claude-brain, claude-md-system, agent-memory]
---

# Claude Brain Methodology

> Treat Claude as a long-running collaborator, not a stateless chatbot. Build the knowledge artifacts — `CLAUDE.md`, skills, memory files, plans — that give it continuity across sessions and a shared model of *how this team works*.

## Summary

A "Claude Brain" is the set of persistent, version-controlled artifacts that travel with a project so that any Claude session — agent, IDE plugin, CLI — picks up where the last one left off. The methodology is a direct application of [Second Brain](./second-brain.md) and [LLM Wiki](./llm-wiki.md) ideas to a *non-human* reader: capture once, organise by actionability, distil progressively, express through structured outputs.

The unit of value isn't a transcript — it's the **artifact the next session will read first**.

## The four artifact layers

### 1. Project memory — `CLAUDE.md`

A file (or set of files) at the root of a project that Claude reads at the start of every session. Contains:

- The project's *purpose* and constraints
- Conventions Claude should follow (filenames, commit style, test runner)
- The handoff protocols (for agent projects — see the team's autonomous playbook)
- Pointers to deeper docs

This is the **always-on context**. Keep it short. Anything that doesn't change session-to-session belongs here; ephemeral state does not.

### 2. Skills — repeatable procedures

A skill is a structured prompt + instructions for *how to do a recurring task*: review a PR, run a sprint plan, audit a CLAUDE.md, set up Sentry. Skills sit in a known directory (e.g. `.claude/skills/` or `.agents/skills/`) and are loaded on demand.

The Claude Brain pattern: when you find yourself explaining the same procedure twice, write a skill. Skills are the *Express* output of CODE for the agent itself.

### 3. Agent memory — long-running context per role

For multi-agent setups, each role has a memory file (`agents/memory/{role}.md`) that captures *what this role learned across sessions*. This is the agent equivalent of Claude Code's auto-memory system: facts that should survive context resets.

Contents typically:

- **User profile** — who the human is, how they work
- **Feedback** — corrections and confirmed patterns
- **Project state** — what shipped, what's open, who owns what
- **References** — where external systems live (Linear, Slack channels, dashboards)

### 4. The vault itself — your existing knowledge base

Everything in [concepts/](../concepts/index.md), [methodology/](./index.md), [maps/](../maps/index.md). The Claude Brain treats the vault as **retrievable context** — Claude reads notes the same way a teammate would, follows the same links, and contributes back as a peer (writing notes, updating MOCs, distilling resources).

## The CODE workflow, applied to working with Claude

| Stage | What it looks like with Claude |
|---|---|
| **Capture** | Drop interesting prompts, transcripts, and patterns into a scratch file or daily note. Don't curate yet. |
| **Organise** | At the [weekly review](./daily-weekly-review.md), promote useful patterns into either a *skill* (for procedures) or a *concept note* (for ideas). |
| **Distil** | Apply [progressive summarization](./progressive-summarization.md) — bold the load-bearing instructions, write a 1-paragraph TL;DR at the top of each skill. |
| **Express** | The skill gets used in a real Claude session; the concept gets cited in a PRD. The artifact earns its keep by *being run*. |

## Conventions for Claude-readable artifacts

These are the *operational* form of [LLM Wiki methodology](./llm-wiki.md):

1. **Frontmatter on everything** — `title`, `tags`, `created`. Skills add `description` so they're discoverable.
2. **Imperative voice in skills** — "Read X, then run Y" beats "X is read and Y is run."
3. **Explicit triggers** — every skill begins with *when to use this skill*, so Claude can self-route.
4. **Bounded tag vocabulary** — see [tags/](../tags/index.md). New tags are intentional.
5. **Resolvable links** — relative paths over wiki-links. Chunks travel; "above" doesn't.
6. **One concept per file** — splits make retrieval precise. (See [evergreen notes](../concepts/evergreen-notes.md).)
7. **Provenance** — when a skill encodes a decision, link to the meeting note, ADR, or resource that set it.

## Where it shows up in this vault / project

| Artifact | Location |
|---|---|
| Project-wide instructions | `CLAUDE.md` at repo root |
| Role playbooks | `.agent_context/skills/playbook-*.md` |
| Issue context | `.agent_context/issue_context.md` |
| Project state | `.agent_context/project_state.md` |
| Dependencies | `.agent_context/dependencies.md` |
| Concept notes (evergreen) | [concepts/](../concepts/index.md) |
| Methodologies (workflows) | [methodology/](./index.md) |
| Templates | [templates/](../templates/index.md) |

## What "good" looks like

A new Claude session in this repo can:

1. Read `CLAUDE.md` → know who it is and how to commit.
2. Read its role's playbook → know its handoff protocol.
3. Read `.agent_context/issue_context.md` → know what task to run.
4. Read `.agent_context/project_state.md` → know what siblings shipped.
5. Read `.agent_context/dependencies.md` → know what to reuse.
6. Read [methodology/index.md](./index.md) and the relevant MOC → know how the team thinks.

If any of those reads requires *asking the human a question to understand*, the brain has a gap. Patch the gap with a doc, not a longer prompt.

## Common failure modes

- **Stale memory.** A memory file claims a function exists; it was renamed last week. Fix: verify before recommending; treat memory as *context as of when written*, not ground truth.
- **CLAUDE.md as a junk drawer.** Every preference, every policy, dumped into one file. Fix: split into `CLAUDE.md` (always-on) and skills (on-demand).
- **Skills with no trigger condition.** Claude doesn't know when to invoke them. Fix: every skill's first line is "*When to use this skill: ...*".
- **Vault-and-CLAUDE.md drift.** Conventions in `CLAUDE.md` contradict the vault's [README](../README.md). Fix: link from one to the other; don't restate.

## Related

- Methodologies: [Second Brain](./second-brain.md), [LLM Wiki](./llm-wiki.md), [AI knowledge integration patterns](./ai-knowledge-integration.md)
- Concepts: [Evergreen notes](../concepts/evergreen-notes.md), [Zettelkasten method](../concepts/zettelkasten-method.md)
- Maps: [Methodology MOC](../maps/methodology.md), [Knowledge Management MOC](../maps/knowledge-management.md)
- Tags: [#claude](../tags/claude.md), [#ai-knowledge-work](../tags/ai-knowledge-work.md), [#methodology](../tags/methodology.md)

## Open questions

- How do we keep agent memory from drifting out of sync with the vault — write it twice, or pick one as source of truth?
- When a skill is *almost* what's needed, should Claude edit it, fork it, or compose two existing skills?
