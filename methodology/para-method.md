---
title: PARA method
tags: [methodology, second-brain, para, knowledge-management, active]
created: 2026-04-17
aliases: [para, projects-areas-resources-archive]
---

# PARA Method

> Organise *everything* — notes, files, tasks — into four buckets, defined by **how actionable** the content is rather than what it's about: **P**rojects · **A**reas · **R**esources · **A**rchive.

## Summary

PARA is the storage half of [Second Brain](./second-brain.md). It rejects topic-based folders ("design", "marketing", "engineering") because the same note often has to support multiple topics. Instead, every item lands in one of four buckets sorted by *time horizon and commitment*. When a project ends, its folder collapses straight into Archive; when a long-running area generates a fresh deliverable, Project folders spin out from it.

## The four buckets

### P — Projects (`projects/`)

> A series of tasks linked to a goal, with a **deadline** and a **defined end state**.

- *Examples:* "Ship knowledge-base v1", "Run Q2 product roadmap workshop", "Migrate auth service to v2".
- *Lives in this vault:* [projects/](../projects/index.md). One folder per project, with a `PRD.md` for product work.
- *Lifecycle:* Created from an Area or a Founder request → drives most weekly work → moves to Archive when shipped.

### A — Areas (`areas/`)

> A sphere of activity with a **standard to maintain** over time, no fixed end date.

- *Examples:* "Engineering hiring", "Vault upkeep", "Personal health", "Customer support quality".
- *Lives in this vault:* `areas/` (created lazily — only when an area gathers enough notes to need its own home; until then, area material sits inside the relevant [MOC](../maps/index.md)).
- *Difference from a Project:* you never "finish" Vault upkeep — but you *do* finish "Add methodology folder to vault."

### R — Resources (`resources/`)

> Topics or themes of **ongoing interest** — reference material that may inform a future project, not tied to current work.

- *Examples:* an article on accessibility patterns, a book summary, a Figma tutorial, a vendor evaluation doc.
- *Lives in this vault:* [resources/](../resources/index.md).
- *Test:* "If I lost this, would I re-look for it?" If yes, it's a Resource. If "probably never read again," it's a candidate for Archive — or for not capturing in the first place.

### A — Archive (`archive/`)

> Anything from the other three buckets that's **inactive but worth keeping** for reference.

- *Examples:* shipped projects, abandoned areas, resources tied to a project that's now done, deprecated workflows.
- *Lives in this vault:* `archive/` (created when first thing is moved in — kept lean to make the active vault scannable).
- *Lifecycle:* Archive is *append-only* in practice; you re-activate by moving items back out, not by editing in place.

## How PARA maps onto our existing folders

This vault was built [zettelkasten-style](../concepts/zettelkasten-method.md) before PARA was introduced, so the mapping is hybrid:

| PARA bucket | Folder(s) here | Notes |
|---|---|---|
| Projects | [projects/](../projects/index.md) | 1:1 mapping. |
| Areas | (lazy) `areas/`, plus thematic [MOCs](../maps/index.md) | We let an area live inside a MOC until it earns its own folder. |
| Resources | [resources/](../resources/index.md) | 1:1 mapping. |
| Archive | (lazy) `archive/` | Created only when the first thing needs archiving. |
| **Atoms (concepts)** | [concepts/](../concepts/index.md) | PARA doesn't model atomic concepts — we keep [evergreen notes](../concepts/evergreen-notes.md) in their own folder so they can be linked freely from any bucket. |
| **People** | [people/](../people/index.md) | Cross-cutting; not a PARA bucket but linked from all of them. |

The difference from "pure" PARA is the [concepts/](../concepts/index.md) folder. PARA optimises for *retrieval by project*; zettelkasten optimises for *retrieval by idea*. Keeping concepts as their own bucket lets us serve both.

## Decision rules

When a new note lands, ask in this order:

1. **Is it tied to a deliverable with a deadline?** → `projects/<project-name>/`
2. **Is it part of a standard you maintain ongoing?** → `areas/<area-name>/` (create the folder if needed)
3. **Is it general reference you might pull on later?** → `resources/`
4. **Was it once active and is now done / dropped?** → `archive/`
5. **Is it a single, link-worthy idea regardless of any of the above?** → also create a [concept note](../concepts/index.md) and link it from wherever it's relevant.

## Maintenance moves

- **Project ships** → move folder into `archive/` and update [projects/index.md](../projects/index.md).
- **Project re-opens** → move it back; don't fork.
- **Area outgrows a MOC** → spin a folder under `areas/` and update [maps/index.md](../maps/index.md).
- **Resource gets used in a project** → leave it in `resources/`, but link it from the project. Don't duplicate.
- **Capture is "interesting but no home"** → goes to `resources/` with a 2-line "why I kept this" note, or doesn't get captured.

The [weekly review](./daily-weekly-review.md) is where most of these moves happen.

## Common mistakes

- **Folder-by-topic creep.** A `frontend/` folder sounds tidy but breaks PARA — frontend stuff lives in *whichever bucket the artifact serves*. Use [tags](../tags/index.md) and [MOCs](../maps/index.md) for topical access.
- **Keeping shipped projects in `projects/`** because "we might revisit them." That's what Archive is for; cluttering Projects masks what's *actually* active.
- **Dumping into Resources.** If you can't write a 2-line "why I kept this," don't keep it.

## Related

- Methodologies: [Second Brain](./second-brain.md), [CODE method](./code-method.md)
- Workflows: [Knowledge capture workflow](./knowledge-capture-workflow.md), [Daily and weekly review](./daily-weekly-review.md)
- Resources: [Building a Second Brain](../resources/building-a-second-brain.md)
- Maps: [Methodology MOC](../maps/methodology.md)
- Tags: [#para](../tags/para.md), [#methodology](../tags/methodology.md), [#second-brain](../tags/second-brain.md)

## Open questions

- Where does *team* PARA differ from *personal* PARA — does an Area belong to a person or a team?
- How aggressive should we be about archiving — weekly, monthly, or only when the project literally closes?
