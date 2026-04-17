---
title: Claude Brain
aliases: [claude-brain, second-brain-for-claude]
tags: [idea, product, llm, second-brain, claude]
created: 2026-04-17
status: idea
related: [[LLM Wiki]], [[Second Brain]], [[Obsidian]]
---

# Claude Brain

> [!idea]
> A shared [[Second Brain]] for a team, stored as an [[Obsidian]]-compatible markdown vault, read and written by [[Claude]] as a first-class collaborator.

## Problem

Team knowledge lives in Slack threads, Notion pages, Google Docs, issue comments, and people's heads. When an LLM agent joins the team, it starts cold on every task — context has to be re-gathered from scratch, or hand-fed into the prompt.

Symptoms:

- Agents re-ask questions that were already answered last week.
- Decisions get relitigated because nobody remembers the rationale.
- Good research dies in a chat thread nobody can find.
- Humans and agents can't easily build on each other's work.

## Proposed outcome

A markdown vault — call it **Claude Brain** — where:

- Every durable artifact (decision, research, spec, incident, person, project) is a note.
- [[Claude]] retrieves from it before acting, and writes back after acting.
- Humans read, review, and edit in [[Obsidian]] or any markdown editor.
- Git holds the full history; PRs are the review surface.

Solved looks like: *a new agent session, starting cold, can get caught up on any ongoing project in under a minute by following links from a project note.*

## How it differs from existing tools

| | Notion / Confluence | Slack | Claude Brain |
|---|---|---|---|
| Machine-writable | Limited | No | **Yes (markdown + Git)** |
| Linked graph | Weak | None | **Native `[[wiki-links]]`** |
| Versioned | Shallow | No | **Full Git history** |
| Agent-native | Retrofit | Retrofit | **Designed for it** |
| Human-editable | Good | N/A | **Good (any editor)** |

## Components

- **Vault** — this repository. Markdown + frontmatter + conventional folders.
- **Writer** — [[Claude]] agents with permission to open PRs against the vault.
- **Retriever** — MCP server or tool that exposes search / graph-walk / full-text over the vault.
- **Reviewer** — humans, via normal Git PR review.
- **Hygiene jobs** — scheduled agents that prune stubs, merge duplicates, flag stale notes.

## Guardrails

- Agents write via **PRs**, not direct pushes, until trust is established.
- Sensitive data lives outside the vault; the vault links to it by reference.
- Every agent-authored note carries a `author:` frontmatter field so provenance is clear.
- Humans can always override — the vault is markdown, not a database.

## Near-term experiments

- [ ] Seed the vault with 10–20 existing decisions and research notes to bootstrap the graph.
- [ ] Wire a retrieval tool so Claude can query the vault from any Multica issue.
- [ ] Define the frontmatter schema for the five main note types (concept, project, decision, person, daily).
- [ ] Run a week of "every completed issue produces a note" and measure whether it's sustainable.

## Open questions

- Should the vault be one repo per team, or one shared across the workspace?
- Do we mirror the vault into an embedding index, or stay link-graph-only?
- How opinionated should the folder structure be before it becomes a tax?

## See also

- [[LLM Wiki]] — the broader research context and design principles.
- [[Second Brain]] — Tiago Forte's original framing.
- [[Zettelkasten]] — the atomic-note tradition this borrows from.
