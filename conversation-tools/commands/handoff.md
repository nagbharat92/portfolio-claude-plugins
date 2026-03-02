---
description: Create a handoff document to carry context into a new conversation
argument-hint: "<optional: project or topic name>"
---

# Handoff

Read back through this entire conversation and produce a structured handoff document. The purpose is to let a new conversation pick up exactly where this one left off — productive from the first message, without re-deriving anything.

## Trigger

User runs `/handoff` or says they want to move to a new conversation, start fresh, carry context forward, or create a summary for continuing elsewhere.

## Important

This is an operational document, not a narrative. Think of it as a save file, not a story. The next conversation needs to act, not understand the journey.

Be specific. "We discussed the architecture" tells the next conversation nothing. "The app uses a Next.js frontend with a separate Express API, deployed independently on Vercel and Railway" tells it everything.

File paths, repo URLs, package names, API endpoints — include them. The next conversation will waste its first three messages asking for these if you don't.

## Sections

### 1. What We're Building
One to three sentences. The goal. Not the history of how the goal was arrived at — just what it is now.

### 2. Current State
What exists right now. Be concrete:
- What's built and working
- What's partially built (and how far along)
- What's been configured or set up (environments, repos, deploys, accounts)
- Key file paths, repo URLs, branch names

This is the heaviest section. Err on the side of too much detail here.

### 3. Decisions Made
Compact list of choices that have been settled. Each one gets one to two lines max:
- **What was decided** — and the core reason why

Do not list alternatives that were considered. Do not re-open deliberation. The next conversation should treat these as settled unless the user says otherwise.

### 4. Things That Didn't Work
Approaches tried and abandoned. Brief — just enough to prevent the next conversation from walking into the same wall.

Format: what was tried → why it failed or was dropped.

### 5. Open Questions
Unresolved decisions or ambiguities that still need the user's input. These might become the first thing the new conversation asks about.

If nothing is unresolved, say so. Don't manufacture questions.

### 6. Next Steps
What should happen next. Ordered if sequence matters. These should be actionable — specific enough that the next conversation could start on the first one immediately.

### 7. Working Context
Anything that doesn't fit above but would confuse the next conversation if missing:
- Working style preferences established during the conversation (level of detail, pace, tone)
- Constraints mentioned early that shaped everything downstream
- Background the user shared that won't be obvious from the project alone
- Tools, models, or workflows being used (e.g., "brainstorm in Claude, build in VS Code with Copilot")

Only include what's relevant. If the conversation was purely technical with no special working context, skip this section.

## Suggested Opening Message

At the end of the document, include a short block the user can copy-paste into the new conversation:

```
I'm continuing from a previous conversation. I've attached the handoff document — please read it fully before responding. Pick up from the next steps section.
```

## Output

Save as `<topic>-handoff.md` using kebab-case. If no topic name was given, infer one from the conversation's primary focus.

Keep the document tight. If it takes more than two minutes to read, it's too long. Every sentence should earn its place by preventing a wasted exchange in the next conversation.
