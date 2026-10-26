# Skill Spotter

**Stop re-explaining the same task to Claude.**

Skill Spotter is a Claude skill that notices when you're doing work you'll have to explain again, and offers, once, to package it as a reusable skill. Next time, you just ask, and Claude already knows the format, the sources and the rules.

## The problem

Most people never write skills. Not because skills aren't useful, but because nobody stops mid-task to think "I should turn this into a skill." So the same setup gets retyped every week: the report format, the sources to check, the tone, the sections, the edge cases.

## What it does

Skill Spotter watches for three signals:

| Signal | Example |
| --- | --- |
| **You say it's a repeat** | "Do the weekly status update again, same format as last time." |
| **You ask for it** | "Can you make this repeatable?" |
| **The task clearly earns it** | A multi-step job with rules, a format and sources you'd hate to retype |

When one fires, Claude finishes your task first, then adds a single line:

> Skill candidate: **weekly-status-update**. Saves you: re-explaining the sections, the sources and the tone. Want me to build it?

Say yes and you get a ready-to-install skill folder. Ignore it and it never asks again in that conversation.

## Designed not to nag

- Never interrupts the work. The offer comes after the answer, in one line.
- At most one offer per conversation.
- Declined or ignored means dropped.
- A high bar for guessing: one-off questions don't qualify.
- Checks for a skill you already have before suggesting a new one.

## Install

**Claude apps (claude.ai, desktop, mobile)**
1. Download [`skill-spotter.zip`](https://github.com/BrianChase515/skill-spotter/raw/main/skill-spotter.zip).
2. In Claude, open Customize > Skills and upload the zip.

**Claude Code**
```
/plugin marketplace add BrianChase515/skill-spotter
/plugin install skill-spotter@brianchase-skills
```
Or copy `skills/skill-spotter/` into `~/.claude/skills/`.

**Other agents that read SKILL.md** (for example GitHub Copilot): copy `skills/skill-spotter/` into your agent's skills folder, such as `.github/skills/` or `~/.copilot/skills/`.

## Companion skill

[Blindspot](https://github.com/BrianChase515/blindspot) catches the missing context in a vague request before Claude guesses. Use Blindspot to dial a task in, then Skill Spotter to package it.

## Feedback

Tried it? Open an issue with what it caught, what it missed, or where it was too eager. That's how the trigger rules get better.

## Author

Built by [Brian Chase](https://github.com/BrianChase515). MIT licensed.
