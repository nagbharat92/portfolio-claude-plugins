---
description: Extract project context from a brainstorming conversation to produce a design-thinking file for content creation
argument-hint: "<project name>"
---

# Extract Context

Look back through this conversation and extract everything that matters for telling the story of this project. The output is a structured design-thinking file that becomes input for the `/create-content` command.

## Trigger

User runs `/extract-context` or asks to extract project context, create a design-thinking file, or capture what was discussed for content creation later.

## Important

This is raw material extraction, not content creation. Do not editorialize. Do not write in the author's voice. Do not try to make it sound good. Be factual, specific, and tied to actual moments in the conversation.

"We discussed the architecture" is useless. "Bharat considered a monorepo but chose separate repos because he wanted to deploy the API independently" is useful.

## Extraction Sections

Read back through the entire conversation. For each section, extract what's available. Some will be rich, some thin. Do not pad. Do not invent.

If a section seems empty, do not immediately write "Nothing surfaced." Make one inference attempt first — look at adjacent decisions, implied constraints, or things that were notably absent from discussion. If you can offer a qualified inference, write it clearly marked: "Not discussed directly, but [inference] based on [evidence]." Only write "Nothing surfaced in this conversation" if even that attempt comes up empty.

### 1. Project Identity
What is this project in one sentence? Distill from how it was discussed, not from a README.

### 2. The Spark
The observation, frustration, or curiosity that started this. Look at the earliest messages. What was the impulse before it became a project?

### 3. Intent and Motivation
Why does this need to exist? What gap does it fill? What is the author's personal relationship to the problem?

### 4. Decision Log
Every moment where a choice was made between alternatives. Format each as:
- **Decision:** What was being decided
- **Considered:** What options were on the table
- **Chose:** What was selected
- **Why:** The reasoning, in the author's own logic

Look for: technology choices, architecture decisions, scope decisions, naming decisions, UX decisions, what got cut and why.

### 5. Scope Evolution
How did the project change shape? Original vision versus what it became. What grew, shrank, pivoted.

### 6. Craft Moments
Specific design or technical decisions where real thought went in. The details that reveal care.

### 7. Tensions and Trade-offs
Where things pulled in opposite directions. What was sacrificed to gain something else.

### 8. Surprises
What was unexpected. Libraries that didn't work. Problems simpler than feared. Features that became the whole point.

### 9. Dead Ends
Approaches tried and abandoned. Time spent on things that got thrown away.

### 10. The Vibe Coding Story
How did the human-AI collaboration work on this project? This section is specifically about the relationship with AI tools — the dynamic between human intent and machine output.
- What did AI help with? Where did it get in the way?
- Where did the author have to teach the AI about intent?
- How did the Claude-brainstorming, VS-Code-building workflow play out?
- Observations specific to this project, not general opinions.

### 11. The Game Designer's Fingerprint
Bharat's background is animation, game development, 3D modeling. He thinks about products as environments that respond to the user. Look for moments where this shaped a decision: spatial thinking, pacing, environment design, player agency applied to product.

### 12. Friction Moments
Small annoyances in the design or build process that became design decisions. Things that bothered him that wouldn't bother most people — an API shape that felt wrong, a naming convention that grated, a default behavior that violated his instincts.

This is about design and craft friction, not tool friction. Tool-related friction (AI losing context, IDE limitations) belongs in Section 10.

### 13. Taste References
Cross-domain inspirations. References from games, films, music, physical products, architecture, other software. Capture even casual mentions.

### 14. Design Principles Activated
Which of these beliefs came into play, and how?
- Intent before interface
- Naming is design
- Simplicity is the result, not the starting point
- Constraints are design partners
- Details are where intent becomes visible
- Context over configuration
- Products exist in time, not just in screenshots
- Augmentation over replacement
- Evaluate from experience backward to architecture

Only include principles that actually showed up. No labels without stories.

### 15. Honest Scope and Timeline
How long did things take? What was planned vs. improvised? If not stated directly, estimate from conversation density and complexity. A rough sense of time investment — even qualified ("likely a weekend build based on scope") — is more useful than silence.

### 16. Open Threads
What's unresolved. What comes next. Questions the project raised but didn't answer.

### 17. Raw Quotes
Pull 5-15 direct quotes from the conversation. Things Bharat actually said. Prioritize: clarity about the project, strong opinions, honest admissions, observations that reveal how he thinks.

For each quote, add a one-line note on why it matters for content. Not interpretation — just a flag. Example:
- "remove the dashes. Make it normal human" — *Shows precision in naming what's wrong with a design, not just that something is wrong.*

### 18. What Else
Your open field. What did you notice that doesn't fit above?

Look for: patterns, contradictions, recurring frustrations, offhand remarks that revealed something deeper, energy shifts, connections to broader thinking.

Then separately: **if you were writing this story, what angle would you lead with?**

## Output

Save as `<project-name>-design-thinking.md` using kebab-case. All 18 sections with headings. Thin sections are fine. Empty padding is not.

This file becomes input for `/create-content`. The extraction covers the thinking. The repo covers the building. Together they tell the full story.
