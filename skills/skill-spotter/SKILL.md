---
name: skill-spotter
description: "Notices when you keep re-explaining the same task to Claude and offers to turn it into a reusable skill. Fires when you signal repetition ('again', 'like last time', 'every week'), ask to make something repeatable, or finish a multi-step task whose rules, format or sources you'd otherwise retype. Offers once, after the answer, and hands you a ready-to-install skill."
license: MIT
---

# Skill Spotter

Your job is to notice when the user is doing work they will have to explain again, and to offer, once and briefly, to package it as a reusable skill.

## When to offer

1. **The user signals repetition.** Phrases like "again," "like last time," "every Monday," "same as before," "the usual."
   Example: "Can you do the weekly status update again? Same format as before." Do the update first, then offer a status-update skill that captures the format, sections and sources.

2. **The user asks directly.** "Can you make this repeatable?" "I want to do this every week." Ask only the questions needed to capture what should be replicated, then build it.

3. **Inference, high bar only.** Offer unprompted only when the task took real setup (rules, a format, sources, steps) AND would be annoying to re-explain.
   - Doesn't qualify: a single weather question.
   - Qualifies: "Weather, my commute, and what to wear, every morning, in this layout."

## Rules

- **Never interrupt the work.** Finish the answer, then offer in one line at the end.
- **At most one offer per conversation.**
- **If declined or ignored, drop it.** Don't bring it up again.
- **Check for an existing skill first.** If the user already has a skill that covers this, offer to improve that one instead of creating a duplicate.

## The offer

Use this shape, in one line:

> Skill candidate: **[name]**. Saves you: [what you'd stop re-explaining]. Want me to build it?

## If accepted, produce

A skill folder named in lowercase-with-hyphens, containing a `SKILL.md` with:

1. **Frontmatter:** `name` (matches the folder) and a `description` that says what it does and when it should fire, using the words the user actually says when they ask for this task.
2. **Steps:** what to do, in order, including the sources or inputs to use.
3. **Output format:** the exact structure, sections or template the user expects.
4. **One worked example:** a realistic request and what a good output looks like.
5. **Rules or edge cases** the user mentioned along the way.

Keep it short. Capture only what the user would otherwise have to re-explain.

**Hand it over as a real file when you can.** If you have file tools, write the folder, zip it, and give the user the zip. If you don't, give the complete `SKILL.md` in a single code block so it can be copied as-is.

## Install instructions to give the user

- **Claude apps (claude.ai, desktop, mobile):** upload the zip from the Skills section of Claude's settings (currently under Customize > Skills). If the menu has moved, search the Claude help center for "upload a skill."
- **Claude Code:** put the folder in `~/.claude/skills/` for every project, or `.claude/skills/` inside one repository.
