---
title: Component-driven development
tags: [concept, frontend, design-system, active]
created: 2026-04-17
aliases: [CDD, component-first]
---

# Component-Driven Development

> Building UIs bottom-up from small, isolated, independently testable components that compose into pages.

## Summary

Component-driven development (CDD) treats the *component* as the unit of work. You build and document each one in isolation — usually in a workbench like Storybook — then compose them into screens. The payoff is parallel work, visual regression tests that actually catch things, and a design system that can grow without a weekly merge conflict.

## Key ideas

- **Isolation** — a component is developed and viewed outside the app that uses it.
- **Composition over configuration** — small parts combine into bigger parts. Avoid prop bloat.
- **One source of truth for behaviour** — the component, not the page that renders it.
- **Tight feedback loop** — designers and engineers review the same artefact.

## Example

A `<Button>` is implemented, reviewed, and snapshot-tested on its own. Only afterwards does it appear inside a `<CheckoutForm>`, which is itself reviewed on its own before landing on `/checkout`.

## Related concepts

- [Design tokens](./design-tokens.md) — the values components consume
- [Accessibility first](./accessibility-first.md) — a discipline CDD makes easier to enforce
- [Zettelkasten method](./zettelkasten-method.md) — the same "atomic, composable" idea, applied to notes

## Applied in projects

- [Kollektiv Knowledge Base](../projects/kollektiv-knowledge-base.md) — meta-example: the vault itself is built atomically

## Backlinks

- [concepts/design-tokens.md](./design-tokens.md)
- [concepts/accessibility-first.md](./accessibility-first.md)
- [tags/frontend.md](../tags/frontend.md)
- [tags/design-system.md](../tags/design-system.md)
- [maps/frontend.md](../maps/frontend.md)
- [maps/design-system.md](../maps/design-system.md)
