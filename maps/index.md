---
title: Maps of Content
tags: [index, moc]
---

# Maps of Content

A **Map of Content** (MOC) is a hand-curated hub note for a topic area. It doesn't hold original thinking — it *points* at the notes that do, arranged in an order that tells a story. MOCs grow with the vault: add a note, decide where it fits in the map, link it in.

> **Why MOCs?** Folders force a single parent; tags flatten everything. MOCs sit in between — a pragmatic "here's where to start reading about X" that you write once and revise as understanding shifts.

## Navigate

- [Home](../index.md)
- [Concepts](../concepts/index.md)
- [Projects](../projects/index.md)
- [People](../people/index.md)
- [Resources](../resources/index.md)
- [Tags](../tags/index.md)
- [Templates](../templates/index.md)

## Contents

### Topic MOCs

- [Knowledge Management](./knowledge-management.md) — how we capture, link, and retrieve what we know
- [Frontend](./frontend.md) — components, accessibility, rendering, the browser
- [Design System](./design-system.md) — tokens, primitives, contracts between design and engineering

### Vault-meta notes

- [Graph view](./graph-view.md) — how relationships in the vault are mapped and navigated
- [Link maintenance](./link-maintenance.md) — manual procedures for catching broken links and orphans

## When to write a new MOC

Write one when three or more notes cluster around a topic *and* a newcomer would benefit from a "start here" read-order. Don't pre-build empty MOCs — the map earns its place by having enough terrain to describe.

## MOC skeleton

```markdown
---
title: <Topic> MOC
tags: [index, moc]
---

# <Topic>

> One-sentence framing of what this map covers and why the topic hangs together.

## Start here

- [Most foundational note](./foo.md) — why to read this first

## Core concepts

- [Concept A](../concepts/a.md)
- [Concept B](../concepts/b.md)

## Resources

- [Resource](../resources/r.md)

## Related maps

- [Adjacent MOC](./adjacent.md)
```

## See also

- [Graph view](./graph-view.md) — MOCs become hub nodes in the vault graph
- [Link maintenance](./link-maintenance.md) — MOCs are the first place broken links surface
