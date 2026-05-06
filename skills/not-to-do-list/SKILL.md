---
name: not-to-do-list
description: Build a personalized not-to-do list — Tim Ferriss's inversion of the to-do list, drawing on the 9 habits to eliminate from The 4-Hour Workweek and Tim's later "Not-To-Do List" post. Use when the user says "I have too many to-dos," "what should I stop doing," "I keep doing things I shouldn't," "not-to-do list," or after running /eighty-twenty (the cuts naturally become not-to-dos). Generates a written list of explicit "stop" rules with the trigger that prompted each, posted somewhere visible. Pairs with low-info-diet, batching, and email-autoresponder.
metadata:
  version: 1.0.0
---

# Not-To-Do List

You are helping the user build a **not-to-do list** — Tim's inverted, often more important counterpart to the daily to-do list.

The argument: most people optimize what they do without ever auditing what they keep doing by default. The not-to-do list is the explicit set of rules that protect the user from the most common, most expensive, most invisible time and energy leaks.

This skill produces a **personalized, written list** with:
1. The rule (what to stop)
2. The trigger (the specific cue that used to make the user do it)
3. The replacement behavior (what to do *instead* when the trigger fires)

## Before Starting

Read `lifestyle-design.md` if it exists.

If the user has already run `/eighty-twenty`, the bottom-20% items often translate directly into not-to-do rules — start from those.

If they haven't, walk them through the **9 starter rules** below and force a personalized version of each.

## The 9 Starter Rules

These are Tim's recurring not-to-do principles. Walk through each. For each, ask: *"Does this apply to you? In what specific form?"* Capture the user's answer.

### 1. Do not answer calls from unknown numbers.

For the user: when does this happen? What's the modern equivalent (random Slack DMs from people you don't work with, LinkedIn DMs)? What's the rule going to be?

### 2. Do not check email first thing in the morning, or last thing at night.

This is the highest-leverage one for most users. The first 1-2 hours of the day are the only block where deep work is uncontested by other people's priorities. Burning them on email is a category mistake.

For the user: what's the new policy? When can email be checked at the earliest? When at the latest?

### 3. Do not agree to meetings or calls without a clear agenda or end time.

The default meeting is "30 min, no agenda" — which expands into 30+ min and produces no decision. Force agendas. Force end times.

For the user: write the **two responses** — one polite, one firm — to "do you have time for a quick call?"

> Polite: "Sure — can you send me what you'd like to decide on first? Helps me come prepared and keep it tight."
>
> Firm: "Happy to. What's the decision we're making, and is 15 min enough?"

### 4. Do not let people ramble. Cut to the point.

People who don't know what they want will eat your hour. The polite interrupt:

> "Sorry to jump in — what's the ask, just so I make sure I'm useful?"

Use early. Use often.

### 5. Do not check email constantly. Batch.

The ongoing rule from `/email-autoresponder`. Two checks per day, calendar-blocked.

### 6. Do not over-communicate with low-profit, high-maintenance customers / collaborators.

This is the 80/20 of communication. The bottom 20% of relationships consume 80% of communication time. Ration accordingly.

For the user: name 1-2 people who fit this pattern. What's the new policy with them — slower replies, weekly batched updates, an autoresponder?

### 7. Do not work more to fix overwhelm. Prioritize ruthlessly.

When overwhelmed, the instinct is "more hours." The right move is "fewer items." Adding hours to a 7-priority week makes it a 7-priority week with longer days. Cutting to 1 priority makes it a 1-priority week.

For the user: what's the rule for what they do on overwhelm days? (Common: "If overwhelmed, cut the list to 1 item before adding any hours.")

### 8. Do not carry a phone or smartphone 24/7.

Modern translation: the phone is not in the bedroom; the laptop is not on the dinner table; one full day per week (or evening per day) is a no-screen window.

For the user: what's the personalized rule? When and where is the phone explicitly off-limits?

### 9. Do not expect work to fill a void that non-work relationships and activities should.

This is the hardest one and the most important. Work expanding to fill emotional gaps in life is a permanent treadmill.

For the user: ask gently — is there a category in their life (a friendship, a hobby, a creative practice, a physical practice) that has been quietly absorbed by work? What's the rule that protects it going forward?

## Step 2: Add the user's own

After the 9 starters, ask:

> "What are 3 things you keep doing that you keep telling yourself you should stop?"

Capture them. Each becomes a rule, with a trigger and a replacement.

## Step 3: For each rule, define the trigger and replacement

A rule without a trigger is a hope. With a trigger, it's a habit.

For each rule:

```
Rule:        Don't [X]
Trigger:     When [specific situation/cue/time/feeling]
Replacement: Instead, [specific alternative behavior]
```

Examples:

```
Rule:        Don't check email first thing in the morning
Trigger:     When I wake up and reach for my phone
Replacement: Phone is in the kitchen overnight. First action is making coffee
             and writing one sentence about today's #1 priority.
```

```
Rule:        Don't agree to meetings without an agenda
Trigger:     When someone Slacks "got 30 minutes?"
Replacement: Reply with: "Sure — what's the decision we're making? Often a 
             5-min Loom or a couple Slack messages does it."
```

```
Rule:        Don't over-communicate with [client name]
Trigger:     When they email more than 1x/day
Replacement: Reply with: "Looping back to you Friday with a digest — keeps 
             us focused." File the rest in a "weekly" label.
```

## Step 4: Make it visible

The not-to-do list dies in private. Pick at least one of:

- Print it. Tape it to the desk.
- Pin it as a Slack pinned message in the user's #me channel.
- Set it as a daily 8:30am calendar event.
- Add it as a startup item in their notes app.
- Tell one friend or partner. Permission to call out violations.

## Save the Output

Write `not-to-do.md`:

```markdown
# Not-To-Do List

_Last updated: YYYY-MM-DD_

## Rules

### 1. Don't [X]
- Trigger: ...
- Replacement: ...

### 2. Don't [X]
- Trigger: ...
- Replacement: ...

(repeat for all rules)

## Visibility
This list is posted at: [location]
Reviewed every: [cadence — weekly recommended]

## Violations log
| Date | Which rule | What happened | Update? |
|---|---|---|---|
| ... | ... | ... | ... |
```

## Common Failure Modes

- **Too many rules at once.** 5-8 rules is plenty. More than 12 = the user remembers none.
- **No trigger.** Rule with no trigger gets ignored. Force the trigger.
- **No replacement.** Just "stop X" without "start Y" creates a vacuum that fills with the original behavior.
- **Hidden list.** If it isn't visible at the moment of trigger, it does nothing.
- **Perfectionism.** The list is updated. The first version is wrong about something. Iterate every 2 weeks for the first 2 months, then every 6 months.

## What to Avoid

- Negative-only framing for everything. A few "stop" rules are fine; if every rule is a stop, the user feels constrained, not liberated.
- Adding "be more present" type rules. Vague. Make rules concrete.
- Treating the list as a moral commitment. It's an operating policy. When it stops serving, change it.

## Related Skills

- **eighty-twenty** — The audit that produces the most natural not-to-dos.
- **low-info-diet** — Many not-to-do rules will be about consumption.
- **email-autoresponder** — The email policy is itself 2-3 not-to-do rules.
- **interruption-killer** — Most rules will name a specific interruption pattern.
- **batching** — Several rules will be "don't do X scattered through the day; do it in a batch."
