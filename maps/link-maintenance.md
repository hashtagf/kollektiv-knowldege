---
title: Link maintenance
tags: [index, moc, vault-meta]
---

# Link Maintenance

> Manual procedures for catching broken links, orphaned notes, and stale backlinks in the vault. No crawler — on purpose. The friction is the feature.

This vault is plain markdown. We don't run a link-checker in CI, and we don't have a plugin regenerating backlinks. Link maintenance is a habit, done by hand, and this page is the checklist.

## Navigate

- [Home](../index.md)
- [Maps of Content](./index.md)
- [Graph view](./graph-view.md) — the conceptual counterpart to this note

## When to run this check

- **On every note you touch.** Spot-check its links before committing.
- **Weekly sweep.** Once a week, walk the four checks below end-to-end. 10–15 minutes.
- **Before major reorganisations.** Renaming a folder will break every relative link that crosses into it — catch them the same session.

## Check 1 — Broken outgoing links

Goal: find `[label](./path.md)` references that don't resolve.

1. From the repo root, list every markdown link target:

   ```sh
   grep -r -oE '\]\(\.\.?/[^)]+\.md[^)]*\)' . \
     | sed -E 's/.*\((.+)\)/\1/' \
     | sort -u
   ```

2. Spot-check each path: does the file exist? Easiest way — open the file in Obsidian or VS Code and click the link. A broken link is rendered differently (Obsidian shows a red/unresolved style; VS Code fails to navigate).
3. Fix by either:
   - Creating the missing file (if the link represents real intent), or
   - Updating the link to point somewhere real, or
   - Deleting the link if the reference is no longer relevant.

### A lighter alternative

If grep feels heavy, just open the folder index (e.g. [concepts/index.md](../concepts/index.md)) and click each link. Indexes are the highest-traffic pages and catch the majority of breakage.

## Check 2 — Orphaned notes

Goal: find content notes that no other note links to. An orphan is either a brand-new note (fine) or a forgotten one (a smell).

1. For a suspect note, grep for its filename across the vault:

   ```sh
   grep -r "zettelkasten-method" --include="*.md" .
   ```

2. Results should include at least:
   - The folder index (e.g. [concepts/index.md](../concepts/index.md))
   - One relevant tag page in [tags/](../tags/index.md)
   - One MOC in [maps/](./index.md), if the topic has one
   - At least one peer content note
3. If it's missing from the folder index, add it. If it's missing from every tag page and every MOC, either link it in or archive it.

## Check 3 — Stale backlinks

Goal: the `## Backlinks` section of every content note should match reality.

Backlinks are maintained by hand — when you add a link *from* A *to* B, you also add a reciprocal entry in B's Backlinks section. That step gets forgotten. To catch the drift:

1. Pick a content note (say, [concepts/zettelkasten-method.md](../concepts/zettelkasten-method.md)).
2. Grep for incoming links:

   ```sh
   grep -r "zettelkasten-method.md" --include="*.md" .
   ```

3. Compare the grep result to the note's `## Backlinks` section. Add any missing entries; remove entries that no longer exist.

Cadence: do this for 3–5 notes per weekly sweep, not all of them. Over a few weeks the whole vault rotates through.

## Check 4 — Tag consistency

Goal: every tag used in frontmatter has a page in [tags/](../tags/index.md), and every tag page appears on at least one note.

1. Collect every tag used across the vault:

   ```sh
   grep -r "^tags:" --include="*.md" . | tr ',' '\n' | sed -E 's/.*\[|\].*//g' | sort -u
   ```

2. For each tag, check that `tags/<tag>.md` exists. If not, create it using the skeleton in [tags/index.md](../tags/index.md).
3. Open each tag page; verify its **Notes** section lists at least one note. Empty tag pages either get a note added or get deleted.

## When you rename a file

Renaming breaks every incoming link. Before renaming:

1. Run Check 2 (grep for the old filename) to find every inbound link.
2. Rename the file.
3. Update each inbound reference — including folder index, tag pages, MOCs, and `## Backlinks` sections of linked notes.
4. Commit the rename and the link updates in a single commit so reviewers can verify nothing was missed.

## When you delete a file

1. Run Check 2 to find inbound links.
2. Decide per-link whether to delete the reference, redirect it, or replace it with a short note saying the content moved.
3. Don't leave dangling references.

## Automation boundary

The vault is deliberately tool-agnostic. We can add a CI link-checker later (`markdown-link-check` or similar) *if* manual upkeep becomes a burden, but the first-order fix when the vault gets noisy is usually to write fewer, better notes rather than to add tooling. Adopt automation only when you've run the manual sweep three weeks in a row and still miss things.

## Related

- [Graph view](./graph-view.md) — what a healthy link graph looks like
- [Tags index](../tags/index.md) — the tag system this maintenance supports
- [Maps of Content](./index.md) — hubs that surface link breakage first
