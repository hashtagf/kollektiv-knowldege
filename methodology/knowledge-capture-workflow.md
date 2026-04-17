---
title: Knowledge capture workflow
tags: [methodology, second-brain, knowledge-management, active]
created: 2026-04-17
aliases: [capture-workflow, knowledge-capture]
---

# Knowledge Capture Workflow

> The end-to-end recipe for moving a piece of information from *"I just saw something interesting"* to *"there's a useful note in the vault"*. This is the operational form of the *Capture* and *Organise* steps of the [CODE method](./code-method.md).

## Summary

Capture is the highest-volume stage of [Second Brain](./second-brain.md) and the easiest to bungle. Two failure modes dominate: capturing too much (the vault becomes an unread inbox) and capturing too little (you re-find the same article three times because you didn't keep it the first time). The discipline is **selective at the moment of capture, generous in the moment of organising** — say no early, then say yes to a properly-shaped note when you sit down to file it.

## The full workflow

```
SOURCE
  → quick-capture (≤30s)
    → daily note inbox
      → weekly review
        → decide: discard / Resource / Project / Concept
          → use the right template
            → link from the right index
              → tag in frontmatter
                → add to relevant tag page
                  → linked & discoverable
```

## Step-by-step

### 1. Source — *what triggers a capture*

A capture is worth making when **at least one** of these is true:

- It made you nod, react, or argue with it.
- It solves a problem you have *now* on a current [project](../projects/index.md).
- You can already imagine the project that would pull on it.
- It contradicts something already in the vault — surfacing the contradiction is itself useful.

If none of those is true, *don't capture*. Coverage is not the goal.

### 2. Quick-capture (≤30 seconds)

Drop the raw material in the **lightest possible place**:

- Today's [daily note](../templates/daily-note-template.md) under `## Notes`, or
- A new file using the [knowledge capture template](../templates/knowledge-capture-template.md) if it's bigger than a paragraph.

Required at this stage:

- The source link (URL, book + page, conversation context)
- A one-line *why I kept this* — written immediately, while you can still feel the resonance

Not required (do **not** do this now):

- Folder choice
- Tags
- Distillation

### 3. Park it in the inbox

Captures live in [daily notes](../templates/daily-note-template.md) until the [weekly review](./daily-weekly-review.md). Resist the urge to file mid-week — it's the most common procrastination move in PKM, and weekly batching gives you better signal about *which captures still feel useful three days later*.

### 4. Weekly review — the routing decision

For each capture from the past week, decide which of these it is:

| Decision | Where it goes | Template |
|---|---|---|
| **Discard** — no longer feels useful | nowhere; delete the line | — |
| **Resource** — reference for later | [resources/](../resources/index.md) | [resource-template.md](../templates/resource-template.md) |
| **Project material** — directly relevant to a current project | inside `projects/<name>/` | [project-template.md](../templates/project-template.md) or freeform |
| **Concept candidate** — atomic idea worth a permanent home | [concepts/](../concepts/index.md) | [concept-template.md](../templates/concept-template.md) |
| **Person** — someone new to the team's orbit | [people/](../people/index.md) | [person-template.md](../templates/person-template.md) |
| **Meeting** — outcome of a discussion | inside `projects/<name>/meetings/` or `meetings/` | [meeting-note-template.md](../templates/meeting-note-template.md) |
| **Daily** — already in the right place | leave it in the daily note | — |

The decision rule is **not** "what is this *about*?" — it's "*what's this for, and when will I reach for it next?*" (See [PARA method](./para-method.md).)

### 5. Apply the template

Copy the matching template, rename to `lowercase-hyphenated.md`, and fill in the frontmatter. The template's headings tell you *what shape a useful note has* — don't skip sections without thinking about them.

### 6. Link from the relevant index

Add a one-line entry to the folder's `index.md` so the note is reachable. A note not linked from at least one index is an orphan; orphans rot. See [link maintenance](../maps/link-maintenance.md).

### 7. Tag in frontmatter

Pick from the existing [tag vocabulary](../tags/index.md). Avoid inventing new tags unless the existing ones genuinely don't fit — and if you do invent one, create the tag page in [tags/](../tags/index.md) at the same time.

### 8. Add to relevant tag pages

For each tag in frontmatter, add a line to the tag's page in [tags/](../tags/index.md). This is the manual cost that keeps tag pages honest.

## What "good capture" looks like

A note ten minutes old should already have:

- Title (matches the filename)
- Frontmatter with `title`, `tags`, `created`, `aliases` if relevant
- A short *Summary* — written for future-you, not the source
- *Key ideas* in your own words — not quoted
- A *Source* link
- At least **two outbound links** (any combination: concept, MOC, tag, project)
- An entry in the relevant folder's `index.md`
- An entry in each relevant tag's page

If a captured note doesn't yet meet that bar, it's still in the inbox.

## Common failure modes

- **Inbox overload.** Captures pile up in daily notes, never reviewed. Fix: shorter weekly review, or be stricter at step 1.
- **Premature folders.** Filing during step 2 instead of step 4. Skips the cooling-off that filters out impulse captures.
- **Tag inflation.** New tag every other note. Fix: read the [tags index](../tags/index.md) before you reach for `tags:`.
- **Orphan creation.** Note in the right folder but no link in any index. Fix: step 6 is non-optional.
- **Capture as procrastination.** Long sessions of "organising the inbox" instead of producing output. The vault exists to feed *Express*; if it's not, ship something instead.

## Cadence

| Cadence | Activity |
|---|---|
| In the moment | Quick-capture (steps 1–3) |
| Weekly | Routing + templating + linking (steps 4–8) — see [daily and weekly review](./daily-weekly-review.md) |
| Monthly | Re-tag, prune, archive — see [link maintenance](../maps/link-maintenance.md) |

## Related

- Methodologies: [Second Brain](./second-brain.md), [CODE method](./code-method.md), [PARA method](./para-method.md), [Progressive summarization](./progressive-summarization.md), [Daily and weekly review](./daily-weekly-review.md)
- Templates: [Knowledge capture template](../templates/knowledge-capture-template.md), [Daily note template](../templates/daily-note-template.md), [Concept template](../templates/concept-template.md), [Resource template](../templates/resource-template.md)
- Maps: [Methodology MOC](../maps/methodology.md), [Knowledge Management MOC](../maps/knowledge-management.md), [Link maintenance](../maps/link-maintenance.md)
- Tags: [#capture](../tags/capture.md), [#methodology](../tags/methodology.md), [#second-brain](../tags/second-brain.md)

## Open questions

- Should the daily-note inbox be *one* file per day, or *one* rolling capture file per week?
- Where do voice / audio captures sit in this workflow before the LLM transcription pattern from [AI knowledge integration patterns](./ai-knowledge-integration.md) hits them?
