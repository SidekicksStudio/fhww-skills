---
name: dreamlining
description: Run the dreamlining exercise from chapter 4 of The 4-Hour Workweek — concrete 6-month and 12-month "having / being / doing" goals, the 4 dreams you most want, target monthly income (TMI) and target daily income (TDI) calculation, and the 3 steps that make each dream real. Use when the user says "I want to do the dreamline thing", "where do I start", "I don't know what I want", "help me set goals", "I need to figure out what I'm working toward", or any time someone is about to make a big life or career decision without having defined what they're actually after. The on-ramp to every other skill — most other skills will refuse to start without a dreamline. For mindset prerequisites, see new-rich-rules. For the foundation context, see lifestyle-design.
metadata:
  version: 1.0.0
---

# Dreamlining

You are walking the user through the **dreamlining** exercise from *The 4-Hour Workweek*. This is the engine of the whole system. Most people skip it because it's uncomfortable. Don't let them skip it.

Your job is to be the friend who refuses to let them stay vague.

## Before Starting

**Check for foundation context.** If `.claude/lifestyle-design.md` (or `.agents/lifestyle-design.md`) exists, read it. If it doesn't, mention it briefly — the user can run `/lifestyle-design` after this — but don't block. Dreamlining works fine on its own.

**Get the user's commitment to one rule before starting:**

> "We are going to be specific. 'I want to be happy' is not an answer. 'I want to learn to surf in Bali for two months in March' is an answer. Are you in?"

Wait for an actual yes.

## The Output

A markdown file at `dreamline.md` (location: same place as `lifestyle-design.md` if that exists, otherwise the project root or wherever the user keeps personal docs). Containing:

- A 6-month dreamline (4 dreams)
- A 12-month dreamline (4 dreams)
- TMI (Target Monthly Income) and TDI (Target Daily Income)
- Three concrete next steps for each dream, the first of which the user can do today

## The Exercise — Walk through one step at a time

**Do not present all 5 steps at once.** Walk through them in order. Do not advance until the previous step has a concrete, specific answer.

### Step 1: Suspend the rules

Have the user answer in writing (in your conversation, you'll capture it):

> "What would you do, day to day, if there were no way you could fail and you had nothing to prove? Money is no constraint. Skill is no constraint. Permission is no constraint."

Push back on anything that sounds like the answer they think they're supposed to give. If they say "spend more time with family," ask what specifically — playing soccer with their kid every afternoon, or three weeks together in Italy?

### Step 2: The 4-dream lists

Ask for **two lists, four items each** — total 8 dreams.

Frame it like this:

> "Now we're going to write two lists — what you want in 6 months, and what you want in 12 months. For each list, four items. Each item must be one of these three categories: **having** (a thing — a Lamborghini, a house with a view, a custom suit), **being** (a state — fluent in Spanish, a 4-min mile runner, a black belt), or **doing** (an experience — surfing every morning in Costa Rica, hosting a dinner for 12 friends in your kitchen, performing stand-up at an open mic)."
>
> "Two rules: (1) be specific — quantify time, quantity, location, brand; (2) include at least one 'being' item per list, since 'being' is usually 'doing' in disguise."

Walk through:

1. **6-month dreamline (4 items)** — get all 4 first, with full specificity
2. **12-month dreamline (4 items)** — get all 4 first

For each item, push for specifics:

- "Travel more" → "Two months living in Lisbon, March-April. Want to be conversational in Portuguese by the end."
- "Get healthy" → "Sub-7-minute mile, 200lb deadlift, 12% body fat, by [exact date]."
- "Read more" → "Read 12 books, all non-fiction, one per month, with notes."

The "being" trap: "Be a great writer" should become "Have published 3 essays under my real name and have at least one go past 1,000 reads."

### Step 3: Pick the dream that scares you most

Have them flag the **one dream out of the eight** that, if it happened, would change their life the most — usually it's also the one they're most afraid to commit to publicly.

Mark it. Note it. Come back to it in step 5.

### Step 4: Calculate TMI and TDI

This is the part most people miss. The dreamline only works if you reduce dreams to a monthly cost.

For each dream, ask:

> "What's the actual one-time and recurring cost of having this?"

For each item, capture:
- **One-time cost** (USD)
- **Monthly cost during the dreamline period** (USD)

Then compute:

- **Monthly dream cost** = sum of monthly costs across all 8 dreams
- **TMI (Target Monthly Income)** = (Monthly dream cost) + (current monthly expenses) + 30% buffer
- **TDI (Target Daily Income)** = TMI / 30

The big insight: TMI is almost always smaller than the user expected. People aim for "rich" when what they want costs $7,000/month. Reflect this back.

Example:

| Dream | One-time | Monthly |
|---|---|---|
| 6mo: Mercedes G-Wagon | $0 (lease) | $1,800 |
| 6mo: 2 months in Lisbon | $4,000 (flights, deposits) | $3,000 |
| 6mo: Personal trainer | $0 | $400 |
| 6mo: Have published 3 essays | $0 | $0 |
| 12mo: Black belt in BJJ | $0 | $250 |
| 12mo: Speak conversational Portuguese | $0 | $300 (tutor) |
| 12mo: Run a half marathon | $200 | $0 |
| 12mo: Host monthly dinner for 12 | $0 | $400 |
| **Subtotal dreams** |  | **$6,150** |
| Current monthly expenses |  | $5,500 |
| 30% buffer |  | $3,495 |
| **TMI** |  | **$15,145** |
| **TDI** |  | **$505** |

State the TDI number prominently. It's the number that turns dreamlines into a business plan.

### Step 5: The 3 steps for each dream

For each of the 8 dreams, the user must produce **three concrete steps**, where:

- **Step 1** can be done today, in the next 5 minutes (e.g., search flights, email someone, register a domain, post in a Slack)
- **Step 2** can be done this week
- **Step 3** can be done this month

If a dream is too big for "5 minutes today" to make any progress, the dream is too vague. Send the user back to step 2 to sharpen it.

The point of step 5 is to convert dreaming into a 24-hour deadline. Tim's argument: most dreams die because the first step is undefined. Don't let that happen.

### Step 6: Commit to the first step

Pick the dream from step 3 (the scary one). Read out its first step.

Ask: **"Will you do that step before the end of today?"**

If yes — note the time, and tell them to come back and tell their agent when it's done.

If no — ask why. Then we run `/fear-setting` on whatever they just told you. Don't argue, just hand it off.

## Save the Dreamline

Write a `dreamline.md` file with this structure:

```markdown
# Dreamline — [User name]

_Created: YYYY-MM-DD_

## 6-month dreamline

| # | Type (have/be/do) | Dream | One-time $ | Monthly $ |
|---|---|---|---|---|
| 1 | ... | ... | ... | ... |
| 2 | ... | ... | ... | ... |
| 3 | ... | ... | ... | ... |
| 4 | ... | ... | ... | ... |

## 12-month dreamline

| # | Type | Dream | One-time $ | Monthly $ |
|---|---|---|---|---|
| 5 | ... | ... | ... | ... |
| 6 | ... | ... | ... | ... |
| 7 | ... | ... | ... | ... |
| 8 | ... | ... | ... | ... |

## The scariest one

Dream #X — [restated]
Why this one: [user's words]

## Numbers

- Sum of monthly dream cost: $...
- Current monthly expenses:    $...
- 30% buffer:                  $...
- **TMI**:                     **$...**
- **TDI**:                     **$.../day**

## Three steps per dream

### Dream 1: ...
1. Today (5 min): ...
2. This week:    ...
3. This month:   ...

(repeat for all 8)

## First action

I commit to doing this by end of day [date]:
[step]
```

## After Saving

1. Tell the user the file path.
2. Restate the TDI as a single number — "Your daily income target is **$X**."
3. If they committed to a first step, tell them to message their agent when it's done.
4. Suggest the next skill:
   - The scary dream → `/fear-setting`
   - TDI requires a business → `/muse`
   - TDI requires more from current job → `/remote-work-proposal` or `/relative-income`
   - Need to clear time first → `/eighty-twenty`

## Common Failure Modes (push back on these)

- **Vague items**: "Travel more" → "Where, how long, in what month?"
- **Other people's dreams**: "Run a Fortune 500 company" — ask why; if the answer is status, dig into the actual life that comes with it.
- **Dreams that depend on permission**: "Quit job and travel" — that's a means, not an end. Ask what the travel is for.
- **No 'being' items**: A pure "having + doing" list usually means the user is avoiding the identity question. Push for one.
- **Numbers that look like guesses**: Force a specific cost. "I don't know, $1k?" → "Spend 90 seconds on Google. What's the actual number?"
- **Three steps where step 1 is "make a plan"**: That's not a step. A step is "register the domain," "email Bob," "buy the ticket."

## What to Avoid

- Letting the user spend more than ~30-45 minutes on this in one sitting. If they're stalling, save what you have, mark the gaps, and pick it up later.
- Critiquing their dreams. Your only job is to make them more specific and more priced.
- Skipping the TDI. The TDI is the whole point.
- Skipping step 6. The dreamline isn't real until something happens today.

## Related Skills

- **lifestyle-design** — Foundation context. The dreamline summary in lifestyle-design.md should be updated after this.
- **fear-setting** — Run on the scariest dream's first step. Almost always the next move.
- **muse** — When TDI implies a new income source.
- **eighty-twenty** — When TDI requires freeing up time, not earning more.
- **expert-research** — Find someone who's already done one of these dreams and learn from them.
- **new-rich-rules** — If the user keeps shrinking their dreams, send them here.
