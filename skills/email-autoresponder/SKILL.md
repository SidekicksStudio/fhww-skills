---
name: email-autoresponder
description: Install Tim Ferriss's email policy from The 4-Hour Workweek — twice-a-day batched checking, autoresponder template that sets expectations, never check first thing in the morning, escalation path for true emergencies. Use when the user says "my inbox is destroying me," "I'm checking email 100 times a day," "set up an autoresponder," "Tim Ferriss email policy," "email batch," or "out of office for everyday use." Often the single highest-leverage skill in the entire system. Pairs with /batching and /interruption-killer; they reinforce each other.
metadata:
  version: 1.0.0
---

# Email Autoresponder + Email Policy

You are installing the email policy *The 4-Hour Workweek* recommends. For most users, this is the single highest-leverage productivity move in the book — bigger than any tool, app, or hack.

The policy has three parts:
1. **The schedule** — when email is checked
2. **The autoresponder** — what senders see in the meantime
3. **The exception path** — how true emergencies reach you

## Before Starting

Read `lifestyle-design.md` if it exists.

Ask the user:
- "How often are you checking email today, roughly? 5x? 50x? 100x?"
- "Do you have an autoresponder running now? What does it say?"

If the user has objections like "my job requires immediate response" — push gently. The number of jobs that genuinely require <30-min email response time is far smaller than people think. Most users overestimate by 10-100x.

## Step 1: The Schedule

Tim's default: **twice a day.** Once at ~11am, once at ~4pm. Calibrate to the user's life:

- Knowledge worker, US east coast → 11am, 4pm (Tim's default)
- International schedule → align to when responses actually need to be in
- Sales / customer-facing → may need 3x: 9am, noon, 4pm
- Founder of a small team → 2x is plenty, with one Slack-based emergency channel

The two non-negotiables:

1. **Not first thing in the morning.** The first 1-2 hours of the day are the only block where deep work is uncontested by other people's priorities. Burning them on email is a category mistake.
2. **Not last thing at night.** Late-night email creates middle-of-the-night anxiety loops. Stop checking by ~6pm.

Get the user to commit to specific times. Calendar them.

## Step 2: The Autoresponder

A good autoresponder does three jobs:

1. Tells the sender how long they'll wait
2. Tells them what to do if they need an answer faster
3. Sets the policy in language that doesn't make the sender feel devalued

Here's the **base template** (cribbed from Tim's various versions, then modernized). Customize the bracketed parts.

```
Hi —

Quick note on my email habits, since this is going to feel slow if
you don't know:

I check email twice a day, at 11am and 4pm Eastern. If you've
emailed me in between, I'll get back to you in the next batch.
Most things are answered within 24 hours.

If something is genuinely time-sensitive (true emergency, customer
escalation, deal-blocking), please:

  • [Phone / SMS — your number]
  • Or send a message to [colleague / partner / assistant who can
    triage], cc'ing me

Otherwise: thanks for your patience. This system lets me ship
real work for the people I work with — including, possibly, you.

— [Name]
```

Variants:

### For people running a business

Add a line above the emergency path:

```
For customer support, please reach [support@yourdomain.com] —
they're authorized and faster than I am.
```

### For people on a sabbatical / mini-retirement

```
Hi —

I'm on a 6-week mini-retirement and offline for most of it. I'll
check email roughly weekly on Sundays.

For [topic], please contact [colleague].
For [other topic], please contact [other person].
For anything time-sensitive, I unfortunately can't help — I'll be
back online [date].

— [Name]
```

### For employees who can't autoresponder all senders (e.g., internal-only)

For internal mail, set up a recurring Slack/Teams status:

```
Email windows: 11am + 4pm. Slack DMs faster (still batched).
Urgent: text [number].
```

And use the autoresponder only for external email or vacation.

### What the autoresponder should NOT do

- Apologize.
- Use "Sorry for the delay."
- Promise specific reply times you can't guarantee.
- Sound corporate or HR-written.
- Be longer than the template above.

## Step 3: The Exception Path

The autoresponder must give a real path for genuine emergencies. Without it, two things happen: senders panic, and the user gets blamed for "being unreachable."

The exception path is **not** "another email" — it has to be a different channel:

- A phone number (best for adults; second-best for everyone)
- A specific colleague who can triage
- A specific Slack channel with a real on-call rotation
- An SMS shortcode

**The trick that makes this work**: Make the alternative path *slightly inconvenient* — phone, not chat; person-to-person, not message — so it self-filters. People who genuinely need an immediate answer will use it. People who don't, won't.

## Step 4: First-72-hours implementation

Walk the user through these specific steps:

1. **Today**: Set up the autoresponder, calendar the 2 daily email windows, **uninstall the email app from your phone** (yes, really — at least for the trial period).
2. **Day 2**: When the urge to check hits outside the windows, write down what you wanted to look for. Don't check.
3. **Day 3**: Review the list of "what I wanted to look for." Almost always: nothing was real.
4. **Day 5**: Adjust the autoresponder if needed (lots of confused replies? simplify the language).
5. **Day 7**: Decide whether to keep or evolve. Most users keep it.

## Step 5: The colleagues / clients conversation

Some users worry about how the autoresponder will land socially. The conversation script:

For a boss / important client:
> "I'm trying something for the next two weeks — checking email twice a day instead of constantly — to ship real work. The autoresponder will tell people how to reach me if it's actually urgent. If you ever need me faster, [phone / specific channel] gets straight through. This is in service of getting more done for you, not less."

Most people are fine with it. The few who push back are usually the ones the user shouldn't be optimizing for anyway.

## Save the Output

Write `email-policy.md`:

```markdown
# Email Policy

_Installed: YYYY-MM-DD_

## Schedule
- Window 1: [11:00 AM]
- Window 2: [4:00 PM]
- Hard cap each: 30 min

## Autoresponder text
[full text, ready to paste into Gmail/Outlook/Apple Mail]

## Emergency channel
- [phone / colleague / Slack channel]

## Phone setup
- Email app uninstalled from phone: [Y/N]
- Push notifications off: [Y/N]
- Notification preview off (for SMS): [Y/N]

## Exceptions / on-call
- [If applicable: specific roles / accounts that bypass the policy]

## 7-day check-in note
[after week 1 — what worked, what didn't, what to change]
```

## Common Failure Modes

- **Not actually setting the autoresponder.** Talking about it, not installing it. Force the user to set it up live.
- **Checking "just once" outside the window.** This is an addiction; treat it like one. The discomfort lasts about 4 days.
- **Long, apologetic autoresponder.** Sounds defensive, invites more anxiety from senders. Short and matter-of-fact wins.
- **Phone email app still installed.** Removing it is the single most predictive change.
- **No emergency path.** People feel abandoned and escalate other ways.

## What to Avoid

- Setting up the autoresponder, then disabling it after one bad day. The system requires 7+ days to settle. Commit upfront.
- Making the policy passive-aggressive ("if you really need me" phrased as an attack). Be matter-of-fact.
- Ignoring the team / boss conversation. Surprise policy changes break trust; pre-warned ones don't.

## Related Skills

- **batching** — Email is one batch; this policy is the rules of that batch.
- **interruption-killer** — Email is the canonical category-2 interruption.
- **not-to-do-list** — "Don't check email first thing" is usually the #1 entry.
- **low-info-diet** — Email is part of the broader information diet.
- **mini-retirement** — The autoresponder is also the on-ramp for any extended absence.
