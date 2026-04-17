---
title: Design tokens
tags: [concept, design-system, frontend, active]
created: 2026-04-17
aliases: [tokens, design-system-tokens]
---

# Design Tokens

> Named, themeable values (colour, spacing, radius, motion) that act as the atoms of a design system.

## Summary

Design tokens are the smallest reusable units of a design system: `color.bg.primary`, `space.4`, `radius.sm`. They separate *intent* ("primary surface") from *value* ("#0A84FF"), so dark mode, brand refreshes, and white-label theming become a token swap instead of a refactor. Tokens live in a platform-agnostic source (JSON or YAML) and compile out to CSS variables, Swift, XML, or anything else the consumers need.

## Key ideas

- **Semantic over raw** — components reference `color.bg.primary`, never `#0A84FF`.
- **Tiers** — global → alias → component-specific; the further down, the more opinionated.
- **One source of truth** — the token file is the contract between design and engineering.
- **Themeable by construction** — changing a theme is changing which values back the aliases.

## Related concepts

- [Component-driven development](./component-driven-development.md) — the consumers of tokens
- [Accessibility first](./accessibility-first.md) — contrast, focus, motion tokens are a11y features in disguise

## Backlinks

- [concepts/component-driven-development.md](./component-driven-development.md)
- [concepts/accessibility-first.md](./accessibility-first.md)
- [tags/design-system.md](../tags/design-system.md)
- [maps/design-system.md](../maps/design-system.md)
