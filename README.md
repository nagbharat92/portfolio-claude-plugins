# Bharat's Plugins

A personal Cowork plugin for bharatnag.dev. Content creation, project documentation, and whatever else needs automating.

## Installation

```bash
claude plugins add bharats-plugins
```

Or install locally by pointing Cowork at this directory.

## Commands

| Command | Description |
|---|---|
| `/create-content` | Write a project case study, blog post, or portfolio page |
| `/extract-context` | Extract project context from a brainstorming conversation into a design-thinking file |

## Skills

| Skill | Description |
|---|---|
| `content-creation` | Voice, philosophy, and workflow for generating content as Bharat |

## Workflow

1. Brainstorm a project in Claude conversations as usual
2. When ready to write about it, run `/extract-context` in that conversation to produce a `<project-name>-design-thinking.md` file
3. Start a new Cowork task, attach the design-thinking file (and optionally give folder access to the project repo), and run `/create-content`
4. Claude interviews, researches, drafts, and iterates until the post is right
5. Final `.md` file goes to the portfolio repo at `src/data/content/`

## Reference Docs

The content-creation skill draws on these references (in `skills/content-creation/references/`):

- **blog-philosophy.md** — writing voice, tone, structure, anti-patterns
- **personality-reference.md** — how Bharat thinks, talks, and processes ideas
- **design-philosophy.md** — core beliefs, the browser thesis, game designer's lens
- **design-principles.md** — 100+ design principles from Universal Principles of Design
