---
title: Design System MOC
tags: [index, moc, design-system]
---

# Design System

> A map of design-system thinking in the vault — the tokens, primitives, and conventions that let design and engineering share one contract.

A design system is *not* a component library. The library is what you can see; the system is the set of agreements — tokens, semantics, governance — that makes the library consistent. The notes here describe those agreements.

## Start here

- [Design tokens](../concepts/design-tokens.md) — the atoms of the system; semantic values that decouple intent from raw CSS
- [Component-driven development](../concepts/component-driven-development.md) — how the system grows in code, one component at a time

## Core concepts

- [Design tokens](../concepts/design-tokens.md) — colour, spacing, radius, motion as named, themeable values
- [Component-driven development](../concepts/component-driven-development.md) — building the library bottom-up
- [Accessibility first](../concepts/accessibility-first.md) — a11y as a property of the primitives, not a retrofit

## The contract, in one paragraph

Tokens are the shared language ("primary surface," "space-4," "motion-fast"). Components consume tokens, never raw values — so a theme change is a token swap. Components are built and reviewed in isolation, accessible by default, and only then composed into pages. Designers and engineers review the same artefact (component, not screenshot) to close the loop.

## Related tags

- [#design-system](../tags/design-system.md)
- [#frontend](../tags/frontend.md)
- [#concept](../tags/concept.md)

## Related maps

- [Frontend](./frontend.md) — where the components live once they exist
- [Knowledge Management](./knowledge-management.md) — meta: the vault itself is a kind of design system for notes

## Open questions

- Where do governance decisions (who can add a token, how do we version) get written down?
- How do we track token adoption — which components still reference raw values?
