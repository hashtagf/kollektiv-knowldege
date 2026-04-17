---
title: Frontend MOC
tags: [index, moc, frontend]
---

# Frontend

> A map of the frontend-engineering territory covered by the vault — components, accessibility, and the patterns that make them compose.

Frontend work here starts from one stance: **build bottom-up, from small parts that are accessible by default.** The notes in this map all circle that stance from a different angle.

## Start here

- [Component-driven development](../concepts/component-driven-development.md) — the process we build UIs with
- [Accessibility first](../concepts/accessibility-first.md) — the default we hold every component to

## Core concepts

- [Component-driven development](../concepts/component-driven-development.md) — isolation, composition, tight feedback loops
- [Accessibility first](../concepts/accessibility-first.md) — keyboard, semantics, primitives
- [Design tokens](../concepts/design-tokens.md) — the values components consume (see also the [Design System MOC](./design-system.md))

## How the concepts connect

- CDD gives you small, isolated components → a11y-first is *affordable* because every component only has to get it right once.
- Tokens make the a11y parts (focus ring width, contrast ratios, motion preferences) values you can theme instead of re-implement.
- Accessibility-first and CDD share the same idea — push correctness to the lowest layer and let composition spread it.

## Related tags

- [#frontend](../tags/frontend.md)
- [#design-system](../tags/design-system.md)
- [#concept](../tags/concept.md)

## Related maps

- [Design System](./design-system.md) — where tokens and primitives live as a discipline of their own
- [Knowledge Management](./knowledge-management.md) — meta: how we capture the frontend thinking above

## Open questions

- Where does testing strategy (visual regression, a11y automation) get its own note?
- How do we capture rendering/perf knowledge without reinventing every browser's docs?
