---
name: eighty-twenty
description: Run an 80/20 (Pareto) audit on the user's customers, products, projects, time, or stress sources — the single most leverage-producing exercise in The 4-Hour Workweek (Elimination phase). Use when the user says "I'm overwhelmed," "where do I cut," "what should I focus on," "my customers are draining me," "too many priorities," "Pareto," "80/20," or any time they need to identify what's producing 80% of value vs. 80% of pain. Tim's two questions ("which 20% of sources are causing 80% of my problems / producing 80% of my desired outcomes") with the follow-on cuts and doublings. For deadline shrinking after the audit, see parkinsons-law. For converting findings into a no-list, see not-to-do-list.
metadata:
  version: 1.0.0
---

# 80/20 (Pareto) Audit

You are running an **80/20 audit** in the spirit of *The 4-Hour Workweek*'s Elimination chapter — Tim's most-cited move from the book. He used it twice on his own business and produced a 10x revenue jump while cutting hours.

The Pareto Principle (Vilfredo Pareto, ~1906): for many phenomena, ~80% of effects come from ~20% of causes. The exact numbers don't matter — the asymmetry does.

Tim's two questions:

> **Q1: Which 20% of sources are causing 80% of my problems and unhappiness?**
>
> **Q2: Which 20% of sources are producing 80% of my desired outcomes and happiness?**

Your job: get the user to answer both, ruthlessly, with names and numbers, and then act on the answers.

## Before Starting

Read `lifestyle-design.md` if it exists.

Ask the user **what we are auditing**. Common scopes:

- **Customers** — most useful for service businesses, freelancers, agency owners
- **Products / SKUs** — for product businesses
- **Projects** — for IC employees or consultants juggling multiple things
- **Time blocks** — for anyone overwhelmed
- **Stress sources** — for anyone burning out
- **Information / inputs** — feeds, newsletters, slacks (often a hidden 80/20 win)

Pick one. Don't audit everything at once. The skill is rerunnable — do it on customers today, products next week.

## The Audit — Walk through one step at a time

### Step 1: List the universe

Have the user list all the items in scope. For customers — every account. For projects — every active commitment. For time — a one-week timesheet by activity.

Don't skip this step. It is uncomfortable to look at the list. That's why most people skip it.

If the list is too big to enumerate (e.g., 800 customers), bucket it (top 20 by revenue, plus the rest in tiers) — but don't average it. Averages hide the 80/20.

### Step 2: Score each on two axes

For each item, score:

- **Value** — what it produces (revenue, learning, energy, joy, strategic position)
- **Cost** — what it takes (hours, stress, opportunity cost, emotional drain)

Use a simple 1-5 scale on both. Numbers are fine even if rough.

Add a third column when relevant:

- **Why I keep it** — the answer is often "habit" or "guilt."

### Step 3: Sort and look

Sort by value desc. Look at the top.

> "What do the top 20% have in common? What did you have to do, or what did the customer/product have to be, for it to land in this group?"

Capture the **pattern**.

Sort by cost desc, value asc. Look at the top.

> "What's eating you for no return? What pattern do they share?"

Capture the **anti-pattern**.

### Step 4: The cuts

For each item in the bottom 20% by value (or top by cost-to-value ratio), force a decision:

- **Fire** — full stop, stop doing/serving immediately
- **Raise the bar** — keep, but at 2-5x price, or with a sharply reduced scope (so they self-select out or self-select up)
- **Hand off** — keep alive, but transfer to someone else (junior, partner, agency)
- **Automate** — keep, but reduce your time to near-zero (template, FAQ, autoresponder)
- **Keep, with reasons** — only if the user can articulate a non-emotional reason

Tim's heuristic: when in doubt, fire. He famously cut two-thirds of his customers when he ran this audit on BrainQUICKEN. Revenue went up because he had time to focus on the top.

For the user, calibrate to risk tolerance — but call out when "keep with reasons" is being used as a hiding spot.

### Step 5: The doublings

For the top 20% by value:

> "If you only had this group, what would you do differently? More of the same? A larger product for the same buyer? Higher price? More acquisition focused on people who look like them?"

Capture **two specific things to double down on**.

The classic mistake is to be so satisfied with the cuts that the user forgets the second move — the cuts free up time that has to be redeployed, not absorbed.

### Step 6: The 30-day calendar

Help the user write the actual calendar of next 30 days:

- Week 1: send the firing emails / raise prices on bottom 20%
- Week 2: implement the doublings — first concrete actions
- Week 3: review what broke (something will)
- Week 4: re-audit, see whether the new top 20% is now producing more

## Save the Output

Write `eighty-twenty-[scope]-[date].md`:

```markdown
# 80/20 Audit: [scope]

_Date: YYYY-MM-DD_

## Items audited
[count + brief description]

## Scoreboard

| Item | Value (1-5) | Cost (1-5) | Action |
|---|---|---|---|
| ... | ... | ... | Keep & double |
| ... | ... | ... | Fire |
| ... | ... | ... | Raise the bar |
| ... | ... | ... | Hand off |
| ... | ... | ... | Automate |

## Top 20% pattern
[what the top items share]

## Bottom 20% / high-cost pattern
[what the worst items share]

## Cuts (this week)
- ...

## Doublings (this month)
- ...

## 30-day calendar
- Week 1: ...
- Week 2: ...
- Week 3: ...
- Week 4: re-audit
```

## Common Failure Modes

- **Spreadsheet trance.** Hours scoring, no decisions made. Cap the audit at 60 minutes total.
- **"I'll fire them later."** Set a date for the firing emails before closing the session.
- **Cutting and not doubling.** The freed-up time leaks back into busywork unless redeployed.
- **Ignoring the pain audit.** Q1 (sources of pain) is often more useful than Q2 (sources of value), but people skip it because it's uncomfortable.
- **Auditing too small a universe.** "I only have 4 projects" → consider auditing time blocks within projects instead.

## When the audit reveals something hard

Sometimes the top 20% reveals that **the user's most valuable customers / projects / activities are not the ones their identity is wrapped around.** Acknowledge it. Don't argue. Run `/fear-setting` on the implied next move (firing your favorite client, killing your favorite product, leaving your favorite project).

## What to Avoid

- Pretending one "value" axis captures everything. Sometimes a low-revenue customer is high-strategic-value (e.g., logo on the website). Capture it as a reason in column 3 — but be honest about whether it's real.
- Letting the user re-rank to protect the items they like. The first ranking is usually correct.
- Skipping the 30-day calendar. The point is action.

## Related Skills

- **parkinsons-law** — Once the surviving 20% is identified, shrink deadlines on it.
- **not-to-do-list** — Convert the cuts into permanent "stop" rules.
- **batching** — Group what's left.
- **outsourcing** — "Hand off" actions usually feed straight into outsourcing.
- **muse** — If the audit reveals one revenue line dominates, that's often the seed of the muse.
- **fear-setting** — When the audit's findings imply a hard action.
