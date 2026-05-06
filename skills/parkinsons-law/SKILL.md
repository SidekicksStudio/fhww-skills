---
name: parkinsons-law
description: Apply Parkinson's Law to a project, deliverable, or week — work expands to fill the time available, so shrink the time available. From the Elimination chapter of The 4-Hour Workweek. Use when the user says "I have too much to do," "this is taking forever," "what should my deadline be," "compress this project," "8 hour workday is too long," or "I'm working evenings and still behind." Also use as the second move after /eighty-twenty — once you know the 20% that matters, force it into a tight window. Pairs with batching and email-autoresponder for compounding effect.
metadata:
  version: 1.0.0
---

# Parkinson's Law

You are helping the user apply **Parkinson's Law** to a specific project, week, or deliverable.

The law (C. Northcote Parkinson, 1955): **Work expands so as to fill the time available for its completion.**

The 4-Hour Workweek lesson: this works in reverse. Shrink the time, and the work shrinks with it — usually by cutting low-value steps the user wouldn't have cut otherwise. Combined with 80/20, the multiplier is enormous: do the 20% that matters, in 20% of the time, and everything else falls away.

## Before Starting

Get the user to name **one** of the following to work on. Force a single target:

- A project deadline currently set to X — to be shrunk to Y
- A weekly schedule of N hours — to be cut to M hours
- A single deliverable currently estimated at H hours — to be capped at h hours

If they want to apply it to "everything I do," push back: pick one. Once they see it work once, they'll apply it elsewhere.

## The Exercise

### Step 1: State the current deadline

Ask the user, in one line: "What's the project, the current deadline, and how many working hours you've allocated?"

Examples:
- "Q3 marketing plan, due end of month, ~40 hours allocated."
- "Resigning from my job — currently 'this fall.'"
- "Writing the 8-week launch announcement — currently 3 weeks of writing time."

### Step 2: Halve it. Then halve it again.

Ask: "If you had to do this in **half** the time, what would you cut?"

Wait for the answer. Note what gets cut. Often it's: meetings, draft revisions, edge cases, "polish," peer review, gold-plating.

Ask: "And in **half of that** — a quarter of the original — what would you cut?"

This is where it gets uncomfortable. The cuts that come out at this level are the **80/20 of the work** — the steps that aren't actually load-bearing.

Examples:
- 40 hours → 20 hours: "I'd skip the all-hands review and the second draft."
- 20 hours → 10 hours: "I'd write a 1-pager instead of a 12-pager and just send it."

The 1-pager often turns out to be all that's actually needed.

### Step 3: Set the new deadline

Force a date *and a time*.

> "When are you committing to having this done by? Be specific. 'By Friday' is not enough — by Friday at what time."

Pin it. Calendar it. State it out loud (write it back to them).

The new deadline must satisfy two conditions:
1. **Aggressive enough to make you change your approach.** If the new deadline is 80% of the old one, you'll just hurry — not change tactics.
2. **Real enough to be public.** Tell at least one other person about the new deadline. Public commitment compounds.

### Step 4: Identify what gets cut, explicitly

Help the user write a **bullet list of what they will deliberately not do** to hit the new deadline.

```
To hit [new deadline], I am explicitly skipping:
- ...
- ...
- ...

If anyone pushes back on these cuts, I will say:
"[one-line response]"
```

Most pushback comes from the user themselves, internalized as the imagined disapproval of someone else. Naming who and pre-writing the response defangs it.

### Step 5: Set the kill criteria

If the work isn't done by the new deadline, what happens?

> "On [date+time], regardless of whether this is done — what gets shipped?"

Often the answer is "the v1 as it stands at that moment." This is usually the right answer.

If the user can't accept "ship what's done at the deadline," push back: the deadline isn't real, and Parkinson's Law won't bind.

## Two Combinations Worth Knowing

### Combination 1: Parkinson's × 80/20

After running `/eighty-twenty`, the user has identified the 20% of activities that produce 80% of value. Apply Parkinson's Law to *just that 20%* — give it the tight deadline. The other 80% has effectively been killed already.

**The Tim Ferriss multiplier**:
- Do the 20% (E → kept) in 20% of original time (P → shrunk)
- Net output: same value, ~4-5% of original time

### Combination 2: Parkinson's × Batching

If a recurring task is consuming time scattered through the week, batch it into one block, then apply Parkinson's to the block. (E.g., email twice a day at 11am and 4pm, 30 minutes each, hard cap.)

## Worked Example

**Original**: "I need 3 weeks to launch this product page. There's the copy, the design, the dev, the analytics tracking, the email sequence, the launch announcement..."

**Halved (1.5 weeks)**: "I'd skip A/B testing on the page and use one variation. I'd reuse the existing email template instead of designing a new one. I'd do tracking with off-the-shelf events instead of custom."

**Quartered (3-4 days)**: "I'd write the page myself in a Notion doc and ship it as a Carrd. I'd send one launch email instead of a sequence. I'd skip the announcement post and just post in two specific Slacks."

**What was learned**: Most of the original 3 weeks was process, not product. The 3-4 day version is what should ship, then add what's missing if and when conversion data demands it.

## Save the Output

Write `parkinsons-[project-slug]-[date].md`:

```markdown
# Parkinson's Law: [project]

_Date: YYYY-MM-DD_

## Original
- Deadline: ...
- Hours allocated: ...

## Halved
- New deadline: ...
- What was cut: ...

## Quartered
- Final deadline: ...
- What was cut: ...

## What I'm not doing (deliberately)
- ...
- ...

## If anyone pushes back
[one-line response]

## Kill criteria
On [date + time], shipping: [what gets shipped regardless]
```

## Common Failure Modes

- **"Aggressive but reasonable" deadline.** That's the old deadline with anxiety. The new deadline must require a different approach to hit.
- **Private deadline only.** Tell someone. Calendar it. Don't keep it in your head.
- **No explicit "not doing" list.** Without it, the cuts get re-added under stress.
- **Skipping kill criteria.** "I'll just push it if I'm not done" undoes the whole exercise.

## What to Avoid

- Letting the user pretend "I work better under pressure" is the same as Parkinson's Law. Pressure without specific cuts is just stress with the same workload.
- Applying it to learning. Skill development is a different curve — Parkinson's only really works on output.
- Using this on your therapist's appointment. There are categories of work where rushing is harmful. Use judgment.

## Related Skills

- **eighty-twenty** — Identifies *what* deserves the tight deadline. Pair them.
- **batching** — Group the work first, then time-cap the batch.
- **not-to-do-list** — The "deliberately not doing" list often becomes permanent rules.
- **email-autoresponder** — Email is the canonical Parkinson's target. Tim's two-checks-per-day is Parkinson's law on inbox time.
