---
name: interruption-killer
description: Eliminate the three categories of interruption from The 4-Hour Workweek — time wasters, time consumers, and empowerment failures — each with its own scripted response. Use when the user says "I'm constantly interrupted," "drive-by questions," "people Slack me all day," "my team won't decide anything without me," "too many small asks," or after running /eighty-twenty (interruptions are usually how the bottom 20% steals time). Produces a playbook of scripts for redirecting each category and an empowerment policy that lets reports decide without you.
metadata:
  version: 1.0.0
---

# Interruption Killer

You are helping the user eliminate **interruptions** — the small, frequent, draining inputs that prevent any deep work.

Tim's framing in *The 4-Hour Workweek*: there are exactly **three categories** of interruption. Each has a different cause and a different response. Treat them all the same and nothing improves.

## The Three Categories

### 1. Time Wasters

Things that produce no value, regardless of how they're handled.

Examples:
- Group chat / non-essential email threads
- Unscheduled "drop-bys" with no agenda
- Ad-hoc meetings that didn't need to happen
- Most newsletters and feeds (this overlaps with `/low-info-diet`)
- The recurring Friday status meeting that has produced no decisions in 6 months

**Default response: ignore, unsubscribe, or decline.**

### 2. Time Consumers

Things that **must** happen but consume time disproportionate to their value, especially if scattered through the day.

Examples:
- Email and Slack DMs (real but batchable)
- Phone calls returning logistics questions
- Quick approvals
- Customer support
- Required meetings that produce real decisions

**Default response: batch them.** (Send the user to `/batching` if they haven't already.)

### 3. Empowerment Failures

The hardest category and usually the largest. Interruptions caused by **someone else not being authorized to decide without you**.

Examples:
- A team member asking "should I approve this $200 expense?"
- A contractor asking "is this color right?"
- An assistant asking "should I book this hotel or this hotel?"
- A direct report asking "should we accept this customer escalation?"

The interruption isn't really the question. The interruption is the **policy** that makes you the bottleneck for that decision.

**Default response: change the policy, not the answer.** Push the decision authority down.

## Before Starting

Read `lifestyle-design.md` if it exists.

Ask the user to **list 5-10 specific recent interruptions** — actual examples from this week. Real ones, not categories.

Examples to draw out:
- "Sarah asked me yesterday whether to send the proposal in PDF or Google Doc."
- "My contractor stopped progress to ask which font to use."
- "Three different people Slacked me to ask if I was OK with [thing]."
- "My boss came by my desk twice yesterday with 'quick' questions."

## Step 1: Categorize each one

For each interruption on the list, label it:

- **W** — time waster (produces nothing)
- **C** — time consumer (real, batchable)
- **E** — empowerment failure (someone else should have decided)

Use the working definitions above. Be honest: most users have far more E's than they realize.

## Step 2: For each category, install the response

### For W (time wasters)

The response is one of:

1. **Unsubscribe / leave** — group chats, mailing lists, recurring meetings with no decision output.
2. **Decline by default** — meeting invites without an agenda; "got 5 mins?" Slacks with no specified question.
3. **Polite decline script:**

   > "I don't think I'll be useful here — going to step out. Loop me back if a decision needs me."

For each W on the user's list, identify the action: unsubscribe, leave, decline, or skip.

### For C (time consumers)

Send the user to `/batching` and `/email-autoresponder` if not already done.

The two-line response:

> "Got this — I'll handle it in my next [email/admin/calls] batch at [time]. If it's actually urgent, [contact alternative]."

For each C, identify which batch it goes into.

### For E (empowerment failures) — THE CORE OF THIS SKILL

This is the highest-leverage move. Walk through it carefully.

For each E on the list, ask:

> "What's the underlying decision the person was asking about? Could a written rule have made the answer obvious?"

Then write the rule.

#### The empowerment rule format

```
Rule: [person/role] can decide [type of decision] up to [threshold]
      without checking with me, provided they [conditions if any].

Examples this would cover:
- ...
- ...

When this rule doesn't apply / escalate to me:
- ...
```

#### Worked examples

**Original interruption**: "Should I accept the customer's request for a refund on a $180 order?"

**Empowerment rule**:
```
Rule: Customer support can issue refunds up to $250 without asking,
      as long as the customer has not made the same complaint twice.

Examples this covers:
- One-time damaged-product refund
- Customer changed their mind within 30 days
- Shipping was 2+ weeks late

Escalate when:
- Same customer asking for a 2nd refund this quarter
- Refund > $250
- The complaint references our public claims
```

**Original interruption**: "Should I book the team to fly business or coach for the offsite?"

**Empowerment rule**:
```
Rule: Anyone can book travel for trips under 4 hours in coach with no approval.
      Business class for flights >6 hours; ask if it's between 4-6.

Default hotel: 4-star, under $250/night, walking distance to venue if possible.
```

**Original interruption**: "Should the expense for the Slack tier upgrade come from marketing or ops?"

**Empowerment rule**:
```
Rule: For software <$200/month, the requesting team's lead categorizes it
      to whichever budget makes sense. Reconcile quarterly. Don't ask.
```

#### Tim's "ask forgiveness" rule

For repeated low-stakes E interruptions, the most powerful rule is:

> "Default to acting. If you'd do it without thinking if you owned the company, do it. If you turn out to be wrong, we'll review it — and almost never undo it."

This single policy eliminates more interruption than anything else. Write it once. Send it to the team.

### Step 3: Communicate the policy

Empowerment doesn't work in your head. It has to be **written and shared**:

- For the team: a single document — "Decisions you can make without me" — pinned in the team's primary tool.
- For collaborators / contractors: a one-paragraph statement at the start of the engagement.
- For your boss / clients: harder, but possible — "I'm trying to handle X, Y, Z without bothering you. OK if I default to acting, and flag only edge cases?"

## Step 4: For your own internal interruptions

Self-interruption is the often-missed fourth category — the user opening a tab, reaching for the phone, switching to email mid-task.

Brief responses:

- Phone in another room during deep-work batches.
- Browser extensions that block specific sites during specific hours.
- A single physical object (notebook, sticky pad) where the user writes the distraction down ("look up X later") instead of acting on it.

This intersects with `/low-info-diet` and `/batching`.

## Save the Output

Write `interruptions-policy.md`:

```markdown
# Interruption Policy

_Last updated: YYYY-MM-DD_

## Time wasters (W) — to ignore/leave/decline
- ...

## Time consumers (C) — to batch
- Email → email batch (see batching-schedule.md)
- Slack → 3x daily windows
- Calls → office hours Tuesday

## Empowerment rules (E)

### Rule 1
[as above format]

### Rule 2
[...]

## "Ask forgiveness" default
[the team-wide statement, if applicable]

## Self-interruption rules
- Phone location during deep work: ...
- Browser blocks: ...
- Distraction notepad: ...
```

## Common Failure Modes

- **Treating empowerment failures as time consumers.** Batching the question doesn't help — the question shouldn't have been asked. Push the policy down.
- **Writing rules that are too restrictive.** "Spend up to $50 without approval" turns every $51 question back to the user. Set thresholds at the level where most decisions clear.
- **Telling the team but not writing it down.** Verbal empowerment has a half-life of about 10 days.
- **Failing to forgive predictable mistakes.** When someone uses the empowerment rule and gets it slightly wrong, do not retract. Adjust the rule, not the trust.
- **Pretending self-interruption isn't a category.** Often it's the biggest one.

## What to Avoid

- Punishing people for taking initiative under empowerment rules. The policy fails immediately.
- Being so focused on killing interruptions that the user becomes unreachable in genuinely urgent moments. Define what "actually urgent" means and how to reach you in those cases.
- Over-batching emergent issues. Some categories (incidents, security) deserve fast escalation.

## Related Skills

- **batching** — The home for category 2 (time consumers).
- **email-autoresponder** — Email is the canonical batched interruption.
- **outsourcing** — Empowerment rules are how you set up VAs and contractors well.
- **eighty-twenty** — The interruptions that survive review are usually concentrated among the bottom 20% of relationships and accounts.
- **not-to-do-list** — Many interruption rules become permanent not-to-do entries.
