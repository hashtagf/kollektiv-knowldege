---
title: Daily and weekly review
tags: [methodology, second-brain, review, knowledge-management, active]
created: 2026-04-17
aliases: [review-cadence, review-workflow]
---

# Daily and Weekly Review

> The cadences that keep the vault honest. Daily for *staying current*; weekly for *routing captures*; monthly for *pruning and reorganising*. Without these reviews [Second Brain](./second-brain.md) collapses into a write-only notebook.

## Summary

Reviews are the connective tissue between [CODE](./code-method.md) stages. The Capture step happens *in the moment*; everything else (Organise, Distil, Express) is done in batch during a review. Different cadences serve different purposes — daily reviews look forward (what to do today), weekly reviews look backward (route last week's captures), monthly reviews look at the *vault itself* (what's drifting, what's orphaned, what's archive-ready).

Skip these and the symptoms appear in 4–8 weeks: an unread daily-note inbox, projects with no recent activity but still marked active, tag pages out of date with the notes they index.

## The three cadences

### Daily review (~5 min, end of day)

The lightest cadence. The point is to **close the day cleanly** and **set tomorrow's first move**.

- Use the [daily note template](../templates/daily-note-template.md) — every working day starts as a daily note.
- At day-end:
  - Tick off completed tasks.
  - Carry incomplete tasks to tomorrow's `## Tomorrow → Carry over` section.
  - Add one line under `## Learned` if anything is worth keeping.
  - Don't try to file captures yet — that's Friday's job.

### Weekly review (~30–60 min, Friday or Monday)

The **load-bearing cadence**. This is where the [knowledge capture workflow](./knowledge-capture-workflow.md) actually turns inbox material into vault material.

Use the [weekly review template](../templates/weekly-review-template.md). The full pass:

1. **Inbox sweep.** Read each capture from the past week's daily notes. For each: discard, promote to a Resource, promote to a Concept, tie to a Project, or convert to a Meeting note. (Routing rules: see [knowledge-capture-workflow.md](./knowledge-capture-workflow.md).)
2. **Project status.** Walk [projects/index.md](../projects/index.md). For each active project: still active? Blocked? Done — move to `archive/`?
3. **Distil one note.** Pick a single resource that's been sitting at distillation [layer 1](./progressive-summarization.md) and push it to layer 2 or 4. One per week. Don't binge.
4. **Index hygiene.** For any new note in the past week, check it's linked from the relevant folder's `index.md` and tag pages.
5. **Set next week's focus.** One sentence: what's the *single* thing you want done by next Friday?

### Monthly review (~60–90 min, first weekend of the month)

Looks at the *vault as a system*. Mostly maintenance.

Use the [monthly review template](../templates/monthly-review-template.md). The full pass:

1. **Archive shipped projects.** Anything in `projects/` that shipped should be in `archive/`. (See [PARA method](./para-method.md).)
2. **Re-tag drifters.** For each tag page in [tags/](../tags/index.md), check 2–3 notes still belong under that tag.
3. **Orphan hunt.** For each folder, look for notes not linked from the `index.md`. Either link them or delete them.
4. **Broken links.** Run the manual procedures in [link maintenance](../maps/link-maintenance.md).
5. **MOC review.** For each MOC in [maps/](../maps/index.md), check the read-order still makes sense. Add new notes; promote concepts that have outgrown a section.
6. **Decide on new tags or folders.** Anything you've been wanting to add for a few weeks? If yes, propose it now (not mid-week).

## What a healthy cadence looks like

| Day of week | Activity |
|---|---|
| Monday | Open daily note. Glance at last week's `## Tomorrow → Next up`. |
| Tuesday–Thursday | Daily notes; light end-of-day. Captures pile up — fine. |
| Friday | **Weekly review.** ~45 min. Empties the inbox. |
| First Saturday of month | **Monthly review.** ~75 min. Vault hygiene. |

## Failure modes

- **Skipping the weekly review.** The vault works exactly until you skip two in a row, then the inbox becomes uninhabitable. Fix: make it the *first* meeting on Friday afternoon, with a [weekly review template](../templates/weekly-review-template.md) open.
- **Reviews that turn into binge-distillation.** "I'll just clear the whole inbox." 90 minutes later, no output, no Express. Fix: cap at one distillation per weekly review.
- **Daily reviews bloating into journaling.** Daily review is for *closing the loop*, not for processing the day's emotions. Use a separate file if you need that.
- **Monthly review becomes "redesign the vault."** Tinkering with structure is fun and feels productive, but it's not output. Set a 90-min cap.

## Apply it in this vault

- Templates: [daily note](../templates/daily-note-template.md), [weekly review](../templates/weekly-review-template.md), [monthly review](../templates/monthly-review-template.md).
- Routing rules: [knowledge capture workflow](./knowledge-capture-workflow.md).
- Vault hygiene procedures: [link maintenance](../maps/link-maintenance.md).
- Cadence-aware folder triage: [PARA method](./para-method.md).

## Related

- Methodologies: [Second Brain](./second-brain.md), [CODE method](./code-method.md), [Knowledge capture workflow](./knowledge-capture-workflow.md), [PARA method](./para-method.md), [Progressive summarization](./progressive-summarization.md)
- Templates: [Daily note](../templates/daily-note-template.md), [Weekly review](../templates/weekly-review-template.md), [Monthly review](../templates/monthly-review-template.md)
- Maps: [Methodology MOC](../maps/methodology.md), [Link maintenance](../maps/link-maintenance.md)
- Tags: [#review](../tags/review.md), [#methodology](../tags/methodology.md), [#second-brain](../tags/second-brain.md)

## Open questions

- Should the weekly review be a private practice or a team ritual — does sharing the inbox sweep help or just create noise?
- How do agents (see [Claude Brain](./claude-brain.md)) participate in monthly review — auto-suggest archives, or stay out of it?
