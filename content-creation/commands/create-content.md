---
description: Write a project case study, blog post, or portfolio page for bharatnag.dev
argument-hint: "<topic or project name>"
---

# Create Content

Generate content for bharatnag.dev — project showcase pages, case studies, or blog posts on design and product thinking.

## Trigger

User runs `/create-content` or asks to write about a project, create a case study, or draft a blog post.

## Inputs

Gather what's available. Not everything will be provided every time.

1. **Design-thinking file** — a `<project-name>-design-thinking.md` file from a previous `/extract-context` run. If attached, this is the primary source. Read it fully before asking questions.

2. **Project repo access** — if the user gives folder access to the project repository, use it for research. Read the README, inspect the structure, check commit history.

3. **Topic** — if no design-thinking file, ask: "What are we writing about today?" One question at a time. Have a conversation.

4. **Links** — project URL, GitHub repo, image folder. Ask naturally: "Drop me the links — project URL, GitHub, images if you have them."

## Workflow

Follow the content-creation skill's 4-phase workflow:

1. **Discover** — understand what to write and why. If a design-thinking file is provided, confirm the angle rather than re-interviewing. If not, interview one question at a time.

2. **Collect** — gather links, images, and narrative depth. For long-form, ask 2-3 follow-up questions and present an outline before writing.

3. **Research** — inspect the repo, visit the project URL, do web research for long-form. Share findings with the author before writing.

4. **Generate** — draft in conversation first. Iterate until the author is satisfied. Only then write the `.md` file to the portfolio repo.

## Output

A single `.md` file with YAML frontmatter and markdown body, following the portfolio's content authoring format. Written to `src/data/content/[subfolder]/` in the portfolio repo, or produced for the author to place manually.

Ask: "How does this feel? Anything you'd cut, add, or rephrase?"
