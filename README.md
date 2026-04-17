# kollektiv-knowledge

An Obsidian-style knowledge base for the Kollektiv team. Plain markdown files, organized into folders, connected by relative links and wiki-links.

> **Start here:** [index.md](./index.md) — the home node for the vault.

## Folder structure

```
.
├── index.md              # vault home — main navigation
├── README.md             # this file
├── concepts/             # ideas, theories, definitions, frameworks
│   └── index.md
├── projects/             # active & archived projects
│   └── index.md
├── people/               # colleagues, stakeholders, contacts
│   └── index.md
├── resources/            # articles, books, links, references
│   └── index.md
└── templates/            # starter notes for each content type
    ├── index.md
    ├── concept-template.md
    ├── project-template.md
    ├── person-template.md
    ├── resource-template.md
    ├── meeting-note-template.md
    └── daily-note-template.md
```

Each folder has its own `index.md` that lists the notes inside it and links back to the other folders — so you can navigate the whole vault without a sidebar.

## How to use this vault

### Open it

- **Obsidian** (recommended): `File → Open folder as vault`, then point at this repo.
- **Any markdown editor** works too — VS Code, iA Writer, plain text. The vault is just markdown and folders.

### Create a new note

1. Pick the right folder: a concept goes in `concepts/`, a project in `projects/`, etc.
2. Copy the matching template from [`templates/`](./templates/index.md) into that folder.
3. Rename the file. Use lowercase and hyphens: `zettelkasten-method.md`, not `Zettelkasten Method.md`.
4. Update the frontmatter: `title`, `tags`, `created` date.
5. Fill in the body. Delete sections you don't need.
6. Link the new file from the folder's `index.md` so it's discoverable.

### Link notes together

Obsidian supports two linking styles. Both work; pick whichever fits the context.

#### Wiki-links (Obsidian-native)

```markdown
See [[zettelkasten-method]] for the underlying idea.
See [[zettelkasten-method|note-taking]] to customize the link text.
```

Wiki-links resolve by filename anywhere in the vault — you don't need a path. Great for concept-to-concept references.

#### Relative markdown links (portable)

Use these when you want the vault to render correctly on GitHub, GitLab, or any standard markdown viewer.

```markdown
[Concepts index](./concepts/index.md)
[A concept from a project note](../concepts/zettelkasten-method.md)
[Back to home](../index.md)
[A resource I cited](../resources/building-a-second-brain.md)
[A person on this project](../people/jane-doe.md)
```

Relative-path rules of thumb:

| From | To | Path |
|------|----|------|
| Root (`index.md`) | a folder's index | `./concepts/index.md` |
| A folder's index | the root | `../index.md` |
| A folder's index | a sibling folder | `../projects/index.md` |
| A note inside a folder | another folder | `../resources/foo.md` |
| A note inside a folder | a sibling note | `./other-note.md` |

### Tags and frontmatter

Every note starts with YAML frontmatter. At minimum:

```yaml
---
title: Zettelkasten Method
tags: [concept, note-taking]
created: 2026-04-17
---
```

Tags cluster notes across folders. Common tags: `concept`, `project`, `person`, `resource`, `meeting`, `daily`.

### Conventions

- **Filenames:** lowercase, hyphen-separated, `.md` extension.
- **One idea per note.** Atomic notes link well; kitchen-sink notes don't.
- **Link generously.** A note with no links is an orphan. Aim for at least two outbound links.
- **Keep indexes current.** When you add a note, add a line to the folder's `index.md`.
- **Dates** are ISO-8601: `2026-04-17`, not `April 17, 2026`.

## Contributing

This vault is a living document. Add, edit, and reorganize as the team's knowledge grows. When in doubt, copy a template and start typing — a rough note is better than no note.
