---
name: make-it-a-skill
description: Turn a recurring task into a reusable Claude skill or scheduled task — the 2026 "never do the same thing twice" move. Wraps Anthropic's skill-creator (for skills you invoke yourself) and schedule (for tasks that run on their own) into one decision flow. Use when the user says "I keep doing this every week," "make this a skill," "automate this on a cron," "schedule this," "save this as a workflow," "wrap this as a tool," "I want this to run by itself," or after /automate-first lands on Gate 6 (skill or scheduled task). Distinguishes skill vs. scheduled task vs. both, walks through the build, and registers it.
metadata:
  version: 1.0.0
---

# Make It A Skill

You are helping the user wrap a recurring task into something reusable: a **Claude skill** they can invoke, a **scheduled task** that runs on its own, or both.

The 2-Minute Work Week principle: the second time you do something is a bug. By the third, you've cost yourself permanent overhead. The fix is not "be more productive" — it's "convert the work into something that doesn't need you next time."

## Two Things This Skill Wraps

There are two distinct primitives the user might want, and they get confused all the time. Untangle them up front.

### A) A Claude skill

A skill is a markdown file with structured instructions that Claude (or any compatible agent) loads when triggered. It is **invoked by the user** (or another skill) when needed.

Best for: tasks that the user does on demand but always the same way.

Examples:
- "Write a status update from these inputs"
- "Review this PR for our coding conventions"
- "Summarize this meeting transcript with our format"
- "Triage this support ticket per our rules"

Tool: Anthropic's **`skill-creator`** skill (already available in your environment if you see "skill-creator" in your available skills list).

### B) A scheduled task

A scheduled task is something that **runs by itself** on a cadence (or trigger), without the user invoking it.

Best for: things that should happen on a clock — without you remembering to push the button.

Examples:
- "Every Monday 7am, summarize last week's metrics and post to Slack"
- "Every morning at 8am, brief me on overnight emails"
- "Every Friday at 4pm, generate the weekly invoice draft"
- "When this webhook fires, run this triage flow"

Tool: Anthropic's **`schedule`** skill (already available in your environment).

### Often, you want both

Powerful pattern: a scheduled task that, on its cadence, **invokes a skill**. The skill carries the structured behavior; the schedule controls when.

Example: A `weekly-metrics-digest` skill that knows how to fetch, format, and post — invoked by a scheduled task every Monday 7am. If the format ever needs to change, you edit the skill, and the schedule keeps firing.

## Before Starting

Get from the user, in one message:

1. **The task** in one sentence
2. **Inputs** — what does it consume? (a file, a date range, an event, a list, free text)
3. **Outputs** — what does it produce? (a doc, a Slack message, an email, an artifact)
4. **Trigger** — how does it start? (user invokes manually / on a cadence / on an event)
5. **Frequency** — once a week, daily, every time X happens

If the user is mid-`/automate-first`, they already have most of this. Pull from their decision output.

## Step 1: Skill or scheduled — or both?

Map their answers to the right primitive:

| Trigger | Frequency | Choose |
|---|---|---|
| User invokes ("hey Claude, do this") | irregular | **Skill only** |
| Time-based ("every Monday at 7am") | recurring | **Scheduled task** (which may invoke a skill) |
| Event-based ("when X happens") | recurring | **Scheduled task** wired to a webhook/event source |
| Mixed ("usually scheduled but sometimes manually") | recurring | **Both** — skill + scheduled task that calls it |

If the answer is "scheduled task only" with no underlying skill, ask: would the structured behavior be useful to invoke manually too? If yes, build the skill first, schedule it second.

## Step 2: For Claude skills — invoke skill-creator

If the route includes a Claude skill:

1. **Tell the user** you're going to use Anthropic's `skill-creator` skill to build it.
2. Hand off to that skill with the user's inputs ready:
   - **Skill name** (lowercase, hyphens, matches dir): suggest based on the task. e.g., `weekly-metrics-digest`, `pr-review-guide`, `meeting-summary`
   - **Description** (1-1024 chars, with trigger phrases): the skill-creator will draft this; review with the user
   - **Body**: the procedure — what the skill should do step by step

3. Critical inputs the skill-creator will need:
   - **The exact procedure** the user wants run, written in numbered steps
   - **The format of the output**
   - **Any rules / constraints / "always do," "never do"**
   - **Examples** (1-3 of inputs and outputs that exist already are gold)

4. After skill-creator finishes, verify:
   - Frontmatter is valid (`name` matches dir; `description` has trigger phrases)
   - SKILL.md is under 500 lines
   - The skill references the user's existing context files where useful (`lifestyle-design.md`, `dreamline.md`)

5. **Test the skill once with real inputs** before declaring done. The first run reveals the missing instructions.

If `skill-creator` isn't available in this environment, fall back to writing the SKILL.md by hand following the format in any of this repo's existing skills.

## Step 3: For scheduled tasks — invoke schedule

If the route includes a scheduled task:

1. **Tell the user** you're going to use Anthropic's `schedule` skill to build it.
2. Hand off with the user's inputs:
   - **Cadence** (e.g., "every Monday 7am Eastern", "daily at 8am", "first business day of the month")
   - **Action** — what the task does. Two flavors:
     - **Inline action** — direct prompt + tools to use
     - **Invoke a skill** — call the skill the user just built in Step 2
   - **Output destination** — where the result goes (Slack, email, file in workspace, scratchpad)
   - **Failure handling** — what to do if the run fails (notify, retry, silent)

3. After `schedule` finishes, verify:
   - The schedule is actually registered (run a list to confirm)
   - The first run is on the calendar
   - The user knows how to disable / edit / delete it later

4. **Run the scheduled task once on demand** to make sure it works before letting it run automatically.

If `schedule` isn't available, fall back to a cron job, a GitHub Action on a schedule, or a Vercel cron — but those are environment-dependent.

## Step 4: Document where it lives

Most people lose track of their own automations. Maintain a single index file: `automations.md`.

```markdown
# Automations Index

_Last updated: YYYY-MM-DD_

## Skills I built
- `weekly-metrics-digest` — formats Monday metrics. Invoked by: scheduled task below.
- `pr-review` — code review against our conventions. Invoked: manually.
- `meeting-summary` — formats Loom / transcript into our notes template.

## Scheduled tasks
- `monday-metrics-digest` — runs Monday 7am ET; invokes `weekly-metrics-digest` skill; posts to #leadership.
- `morning-email-brief` — runs 8am daily; summarizes overnight emails; emails me.
- `monthly-invoice-draft` — runs first Tuesday of month; drafts in Google Doc.

## Scripts
- `stripe-crm-reconcile.py` — runs locally on demand. Path: ~/code/scripts/.
- `download-organize.sh` — runs on file-system trigger. Path: ~/scripts/.

## Status
- All running ✅
- One broken — `morning-email-brief` (auth expired, fix Tuesday)
```

## Step 5: The maintenance loop

Automations rot. They depend on APIs, formats, and contexts that change.

Schedule a **monthly automation review** — 30 minutes, last Friday of the month — to:

1. Check each scheduled task ran as expected
2. Verify outputs are still useful (not just landing in unread Slack threads)
3. Kill anything that's stopped serving
4. Note any new candidates from the last month's work

Make this review itself a scheduled task. (Of course.)

## A Walked Example

**The user says**: "Every Friday afternoon I write a weekly note to my team summarizing what shipped, what's next, what's blocked. It takes 45 minutes. I want to never do this again."

**Route**:

1. **Inputs**: list of merged PRs (GitHub), list of completed Linear tickets, list of upcoming work, list of blockers (Slack thread or doc).
2. **Outputs**: a Slack post in #team in the format the user already uses.
3. **Trigger**: Friday at 3pm Eastern. (Could also be manual on demand.)
4. **Frequency**: weekly.

**Decision**: **Skill + scheduled task.**

- Skill name: `weekly-team-update`
- Skill behavior: given lists of PRs / tickets / next work / blockers, produce the user's standard format.
- Scheduled task: Fridays 3pm ET, fetch the inputs (via GitHub + Linear MCPs or APIs), invoke `weekly-team-update` skill, post the output as a draft to user's DM (so they can edit + send), with a 30-min reminder.

**Build steps**:

1. Run `skill-creator` to author the skill (give it 2 examples of past updates as a stencil).
2. Run `schedule` to register the Friday cadence pointing to that skill.
3. Test: run the schedule manually on demand once. Check the output.
4. Add to `automations.md`.
5. The user's 45 min/week → ~3 min of review/edit. ~37 hours/year reclaimed.

## Save the Output

When done, save `make-it-a-skill-[task-slug]-[date].md`:

```markdown
# Made it a skill: [task name]

_Date: YYYY-MM-DD_

## Original task
[one sentence]

## Route
- Skill: [name] / [path]
- Schedule: [cadence] / [path or schedule ID]

## Build notes
- Examples used: ...
- Edge cases handled: ...
- Failure mode if it breaks: ...

## Verification
- [ ] Skill runs end-to-end on test input
- [ ] Schedule registered, next run = [date]
- [ ] Output destination confirmed
- [ ] automations.md updated

## Time saved
- Per occurrence: ... min
- Per year: ... hours
```

## Common Failure Modes

- **Building the skill before the procedure is stable.** If the user is still figuring out what they want, automating it locks in a half-baked version. Do the manual version 3-4 times first; only then automate.
- **Scheduled task with no failure handling.** Silent failures rot the most. Always have a notification path for "the task didn't run" or "the task ran but produced nothing."
- **No `automations.md` index.** Six months in, the user can't find their own automations. They get duplicates and rot.
- **Skipping the test run.** Schedule fires Monday 7am, posts garbage to a public channel. Test on demand first.
- **Building skills for one-off tasks.** Skill = repeated process. One-time → just do it (Gate 2 of `/automate-first`).

## What to Avoid

- Treating `skill-creator` and `schedule` as interchangeable. They are not. One is a wrapper for behavior; the other is a wrapper for *when*.
- Building a skill nobody but Claude can run. Make sure the skill works in the agent the user actually uses (Claude Code / Cowork / Cursor / etc.) — test in that environment.
- Letting the schedule become an interruption. A daily 8am brief that the user doesn't read is just spam they wrote themselves.

## Related Skills

- **automate-first** — The router. Lands on this skill when Gate 6 fires.
- **outsourcing** — When the task ultimately needs a human, not a skill. (See its Step 0 triage.)
- **deep-research** — For tasks that warrant a one-off agent run, not a permanent skill.
- **muse-launcher** — When the recurring task is "operate the muse," much of it ends up here.
- **batching** — Even automated tasks should fire on a batch cadence, not per event when avoidable.

## A Note on Anthropic Skills

This skill assumes you have access to Anthropic's `skill-creator` and `schedule` skills. If you do, this skill should call them rather than reinvent. If you don't, fall back to:

- **Skill-equivalent**: hand-write the SKILL.md following the format in this repo's other skills.
- **Schedule-equivalent**: cron, GitHub Actions, Vercel Cron, Cloudflare Workers Cron, or whatever scheduler your environment supports.
