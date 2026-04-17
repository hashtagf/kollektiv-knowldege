---
title: Accessibility first
tags: [concept, frontend, active]
created: 2026-04-17
aliases: [a11y-first, shift-left-a11y]
---

# Accessibility First

> Treat accessibility as a default in every component from the first commit, rather than a retrofit at audit time.

## Summary

"Accessibility first" is the frontend discipline of building every component with keyboard, screen-reader, and reduced-motion support in place from day one. Audit-driven a11y tends to surface dozens of the same issue across a codebase; a11y-first closes them at the primitive level — so every consumer of `<Button>` inherits focus rings, an accessible name, and an appropriate role for free.

## Key ideas

- **Primitive-level a11y** — bake semantics into the lowest component layer and let composition spread it.
- **Keyboard before mouse** — verify every interaction with the keyboard before you care about hover states.
- **Announce the right thing** — screen readers read what you expose, not what you think.
- **Automated + manual** — axe catches ~30% of issues; the other 70% need a human on a screen reader.

## Related concepts

- [Component-driven development](./component-driven-development.md) — the process that makes a11y-first affordable
- [Design tokens](./design-tokens.md) — tokens for focus rings, contrast ratios, motion preferences

## Backlinks

- [concepts/component-driven-development.md](./component-driven-development.md)
- [tags/frontend.md](../tags/frontend.md)
- [maps/frontend.md](../maps/frontend.md)
