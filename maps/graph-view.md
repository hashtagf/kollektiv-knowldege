---
title: Graph view
tags: [index, moc, vault-meta]
---

# Graph View

> How to think about this vault as a graph — what counts as a node, what counts as an edge, and why the shape of the graph is the real deliverable.

The vault looks like a folder of markdown files, but the value isn't in any single file. It's in the *graph* of links between them. This note explains the graph's structure, the kinds of nodes and edges that show up, and how to read the graph visualisation in Obsidian (or any tool that renders one).

## Navigate

- [Home](../index.md)
- [Maps of Content](./index.md)
- [Link maintenance](./link-maintenance.md) — the practical counterpart to this note

## What's a node?

Every `.md` file in the vault is a node. Nodes have roles, signalled by the folder they live in:

- **Concept nodes** ([concepts/](../concepts/index.md)) — atomic ideas; leaf-heavy but densely cross-linked
- **Resource nodes** ([resources/](../resources/index.md)) — external sources; usually sinks (few outgoing links, many incoming)
- **Project nodes** ([projects/](../projects/index.md)) — bounded work; link out to the concepts and resources that informed them
- **Person nodes** ([people/](../people/index.md)) — collaborators; usually linked from projects and meetings
- **Hub nodes** — [Maps of Content](./index.md), [folder indexes](../index.md), and [tag pages](../tags/index.md); high-degree nodes whose job is to point at other nodes
- **Template nodes** ([templates/](../templates/index.md)) — structural; ideally orphaned from the content graph

## What's an edge?

Four kinds of links create edges:

1. **Relative markdown links** — `[Title](../folder/note.md)`. Portable across every markdown renderer (GitHub, VS Code, Obsidian). The vault's default.
2. **Wiki-links** — `[[note-filename]]` or `[[note|alias]]`. Obsidian-native; resolve by filename, no path needed.
3. **Tag edges** — `tags: [...]` in frontmatter. Every tag listed in a note's frontmatter is an implicit edge from the note to the tag's page in [tags/](../tags/index.md).
4. **Backlink references** — the `## Backlinks` section at the bottom of a content note. Links are always directional; backlinks make incoming edges explicit because no crawler maintains them for us.

## Reading the graph

In Obsidian's graph view (or any visualiser), three shapes matter:

- **Hubs** — Maps of Content, folder indexes, tag pages. High degree; they're the nodes you land on when you zoom out. [Knowledge Management MOC](./knowledge-management.md), [Frontend MOC](./frontend.md), and the [Tags index](../tags/index.md) should appear as bright central nodes.
- **Clusters** — tight groups of content notes linked to each other and a shared hub. Healthy clusters are a sign the vault has a coherent topic.
- **Orphans** — nodes with zero or one edge. Expected for brand-new notes; a smell for anything older than a week. See [Link maintenance](./link-maintenance.md) for how to catch them.

## Graph anti-patterns

- **Bridges** — a node that's the *only* path between two clusters. Fragile; if the bridge goes stale, both sides lose each other. Fix by adding direct links between the clusters.
- **Star-topology hubs with no cross-links** — every note points at the MOC but not at siblings. The MOC becomes a bottleneck and the siblings don't reinforce each other. Add at least one "related concepts" link to each content note.
- **Ghost edges** — a `[label](./missing.md)` pointing to a file that doesn't exist. Caught by [link maintenance](./link-maintenance.md).

## Why backlink sections exist

Markdown has no native backlink support. Obsidian computes backlinks on the fly; GitHub, VS Code, and most editors don't. Writing `## Backlinks` sections by hand is the small tax we pay to keep the graph legible in any tool. When you link *from* A *to* B, add a reciprocal entry in B's Backlinks list.

See [Link maintenance](./link-maintenance.md) for the procedure that keeps backlink sections honest.

## Related

- [Link maintenance](./link-maintenance.md) — how to check the graph stays healthy
- [Knowledge Management MOC](./knowledge-management.md) — the conceptual backdrop for why the graph matters
- [Tags index](../tags/index.md) — the other axis of connectivity besides links
