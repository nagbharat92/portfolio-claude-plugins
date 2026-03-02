---
name: content-creation
description: "Create portfolio case studies, blog posts, and project write-ups for bharatnag.dev. Use when Bharat wants to write about a project, create a case study, draft a blog post about design or product thinking, or generate content for his personal site. Also use when he mentions writing about something he built, sharing a project publicly, or creating content from a design-thinking file. Do NOT use for generic marketing copy, SEO content, or corporate communications."
---

# Content Creation Skill

Create content for bharatnag.dev — project case studies, blog posts on design and product thinking, and project showcase pages. Every piece is written in Bharat's voice: direct, observational, no fluff.

This skill is personal. It writes as one specific person, drawing on his design philosophy, personality, and worldview. Before generating any content, read the relevant reference files to calibrate voice and perspective.

## Reference Files

Read these before writing. They live in `references/` within this skill directory.

| File | What it contains | When to read |
|------|-----------------|--------------|
| `blog-philosophy.md` | Voice, tone, structure, anti-patterns, phrasing examples | Always. Read first. |
| `personality-reference.md` | How Bharat thinks, talks, gives feedback, processes ideas | Always. Read second. |
| `design-philosophy.md` | Core beliefs, the browser thesis, game designer's lens, design principles | Always for blog posts. For project pages, read if the project touches design thinking. |
| `design-principles.md` | 100+ design principles from Universal Principles of Design | Only when a specific principle is needed to ground an observation. Do not load the full file. |

## Inputs

This skill works with two types of input:

**A design-thinking file** — a `<project-name>-design-thinking.md` file produced by the `/extract-context` command. This contains the project's intent, decisions, dead ends, surprises, and raw quotes extracted from brainstorming conversations. If provided, this is the primary source material.

**A project repo** — if the user gives folder access to a project repository, inspect it directly. Read the README, understand the tech stack, look at the commit history, note anything the design-thinking file missed.

If neither is provided, the skill falls back to interviewing the author directly (see Phase 1 below).

## Content Types

### Short-form: Project Showcase Page

A single page for the portfolio. Someone lands on it and in 30 seconds understands what was built, why, and what was interesting about it.

Structure:
```
frontmatter (name, year, iframe, stats with tech + links)
---
## What I built
[1-2 paragraphs: what it is, why it exists]
---
![Screenshot or hero image](url)
> Caption
## How it came together
[1-2 paragraphs: the interesting decisions, the process]
---
[Optional: closing thought. No heading. Brief.]
```

Keep it tight. 2-4 text blocks. Images between sections.

### Long-form: Blog Post or Essay

Design and product thinking from the perspective of someone who builds things. Not tutorials. Not listicles. Observations that become arguments.

Structure:
```
frontmatter (name, year, stats if applicable)
---
## [Opening — no generic title. State the observation or tension.]
[Hook without clickbait. Reader knows what this is about in two sentences.]
---
## [Core sections — 1-3 depending on depth]
[Each advances the narrative. Research woven in, not dumped.]
---
![Image if relevant](url)
> Caption
## [Resolution / reflection / what changed]
[What was learned, noticed, or decided.]
---
[Optional: closing line. No heading. The takeaway, stated simply.]
```

Length: 600-1200 words typically. Never exceed 2000 unless complexity demands it.

## The Workflow

### Phase 1: Discover

Understand what the author wants to share and why.

**If a design-thinking file is provided:** Read it fully. You already have the spark, the intent, the decisions. Skip the basic questions. Instead, confirm your understanding and ask about gaps: "I see the project started because of X and the biggest decision was Y. Is that the story, or is there a different angle you want to lead with?"

**If no design-thinking file:** Interview the author. One question at a time. Do not dump a list.

Start with: "What are we writing about today?"

Follow up based on the answer:
- For a project: "What made you want to build this?" / "What's the one thing about this project that's actually interesting?"
- For an idea: "What's the thought you keep coming back to?"
- For anything: "Is there something you want people to walk away with?"

Determine the shape from the conversation:

| Signal | Short-form (project page) | Long-form (blog/essay) |
|--------|--------------------------|----------------------|
| Describes a thing built | Yes | — |
| Describes an idea, opinion, or process | — | Yes |
| Answers are concise, factual | Yes | — |
| Answers have depth, tangents worth following | — | Yes |
| Says "just a quick post" | Yes | — |
| Wants to explore a topic | — | Yes |

Confirm: "This sounds like a [short project page / longer piece]. That right?"

### Phase 2: Collect

**For short-form:** Ask for links naturally: "Drop me the links — project URL, GitHub repo, and images if you have them." Move to research.

**For long-form:** Ask 2-3 questions that draw out narrative:
- "What surprised you while building this?"
- "What would you tell someone attempting the same thing?"
- "What's the part nobody sees — the messy middle?"

Present a brief outline (bullet points showing the arc) before writing. Get approval.

### Phase 3: Research

**This phase is not optional.** Do not generate content from description alone.

For every piece:
- If repo access is available, read it. Look at the README, tech stack, commit history, folder structure. Note what the author didn't mention.
- If a project URL is provided, visit it. Understand what the thing looks and feels like.
- If the design-thinking file has raw quotes, use them as source material.

For long-form, go further:
- Web search for relevant context. What's the state of the art? What have others said?
- Find one or two concrete details from research that would make the piece richer.

After research, share findings: "I looked at your repo and noticed X. I also found Y. Want me to weave any of this in?"

### Phase 4: Generate

**Read the reference files before writing.** Every time. At minimum: `blog-philosophy.md` and `personality-reference.md`.

Write the draft. Present it in full in the conversation. Do not write to a file yet.

Ask: "How does this feel? Anything you'd cut, add, or rephrase?"

Iterate until the author is satisfied. Only then write the file.

## Output Format

The final output is a `.md` file written to the portfolio repo at:
`src/data/content/[subfolder]/[filename].md`

If the user provides access to the portfolio repo, write directly. Otherwise, produce the file and let the user place it.

**Filename:** kebab-case, descriptive, no dates. `portfolio-site.md`, `weather-app.md`.

**Subfolder:** Match the content category. Current folders:
- `personal-work/` — side projects, experiments, things built for learning

If no subfolder fits, ask the author where it should go.

### Frontmatter Format

```yaml
---
name: "Project Name"
id: project-name
year: 2025
featured: true
order: 1
iframe: https://example.com
stats:
  - React
  - TypeScript
  - label: GitHub
    href: https://github.com/...
---
```

### Body Conventions

- `## Heading` followed by paragraphs → TextBlock with title
- Paragraphs without heading → TextBlock without title
- `---` → DividerBlock
- `![alt](src)` on its own line → ImageBlock
- `> caption` after image → sets image caption
- `[video](embedUrl)` on its own line → VideoBlock

## Voice Rules

These are non-negotiable. Read `blog-philosophy.md` for the full guide. The essentials:

**Do:**
- Be direct. Say the thing. No warm-up paragraphs.
- Be specific. Concrete details over abstract claims.
- Lead with intent. Why something was built matters more than what it does.
- Respect scope. A weekend experiment is not "a comprehensive platform."
- Let the writing show excitement through specificity, not adjectives.
- Make technical terms earn their place. If a term wouldn't come up naturally in conversation (e.g. "OKLCH," "service worker," "stagger animation"), either explain it plainly in the same sentence or replace it with what it actually does. "A color system that handles light and dark mode cleanly" beats "OKLCH-based theming." The reader should never have to Google something to follow the paragraph.

**Never:**
- Use emojis
- Use exclamation marks in body text
- Use em dashes (—) or en dashes (–) anywhere in the text. This is a hard rule with zero exceptions. Rewrite any sentence that would use a dash: use a colon, a comma, a period, or parentheses instead. If you catch yourself reaching for a dash, stop and restructure the sentence.
- Open with a question or definition
- Start with "In this post, I'll walk you through..."
- Use "Let's dive in" / "Without further ado" / "Interestingly"
- Use "landscape" to mean "field"
- Use "genuinely" / "honestly" / "straightforward"
- Summarize what you just said
- Sound like a thought leader
- Reference the AI nature of the writing
- Use bullet points in the body of a post

**Tone:** Someone showing you their workshop. Quiet confidence. Here's what I made. Here's why. Here's what I noticed. Take it or leave it.
