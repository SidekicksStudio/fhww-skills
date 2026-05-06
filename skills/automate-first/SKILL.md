---
name: automate-first
description: The 2026 default-mode shift — before delegating, hiring, or doing-it-yourself, ask "what would it take to automate this with AI or a script." Decision tree that takes any task and routes it to the cheapest, fastest, most repeatable solution. Use when the user says "I need to do X," "I have to do this every week," "should I hire someone for this," "automate this," "two minute work week," "how do I never do this again," "what's the lazy way," or any time the user is about to commit human time to a task. Pairs with /outsourcing (which now defers to this for Step 0), /make-it-a-skill (for the wrap-as-reusable step), /deep-research (for one-shot AI runs), and /muse-launcher (for the muse-build version).
metadata:
  version: 1.0.0
---

# Automate First

You are running the **automate-first** decision tree on a single task the user is about to commit time to. The 2026 mindset shift: before you do, hire, or even delegate it — ask if AI or code can absorb it.

The 4-Hour Workweek's bias was "find a person to do this." The 2-Minute Work Week bias is "find a system to do this; only escalate to a person when the system can't."

This skill is the standalone version of `/outsourcing`'s Step 0. Run it any time you catch yourself adding to a to-do list or thinking "I need to hire someone for this."

## Before Starting

Get from the user, in one message:

1. **The task** in one sentence ("Reconcile invoices to Stripe charges for May")
2. **How often it occurs** (one-time, weekly, monthly, "every time X happens")
3. **What goes in and what comes out** (inputs and outputs — files, data, decisions)
4. **What about it actually requires you** (judgment? taste? legal signature? presence?)

If the answer to #4 is "honestly, nothing — I just always do it," that's almost always automatable.

## The Decision Tree

Walk through the gates **in order**. As soon as a gate matches, stop and route.

### Gate 1: Should this be done at all?

Before automating, ask whether the task survives an 80/20 audit. If the user can't say what value the task produces in one sentence, **don't automate it — kill it**.

Send to `/eighty-twenty` if there's any doubt. Automating the wrong work is worse than doing it manually because it makes the work permanent.

### Gate 2: Is this a one-time task?

If the task happens exactly once and never again — automation is wasted effort. The right answer is usually:

- **Single AI prompt** if it's a thinking/writing/summarizing task
- **30 minutes of focus** if it's small and tactile
- **One-shot AI agent run** if it's tedious-but-finite (see `/deep-research`)

**Stop here** if one-time. Don't over-engineer.

### Gate 3: Can a single AI prompt do this?

The 2-minute version. Test by asking: "If I paste this into Claude / ChatGPT / Gemini right now and add the inputs, would I get a useful answer?"

Examples that pass:
- Summarize, compare, translate, classify, extract, rewrite, draft
- Convert one format to another (messy CSV → clean schema)
- Generate variants (5 versions of a subject line)
- Simple analysis (what does this data say)
- Read a contract and flag deviations
- Write a routine response from a few inputs

If yes — that's the answer. Show the user the prompt template, run it once with them, and **stop here**.

### Gate 4: Can an AI agent run + tools do this?

If the task is "tedious-but-bounded" — needs to look at many sources, fetch data, compare, compile — but doesn't need ongoing presence:

- Researching across the web
- Pulling data from N sources and consolidating
- Running through a list of N items applying the same logic
- Reading a folder of files and producing a structured output
- Running a deep research agent on a question

If yes — see `/deep-research` for structuring the run. **Stop here.**

### Gate 5: Can AI write me a small script that does this forever?

If the task is structured, recurring, and the inputs/outputs are stable — the right answer is to spend 30-60 minutes (with Claude Code, Cursor, Codex, etc.) writing a script that does it on demand.

Telltale signs:
- "Every week, I do the same 3 steps"
- "I always pull from these 2 places and put it here"
- "I just need to rename / move / transform / log / send"
- Tactical glue work — files, APIs, spreadsheets, formatters, schedulers

If yes — write the script. Approximate scope:

| Task shape | Time to write with AI | Time to run forever after |
|---|---|---|
| Local file rename / dedupe / sort | 10-20 min | 0 sec |
| API → spreadsheet → notification | 30-60 min | runs on a cron |
| Webhook → conditional action | 30-60 min | instant |
| Browser automation (form fill, scrape) | 60-90 min | reusable |

Once the script exists, see Gate 6 — does it need to run on a schedule?

### Gate 6: Should this become a Claude skill or a scheduled task?

Two distinct questions, both yes-able:

**A) Should it be a Claude skill?**
If the task is something you'll *invoke yourself* repeatedly — "draft a status update from these inputs," "review this code with these conventions," "summarize this meeting transcript" — wrap it as a skill so future-you (or future Claude) does it the same way every time.

→ See `/make-it-a-skill` and Anthropic's `skill-creator`.

**B) Should it be a scheduled task?**
If the task should *run on its own* on some cadence — "every Monday morning, summarize last week's metrics" — make it a scheduled task.

→ See `/make-it-a-skill` and Anthropic's `schedule` skill.

A task can be both. ("Pull metrics on Monday → run my standup-summary skill on the result → post to Slack.")

### Gate 7: Does it need a human VA?

Only if **all** of the following are true:

- Gates 3-6 don't fit (it's not pure AI work)
- The task happens often enough to warrant human onboarding
- It needs real-world presence, judgment calibrated to you, or relationship continuity

Then — and only then — proceed to `/outsourcing`.

### Gate 8: Should I do it myself?

The forgotten gate. Some tasks should be done by the user, with no automation, no delegation:

- Tasks that are part of the user's actual creative work
- Decisions that compound over years
- Relationships where the back-and-forth IS the work
- Things small enough that automation is overhead

Don't talk the user out of doing the right things themselves.

## The Decision Output

Capture the routing as a one-liner per task:

```
Task: [one sentence]
Frequency: [one-time / weekly / monthly / triggered]
Route: [Kill / Single prompt / Agent run / Script / Skill / Scheduled / Human VA / DIY]
Why this route: [one sentence]
Next action: [the literal next step the user takes]
```

## A Walked Example

**Task**: "Every Sunday I look at the previous week's Stripe charges and make sure each one matches a real customer in our CRM. Takes me 90 minutes."

- Gate 1 — should this be done at all? Yes, anti-fraud + finance hygiene.
- Gate 2 — one-time? No, weekly forever.
- Gate 3 — single prompt? Could AI do it once with the data pasted in? Yes — but pasting the data is the work.
- Gate 4 — agent run? Could, but recurring → wasteful.
- Gate 5 — script? **Yes.** Stripe API + CRM API → run join → flag mismatches. ~45 min to write with Claude Code.
- Gate 6 — scheduled task? **Yes.** Run on Monday 7am, post a Slack message in #finance with mismatches. If zero mismatches, "All clear" message.

**Route**: Script + scheduled task. **Next action**: open Cursor / Claude Code, write the script. **Time recovered**: 90 min/week → ~75 hours/year.

The single most expensive sentence in the user's week is "I do this every Sunday." Find them. Burn them.

## Common Failure Modes

- **Skipping Gate 1.** Automating the wrong work is worse than doing it manually.
- **Stopping at Gate 7 by default.** Most users still default to "hire someone." That's the muscle memory this skill is rewiring.
- **Going to Gate 5 for one-time tasks.** Don't write a script for something that happens once. Just do it.
- **Treating AI agents as set-and-forget.** Especially Gates 4-6 need observability — log what the agent did, review weekly. Otherwise you don't know when it broke.
- **Ignoring Gate 8.** Sometimes the user is automating away the work they should be doing. Read the room.

## A Note On Scope

This skill is a **router**, not a builder. It tells the user *which path* to take. The actual building lives in:

- One-shot prompts → just run it
- AI agent runs → `/deep-research`
- Scripts → AI coding tools (Claude Code, Cursor, Codex)
- Skills → `/make-it-a-skill` + Anthropic's `skill-creator`
- Scheduled tasks → `/make-it-a-skill` + Anthropic's `schedule`
- Human VA → `/outsourcing`
- Muse-specific build → `/muse-launcher`

## Save the Output

If the user runs this on multiple tasks at once (often after `/eighty-twenty`), save `automate-first-decisions-[date].md`:

```markdown
# Automate-First Decisions

_Date: YYYY-MM-DD_

| Task | Frequency | Route | Why | Next action |
|---|---|---|---|---|
| ... | weekly | Script + scheduled | API call repeats forever | Write script today |
| ... | monthly | Single prompt | Just summarization | Save prompt as a snippet |
| ... | one-time | Agent run | Tedious but bounded | Run /deep-research |
| ... | weekly | Skill | I invoke this myself often | /make-it-a-skill |
| ... | irregular | Human VA | Needs phone calls | Add to /outsourcing list |
| ... | weekly | DIY | This IS my creative work | No change |
```

## Related Skills

- **outsourcing** — Defers to this skill in its Step 0. Run automate-first first; only land on outsourcing if Gate 7 fires.
- **make-it-a-skill** — When Gate 6 fires, this is where you go to build the skill or scheduled task.
- **deep-research** — When Gate 4 fires, this is the structured way to run an AI agent on a research-shaped task.
- **muse-launcher** — When the task is "build the launch infrastructure for my muse," that's a specialized version of this routing.
- **eighty-twenty** — Always run before automate-first if there's any doubt the task should exist at all.
- **not-to-do-list** — The most-automated category in the 2026 version is often "stop doing this entirely."
