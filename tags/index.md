---
title: Tags
tags: [index, tags]
---

# Tags

Every note in the vault declares `tags: [...]` in its frontmatter. This folder mirrors each active tag as its own `.md` file — a hand-curated index of every note that wears that tag. Think of it as the "group by tag" view of the vault, written as plain markdown so it works in Obsidian, GitHub, and any editor.

## Navigate

- [Home](../index.md)
- [Concepts](../concepts/index.md)
- [Projects](../projects/index.md)
- [People](../people/index.md)
- [Resources](../resources/index.md)
- [Maps of Content](../maps/index.md)

## How tags work here

1. Add tags to a note's frontmatter: `tags: [concept, note-taking, active]`.
2. For each tag used, make sure a file exists in this folder: `./note-taking.md`.
3. Add a link to your note inside that tag file's **Notes** section.
4. If the tag is new, copy the structure of an existing tag file (e.g. [concept.md](./concept.md)) as a starter.

Tag files are maintained manually — there is no crawler. That keeps the vault tool-agnostic, and the friction of editing two files keeps tags intentional rather than sprawling.

## Tag taxonomy

Tags cluster into a few rough families. Reuse an existing tag before inventing a new one.

### Content-type tags (what kind of note this is)

- [concept](./concept.md) — ideas, theories, definitions, frameworks
- [project](./project.md) — active or archived projects
- [person](./person.md) — colleagues, stakeholders, contacts
- [resource](./resource.md) — articles, books, external references
- [meeting](./meeting.md) — meeting notes
- [daily](./daily.md) — daily journal entries
- [index](./index-tag.md) — folder indexes and MOCs

### Status tags (where the note sits in its lifecycle)

- [active](./active.md) — currently being worked on or maintained
- [archived](./archived.md) — kept for reference, no longer active
- [draft](./draft.md) — rough notes not ready for linking

### Topic tags (subject-matter clusters — extend as the vault grows)

- [note-taking](./note-taking.md) — note-taking systems and workflows
- [knowledge-management](./knowledge-management.md) — PKM practices
- [frontend](./frontend.md) — frontend engineering topics
- [design-system](./design-system.md) — design-system work

## Add a new tag

1. Create `./<tag-name>.md` — lowercase, hyphen-separated, no spaces.
2. Use this skeleton:

   ```markdown
   ---
   title: Tag — <tag-name>
   tags: [index, tag-page]
   ---

   # #<tag-name>

   > One-sentence description of what this tag covers.

   ## Notes

   - [Note title](../concepts/note-filename.md)

   ## Related tags

   - [related-tag](./related-tag.md)
   ```

3. Link the new tag from the taxonomy above so it's discoverable.

## See also

- [Link maintenance guidelines](../maps/link-maintenance.md) — how to catch broken tag links.
- [Graph view](../maps/graph-view.md) — how tags show up as connective tissue in the vault graph.
