---
name: batching
description: Identify what in the user's life can be batched — email, calls, errands, content creation, expense reports, social media, support tickets — to kill the switching cost that fragments most knowledge work. From the Elimination chapter of The 4-Hour Workweek. Use when the user says "I can't focus," "I'm context-switching all day," "where are my hours going," "batch my work," "deep work," "I'm always interrupted," or after running /eighty-twenty (kept items often need to be batched). Produces a weekly schedule with named batch windows and the rules that protect them.
metadata:
  version: 1.0.0
---

# Batching

You are helping the user identify and design **batches** — recurring time blocks that group similar tasks together to eliminate context-switching cost.

The premise: every switch between task types has a setup cost — physical (open the right tabs), cognitive (load the relevant context), and emotional (transition from one mode to another). For most knowledge workers, the setup cost is 10-25 minutes per switch. Eight switches a day = 2-3 hours of pure overhead the user never bills, never charges, never gets back.

Tim's argument: most things people do "as they come up" should instead be batched once or twice a week. Email is the canonical example, but it generalizes to almost everything.

## Before Starting

Read `lifestyle-design.md` if it exists.

Ask the user **what's fragmenting their week**. Common answers:
- Email (always batch this)
- Slack / chat
- Phone calls and short meetings
- Expense reports / invoicing
- Content creation (writing, posting)
- Customer support
- Errands and household admin
- 1:1s and check-ins
- Bookkeeping / financial admin

If they're unsure, walk them through a one-week mental log: "What did you do yesterday between 10am and 11am? 11am and noon?" The fragmentation will surface fast.

## Step 1: Inventory

For each candidate task type, capture:

- **Name** of the task type
- **Roughly how often it occurs in a week** (count, not hours)
- **How much time it takes per instance** (5 min, 15 min, etc.)
- **What the setup cost is each time** (loading context, switching apps, reframing)

Example:

| Task type | Occurrences/week | Time each | Setup cost |
|---|---|---|---|
| Email | 35-50 | 3-10 min | 5 min |
| Slack DM responses | 60+ | 1-3 min | 2 min |
| Quick calls / "syncs" | 8 | 30 min | 15 min |
| Expense entry | 12 | 5 min | 10 min |
| Posting on LinkedIn | 4 | 20 min | 20 min |

## Step 2: Compute the cost of not batching

Quick math: setup cost × occurrences = pure overhead per week.

In the example above:
- Email: 5 × 40 = 200 minutes = ~3.3 hours of weekly overhead
- Slack: 2 × 60 = 120 minutes = 2 hours
- Calls: 15 × 8 = 120 minutes = 2 hours
- Expenses: 10 × 12 = 120 minutes = 2 hours
- LinkedIn: 20 × 4 = 80 minutes = ~1.3 hours

**Total fragmentation tax: ~10 hours/week.** That's a full workday lost to switching.

State this to the user, in their own numbers. The math is what unlocks the willingness to batch.

## Step 3: Design the batches

For each task type, decide:

1. **Frequency** — how often per week the batch runs
2. **Duration** — how long each batch is
3. **Time of day** — when on the calendar
4. **Cap rule** — what happens if the batch overruns

Tim's defaults — calibrate as needed:

| Task type | Frequency | Duration | Time of day |
|---|---|---|---|
| Email | 2x/day | 30 min each | 11am, 4pm |
| Slack DMs | 3x/day | 15 min each | 10am, 1pm, 4pm |
| Quick calls | 1x/week | 90 min | Tue 2-3:30pm — "office hours" |
| Expense entry | 1x/week | 30 min | Friday 4pm |
| Content creation | 1x/week | 2-3 hours | Single morning, no interruptions |
| Customer support | 2x/day | 30 min | Same as email windows |
| Errands | 1x/week | 2 hours | Saturday morning |
| Financial admin | 1x/month | 90 min | First Monday of month |

Don't copy these. The user's own pattern matters more — but this anchors the conversation.

## Step 4: The protection rules

A batch only works if it is protected. Design the protection.

### Rule A — The default reply

For email/Slack/DMs, the user needs a one-line response when something arrives outside the window:

> "I check email at 11 and 4 — will get to this then."

For chat:

> "I'm heads-down on [project] until [time]. Will respond in a batch shortly after."

Most people are fine with this. The few who aren't are usually the ones the user shouldn't be optimizing for.

### Rule B — The autoresponder for email

See `/email-autoresponder` for the full template. Short version: a one-paragraph autoresponder that tells senders the policy, what to do for emergencies, and when they'll hear back.

### Rule C — Calendar blocking

Each batch is a calendar event with a real title. Not "focus time." Specific names:

- `Email batch — 11:00am`
- `Office hours — calls and quick syncs`
- `Content batch — LinkedIn posts (3)`
- `Friday admin — expenses + invoicing`

These blocks decline meeting invites by default.

### Rule D — The cap

Each batch has a duration. When the duration ends, the batch ends — even if the inbox isn't empty. Parkinson's Law applies: the inbox will compress to fit the window. (Run `/parkinsons-law` on this if needed.)

## Step 5: The hardest batch — content / creative work

Most users batch admin and miss the bigger win: batching **deep work**.

A 4-hour writing block once a week produces more than 4 separate 1-hour sessions, because the loading cost is paid once.

For each piece of weekly creative output the user has, set up a single batch window:

- Writing: one 3-hour session, weekly
- Recording: one 2-hour session, weekly (record 3-4 pieces of content at once)
- Strategy/planning: one 90-min session, weekly
- 1:1s: stack into a single afternoon, every other week

## Save the Output

Write `batching-schedule.md`:

```markdown
# Batching Schedule

_Last updated: YYYY-MM-DD_

## Fragmentation tax (before)
| Task | Switches/week | Setup cost | Weekly overhead |
|---|---|---|---|
| ... | ... | ... | ... |
| **Total** |  |  | ~X hrs/week |

## Batches

### Email
- When: 11:00am, 4:00pm daily
- Duration: 30 min each
- Cap: 30 min — anything not done waits

### Slack
- When: 10:00am, 1:00pm, 4:00pm
- Duration: 15 min each

### Office hours (calls, syncs)
- When: Tuesday 2:00–3:30pm
- Booking link: [link]

### Admin (expenses, invoices)
- When: Friday 4:00–4:30pm

### Content batch
- When: Wednesday 9:00am–noon
- Output: 3 LinkedIn posts + 1 newsletter

### [Add others]

## Protection rules
- Default email reply: "I check email at 11 and 4 — will respond then."
- Default Slack reply: "Heads-down until X — back then."
- Calendar blocks decline meeting invites by default.
- Autoresponder: see email-autoresponder.md

## Reclaimed time
Estimated: ~X hrs/week, redeployed to: [project / dream]
```

## Common Failure Modes

- **Batching everything immediately.** Pick 2-3 highest-fragmentation areas first. Land them. Then add more.
- **Soft-batching.** "I'll try to check email less" is not a batch. Without specific times and a calendar block, nothing changes.
- **Batches that are too long.** A 4-hour email batch is a misuse of the window. 30 min is the right cap for email.
- **No protection rules.** A batch that gets interrupted constantly isn't a batch.
- **Not redeploying the freed time.** The whole point is using the reclaimed hours for high-leverage work — not letting them leak back into busywork.

## What to Avoid

- Batching activities that genuinely do require continuous presence (your therapist's appointment, your kid's school pickup, sales calls already on the calendar).
- Letting one client or boss override the batches by force of habit. If someone genuinely needs synchronous response time, build that into their specific protocol — not into your default mode.
- Treating batching as productivity theater. It's only useful if the time saved goes somewhere that matters.

## Related Skills

- **email-autoresponder** — The autoresponder + checking schedule that protects the email batch.
- **interruption-killer** — Many interruptions are people violating your batch by accident. Scripts for redirecting them.
- **parkinsons-law** — Apply to each batch's duration cap.
- **eighty-twenty** — Items that survive the audit are usually candidates to be batched.
- **outsourcing** — Things that batch well also delegate well.
