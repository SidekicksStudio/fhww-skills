---
name: lifestyle-design
description: Establish or update the foundational lifestyle-design context that every other 4-Hour Workweek skill reads first — the user's current life, constraints, dreamlines, target monthly income (TMI), freedom criteria, and what they're optimizing for. Use when the user wants to "set up", "get started with", "initialize", or "kick off" the 4HWW skills, when they ask "where do I start", or when an existing context file needs updating because circumstances have changed (new job, new relationship, new dreamline). Other skills will refer the user back here if no context file exists. For the actual dreamline exercise, see dreamlining. For mindset/principles, see new-rich-rules.
metadata:
  version: 1.0.0
---

# Lifestyle Design Context

You are helping the user create a foundational context file that every other 4-Hour Workweek skill will read first. Think of it like `product-marketing-context.md` for the New Rich — a single source of truth for who this person is, what they want, and what they're optimizing for.

## The Output

A markdown file at one of:
- `.claude/lifestyle-design.md` (preferred for Claude Code)
- `.agents/lifestyle-design.md` (cross-agent standard)

If the user is in a project directory, write it there. Otherwise write it to wherever the user keeps their personal context files. Ask if it's not obvious.

## Before Writing

Check if a file already exists at either path. If it does, read it and ask the user what to update rather than overwriting.

If they're brand new to all of this, mention briefly that this is the foundation — every other skill will read this — and that it's fine to fill in only what they know now and come back later.

## What Goes In The File

Walk the user through the sections below **one section at a time**. Don't dump them all at once. Don't move on until the answer is concrete. Vague answers ("more freedom", "less stress") get pushed back on with "What does that look like in a normal Tuesday?"

### Section 1: Current state

What does your life actually look like right now?

- **Work**: Job title, company, hours/week, how much you like it (1-10), how much it pays
- **Money**: Approximate monthly income after tax, monthly expenses, savings, debt
- **Time**: Weekly hours by category (work, sleep, family, hobbies, "wasted")
- **Place**: Where you live, whether you can leave, what's anchoring you
- **People**: Partner / kids / dependents / co-parents / aging parents — anyone whose life is downstream of your decisions
- **Health**: Anything that constrains options (chronic illness, fitness, energy)

### Section 2: Constraints

What can't change, vs. what looks like it can't but actually can?

The book's lesson here: most "can'ts" are unexamined. Push gently.

- Hard constraints (custody arrangements, citizenship/visa, medical, contractual)
- Soft constraints disguised as hard (mortgage, "my partner would never," "my industry doesn't allow remote")
- Things you've told yourself you have to do that nobody is actually requiring

### Section 3: What you're optimizing for

This is where most people stall. Push them to a single sentence.

- **Currency of choice**: Time / Mobility / Income / Status / Mastery / Connection — rank top 3
- **Definition of success in 1 sentence**: "I am successful when ___."
- **What you'd do all day if money and obligations were neutralized**

### Section 4: Dreamline summary

Don't run the full dreamline exercise here — that's the `dreamlining` skill. But capture the headline:

- **6-month dream** (1 sentence)
- **12-month dream** (1 sentence)
- **Target Monthly Income (TMI)** to fund the above (rough estimate is fine)
- **Target Daily Income (TDI)** — TMI / 30 (this is the number they should remember)

If they haven't done a dreamline, write "TBD — run /dreamlining" and point them there next.

### Section 5: New Rich criteria

The non-negotiables. The point of doing any of this.

- The 3 things you want **more** of
- The 3 things you want **less** of
- The 1 thing your current life makes hard that the new life must make easy
- The 1 thing you're afraid of losing if you change

### Section 6: Resources & assets (skip if early)

What you can leverage:

- Skills you can rent out (writing, design, code, sales, ops)
- Audience or network (size, type)
- Cash runway in months
- Existing income that could become semi-passive
- Existing business or product, if any

### Section 7: Status of each DEAL phase

A one-line self-assessment for each:

- **D — Definition**: Have you written down what you actually want? (Y / N / partial)
- **E — Elimination**: Have you cut the noise? (Y / N / partial)
- **A — Automation**: Is anything in your life or income automated? (Y / N / partial)
- **L — Liberation**: Are you geographically free? (Y / N / partial)

This tells later skills which phase to push you on.

## Format of the Saved File

Write the final document with these sections, even if some are empty. Empty sections are useful — they tell the next skill what's missing.

```markdown
# Lifestyle Design Context

_Last updated: YYYY-MM-DD_

## 1. Current state
...

## 2. Constraints
...

## 3. What I'm optimizing for
...

## 4. Dreamline summary
- 6mo: ...
- 12mo: ...
- TMI: $...
- TDI: $...

## 5. New Rich criteria
- More of: ...
- Less of: ...
- Must make easy: ...
- Afraid to lose: ...

## 6. Resources & assets
...

## 7. DEAL self-assessment
- D: ...
- E: ...
- A: ...
- L: ...
```

## After Saving

1. Confirm the file is saved and at which path.
2. Recommend a next skill based on what's missing:
   - No dreamline → `/dreamlining`
   - Dreamline done, never touched fear → `/fear-setting`
   - Has business idea → `/muse`
   - Drowning in email/work → `/eighty-twenty` then `/email-autoresponder`
3. Tell them they can rerun this skill any time their situation changes — and that they should, every 6 months minimum.

## What to Avoid

- Long therapy-style intake. Most sections are 1-3 sentences.
- Letting "I don't know" stand. "Best guess for now" is fine; vague is not.
- Filling in fields with cliches ("more balance," "less stress"). Push for specifics.
- Skipping section 5. The constraints + non-negotiables are what every other skill calibrates on.

## Related Skills

- **dreamlining** — The dreamline section above is a stub. The full exercise lives in dreamlining.
- **fear-setting** — Run after dreamlining on the scariest action implied.
- **new-rich-rules** — The mindset principles. Read once, reference often.
- **deal-framework** — The full DEAL walkthrough that uses this context.
