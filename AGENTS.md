# AGENTS.md

Guidelines for AI agents working in this repository.

## Repository Overview

This repository contains **Agent Skills** that implement the frameworks and exercises from Tim Ferriss's *The 4-Hour Workweek*. Skills install to `.claude/skills/` (Claude Code) or `.agents/skills/` (cross-agent standard). The repo also serves as a **Claude Code plugin marketplace** via `.claude-plugin/marketplace.json`.

- **Name**: 4-Hour Workweek Skills
- **Source**: *The 4-Hour Workweek* by Tim Ferriss
- **License**: MIT (this repo's contents — Tim's frameworks are his)

## Repository Structure

```
fhww-skills/
├── .claude-plugin/
│   └── marketplace.json   # Claude Code plugin marketplace manifest
├── skills/                # Agent Skills
│   └── skill-name/
│       └── SKILL.md       # Required skill file
├── AGENTS.md
├── CLAUDE.md
├── LICENSE
└── README.md
```

## Skill Specification

Each skill lives in `skills/<skill-name>/SKILL.md` and follows the [Agent Skills spec](https://agentskills.io/specification.md).

### Required Frontmatter

```yaml
---
name: skill-name
description: What this skill does and when to use it. Include trigger phrases.
---
```

### Frontmatter Field Constraints

| Field         | Required | Constraints                                                      |
|---------------|----------|------------------------------------------------------------------|
| `name`        | Yes      | 1-64 chars, lowercase `a-z`, numbers, hyphens. Must match dir.   |
| `description` | Yes      | 1-1024 chars. Describe what it does and when to use it.          |
| `license`     | No       | License name (default: MIT)                                      |
| `metadata`    | No       | Key-value pairs (author, version, etc.)                          |

### Name Field Rules

- Lowercase letters, numbers, and hyphens only
- Cannot start or end with hyphen
- No consecutive hyphens (`--`)
- Must match parent directory name exactly

**Valid**: `dreamlining`, `fear-setting`, `eighty-twenty`
**Invalid**: `Fear-Setting`, `-muse`, `eighty--twenty`

### Optional Skill Directories

```
skills/skill-name/
├── SKILL.md        # Required - main instructions (<500 lines)
├── references/     # Optional - detailed docs loaded on demand
├── scripts/        # Optional - executable code
└── assets/         # Optional - templates, data files
```

## Writing Style Guidelines

These skills implement an opinionated book. Match the book's voice where possible — direct, sometimes blunt, allergic to jargon, biased toward action and toward making the reader actually do the exercise rather than read about it.

### Structure

- Keep `SKILL.md` under 500 lines (move details to `references/`)
- Use H2 (`##`) for main sections, H3 (`###`) for subsections
- The skill should run a *conversation*, not deliver a lecture
- When the skill walks through a multi-step exercise, walk through it one step at a time and wait for the user before continuing

### Tone

- Direct and specific — "ask the user X" beats "consider asking the user about X"
- Use Tim's vocabulary where it earns its keep: New Rich, muse, dreamline, lifestyle design, mini-retirement, comparative advantage, geo-arbitrage
- Don't over-cite the book — the reader knows where this comes from
- Don't soften the uncomfortable questions. The exercises only work if they get answered

### Description Field Best Practices

The `description` is critical for discovery. Include:
1. What the skill does (in Tim's terms when applicable)
2. When to use it (trigger phrases the user is likely to say)
3. Related skills for scope boundaries

Example:

```yaml
description: Run Tim Ferriss's fear-setting exercise from The 4-Hour Workweek. Use when the user is stuck on a decision, putting off a big move, considering quitting a job, considering starting a business, or any time they say "I'm scared to," "what if I fail," "I should but I can't," "I keep putting this off." Replaces traditional goal-setting for high-stakes decisions. For dreamline-level "what do I want" work, see dreamlining instead.
```

## Conventions Specific to These Skills

1. **Always read `lifestyle-design` first.** Every skill begins by checking for `.claude/lifestyle-design.md` (or `.agents/lifestyle-design.md`) and using it as context. If it does not exist, the skill should offer to run `/lifestyle-design` first or ask the minimum questions inline.

2. **Default to forcing the exercise.** The point of these skills is not to tell the user what Tim says — it's to make the user do what Tim recommends. Don't summarize. Ask.

3. **One question at a time** for multi-step exercises (`dreamlining`, `fear-setting`, `expert-research`). The user should not be confronted with a wall of questions.

4. **Cite the book lightly, never reverentially.** Reference chapters or concepts when it helps the user place themselves; never quote at length.

5. **Refuse to skip steps.** If the user wants to jump to "tell me what muse to build," refuse and walk them back through the dreamline first. The book's order matters.

6. **Be specific with dollar amounts and timeframes.** Tim's exercises run on TMI (Target Monthly Income) and TDI (Target Daily Income). Always reduce vague goals to concrete numbers and dates.

## Claude Code Plugin

This repo also serves as a plugin marketplace. The manifest at `.claude-plugin/marketplace.json` lists all skills for installation via:

```bash
/plugin marketplace add <your-fork>/fhww-skills
/plugin install fhww-skills
```

## Pull Request Checklist

- [ ] `name` matches directory name exactly
- [ ] `name` follows naming rules (lowercase, hyphens, no `--`)
- [ ] `description` is 1-1024 chars with trigger phrases the user might say
- [ ] `SKILL.md` is under 500 lines
- [ ] Skill references `lifestyle-design` for context (if relevant)
- [ ] Skill walks the user through the exercise rather than summarizing it
- [ ] No sensitive data or credentials
