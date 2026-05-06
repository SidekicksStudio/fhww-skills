---
name: outsourcing
description: Hand off work and life tasks — to AI first, scripts second, scheduled tasks third, and only then to a human VA or contractor. Updates Tim Ferriss's "Outsourcing Life" chapter from The 4-Hour Workweek for the 2026 reality where most "VA tasks" from the book can be done by an AI agent in 2 minutes. Use when the user says "I need a VA," "outsource this," "hire a virtual assistant," "delegate," "where do I find help," "what should I delegate first," or after running /eighty-twenty. Begins with an AI-first triage (Step 0) to route the task, then walks through the human-VA path if needed. For the standalone automate-or-delegate decision tree, see automate-first. For wrapping a recurring task as a reusable skill or scheduled task, see make-it-a-skill.
metadata:
  version: 2.0.0
---

# Outsourcing (AI-First)

You are walking the user through the modernized version of Tim's **Outsourcing Life** chapter. The book's principle is timeless: stop being the bottleneck, hand things off. The platform layer has shifted dramatically:

- 2007 (book era): every "hand it off" was to a human in another country
- 2026: most of the book's example tasks (research, summaries, data collection, logistics, drafts) are now done in 30-90 seconds by an AI agent — for fractions of a cent, with no onboarding

The 2-minute-work-week reframe: **outsourcing is now a hierarchy, not a single move**. Default to AI. Then scripts. Then scheduled tasks. Only then humans — and only for the things that genuinely require judgment, taste, real-world presence, or the kind of context AI still can't carry reliably.

## Before Starting

Read `lifestyle-design.md`. Specifically the user's TDI.

Read `eighty-twenty-*.md` if any 80/20 audits exist — items marked "hand off" go straight here.

## Step 0: The AI-First Triage

For each task the user wants to hand off, run it through this gate **before** considering a human VA. This is the highest-leverage step in the modern version of the skill.

### The 5 questions

For each task, ask in order:

**1. Can a single AI prompt do this?** (chat with Claude / ChatGPT / Gemini, send a file, get an answer back)
- "Summarize these 30 PDFs into a comparison table"
- "Draft 5 versions of this email"
- "Convert this messy spreadsheet into a clean schema"
- "Compare 10 SaaS pricing pages and extract the patterns"
- "Read this contract and flag clauses that deviate from typical"

If yes — that's a 2-minute outsourcing job. No VA needed. **Stop here.**

**2. Can a one-shot AI agent run do this?** (deploy Claude / Codex / Cursor / a deep-research run, with file or web access, to grind through it)
- "Find 30 wedding venues within 2 hours of [city] under $20K, with photos and capacity"
- "Compile every podcast that mentions [topic] in the last 12 months"
- "Find 10 Lisbon apartments matching my criteria, ranked"
- "Build a comparison matrix of every direct competitor's positioning"
- "Reconcile this month's invoices against this list of clients"

If yes — see `/deep-research`. **Stop here.**

**3. Could AI write me a small script that runs forever?** (then I never have to do this again)
- A scraper that runs weekly and emails me when it finds new listings
- A function that auto-tags my inbox by sender pattern
- A renamer that organizes my downloads folder
- A bot that posts a daily metric to Slack
- A workflow that turns transcripts into formatted notes

If yes — see `/make-it-a-skill` to wrap it as a Claude skill or scheduled task. **Stop here.**

**4. Is this recurring enough to warrant a scheduled task or Claude skill?** (something you'll do >5 times this year)
- Weekly status report drafting
- Monthly invoice reconciliation
- Daily news triage
- Quarterly data pull for a recurring report

If yes — see `/make-it-a-skill`. **Stop here.**

**5. Does this require physical presence, real-time human judgment, taste calibration with you, or a relationship you can't transfer?**
- Picking up a package
- Negotiating with a specific human counterparty whose trust matters
- Caring for a pet, plant, or person
- Decisions that require your face / voice / signature in a regulated context
- Creative direction where the back-and-forth IS the work

If yes — proceed to the human VA path below (Step 1 onward). This is the only legitimate "human VA" task in 2026.

### The default-mode shift

Tim's 2007 default: "what can I get a person to do for me?"

The 2026 default: "what can I get an AI to do for me, and what's the small subset that still needs a human?"

If after running the 5 questions, **80%+ of what the user was about to delegate to a VA can be handled by AI or a script**, that's normal. Tell them so. The remaining 20% is where the human VA path actually pays off.

### Examples — old book vs. 2026

| Book example | 2007 answer | 2026 answer |
|---|---|---|
| Research 10 stand-up paddleboards | Hire VA via Brickwork | Claude deep research, 90 seconds |
| Compile every podcast on a topic | VA, $40, 2 days | AI agent run, $2, 5 minutes |
| Inbox triage | VA, ongoing | A Claude skill + scheduled task |
| Travel research / booking | VA | Claude can compare options; you book in 5 min |
| Phone the cable company to negotiate | VA | Still a VA — phone, real-time, contextual |
| Doctor's office back-and-forth | VA | Still a VA — relationship + sensitive |
| Drafting first cuts of content | VA | AI does the draft; VA edits if needed |
| Image editing batches | VA on Photoshop | Photoroom / Claude / a script |
| Scheduling meetings (with rules) | VA | Calendly + Claude skill, no human |
| Customer support ticket triage | VA | AI categorizes; VA handles the 20% that needs judgment |

### Save the triage decision

Before going further, capture per task:

```
Task: ...
Triage: [AI prompt | AI agent | Script | Skill / scheduled | Human VA]
Reason: ...
```

Now — for tasks that landed on **Human VA** in step 0 — proceed.

## Step 1: Calibrate expectations

Tim's most-cited mistake from the book: people expect a VA to operate like an in-person executive assistant from day one. That's wrong.

**A new VA is a new hire**: you have to design the work, write down the procedures, and review the first 2-3 weeks closely. The payoff comes after that.

Tell the user upfront:

> "Plan for 2-4 weeks of setup before you see the time savings. After that, the leverage compounds. The first month, you'll feel like you're working harder, not less. Push through it — the curve is real."

## Step 2: What to delegate first

Walk the user through these candidate categories. For each, ask "Do you have any of this?" and capture specifics.

### A. Research

Anything that requires searching, comparing, summarizing, and not deciding.

- "Find me 10 stand-up paddleboards under $800 with reviews above 4.3, and rank by carry weight."
- "Compile every podcast that mentions [topic] in the last 12 months — title, link, episode #, 1-line summary."
- "Find 30 wedding venues within 2 hours of [city] under $20K, with photos and capacity."

These are the **best first tasks**. Low risk, easy to evaluate, immediately useful.

### B. Inbox + scheduling triage

- Initial scan of email — flagging and categorizing
- Calendaring meetings (with templates and rules)
- Booking travel within parameters
- Filling out forms

### C. Logistics

- Booking, rebooking, expense reports
- Subscriptions audit (cancel duplicates, downgrade unused)
- Insurance comparisons, bill negotiations
- Phone calls to companies you don't want to call (cable, airlines, customer service)

### D. Repeatable creative production

Carefully — only if you can write a clear brief.

- Drafting first cuts of content from a structured outline
- Cleaning up transcripts
- Formatting reports / decks from raw notes
- Image editing batches

### E. Personal life

- Gift research and ordering
- Restaurant reservations
- Doctor's office back-and-forth (with HIPAA caveats)
- Booking household services (cleaners, repairs)

### Tasks NOT to delegate (early)

- High-context, high-judgment work that _is_ the user's competitive edge
- Anything where one mistake is catastrophic (financial decisions, legal documents, medical decisions)
- Direct relationships you've cultivated personally
- The user's actual creative work (not formatting, but origination)
- Anything you can't write down clearly

A useful filter: **if you can't write the procedure for it in 30 minutes, you can't delegate it yet.** Either write the procedure, or keep it.

## Step 3: Where to find a VA

The book's specific recommendations (Brickwork, Brickbat) are dated. Modern equivalents:

| Tier                        | Service                                                         | Best for                          | Approx cost   |
| --------------------------- | --------------------------------------------------------------- | --------------------------------- | ------------- |
| Premium executive assistant | Athena, Persona, Double                                         | High-touch ongoing partnership    | $1500-3500/mo |
| Mid-tier dedicated VA       | MagicAssistants, Belay, Time etc.                               | 20-40 hrs/week, business support  | $800-2000/mo  |
| Hourly / project            | Upwork, Fiverr Pro                                              | One-off projects, specialty work  | $5-50/hr      |
| Specialty                   | Wing (research), Pareto (data ops), Boldly                      | Specific function                 | varies        |
| Niche VAs                   | Filipino-Indian-South-American direct hire (often via referral) | Long-term low-cost dedicated help | $5-15/hr      |

For a first-time user, Tim's advice still applies: start cheap and project-based. **Run a paid trial with 2 candidates simultaneously on the same task** before committing to one.

## Step 4: Writing a delegate-able task

This is the bottleneck for almost everyone. The format that works:

```
TASK: [one sentence — what's the outcome]

CONTEXT: [2-3 sentences — what's the bigger goal this fits into]

INSTRUCTIONS:
1. [step]
2. [step]
3. [step]

DEFINITION OF DONE:
- [specific, observable]
- [specific, observable]
- [specific, observable]

CONSTRAINTS / WATCH-OUTS:
- [things that often go wrong]
- [things you do not want]

DEADLINE: [specific time, with timezone]

CHECK-IN POLICY: [e.g., "ping me if anything is unclear; otherwise
                  send completed work to inbox by deadline"]

OUTPUT FORMAT: [how you want it delivered — Google Doc, spreadsheet,
                Slack message]
```

### Worked example

```
TASK: Find 10 candidate Lisbon apartments for a 6-week stay starting Sept 1, 2026.

CONTEXT: I'm relocating temporarily, traveling solo with a laptop. I want
quiet, walkable, decent natural light, and reliable WiFi (>100 Mbps). Budget
€2,000-€3,500/month all-in.

INSTRUCTIONS:
1. Search Idealista, Spotahome, Flatio, and AirBnB.
2. Filter to entire-place rentals in Príncipe Real, Estrela, Lapa, Chiado,
   or Alfama (avoid Bairro Alto — too loud).
3. For each candidate, capture in the spreadsheet:
   - Listing URL
   - Total monthly cost (rent + utilities + cleaning)
   - Square meters
   - Distance to nearest grocery (Google Maps walking)
   - WiFi speed if listed; if not, note "unknown — ask"
   - Cancellation policy
4. Stop at 10 strong candidates.

DEFINITION OF DONE:
- Spreadsheet has all 10 with every column filled (or "unknown" with note)
- Each row has the listing URL clickable
- A column at right ranks them by your top recommendation, 1-10

CONSTRAINTS:
- No basement units.
- No buildings >5 floors with no elevator.
- Must permit stays of 30+ days.
- Avoid AirBnBs with <20 reviews.

DEADLINE: Friday March 15, 5pm Lisbon time.

CHECK-IN: Slack me with any questions; otherwise share the link to the
sheet by deadline.

OUTPUT FORMAT: Google Sheet, share with sample@example.com.
```

The critical move: **write the procedure once, save it as a template**, and reuse for similar tasks. This is how outsourcing compounds.

## Step 5: The trial week

Before committing to ongoing work:

1. Pick 3 specific tasks from the categories above.
2. Hire 2 VAs (or 2 services). Send each the same first task.
3. Compare outputs at 24-48 hours.
4. Run task 2 with the better one. Task 3 with the better one. By end of week, you'll know.

Pay for the trial. Cheap is fine; free is wrong — it sets the wrong expectations.

## Step 6: Ongoing operating principles

Once a VA is in place, four rules:

### Rule 1: Default to over-communicating in writing

A 3-line task can fail in 10 ways. Write what they should _not_ do as well as what they should. The marginal time you spend on instructions saves 10x in rework.

### Rule 2: Empower rather than approve

(Same logic as `/interruption-killer`.) Give the VA decision authority up to thresholds. "Approve any expense under $200; ping me on anything above." Otherwise you're still the bottleneck.

### Rule 3: 1:1 once a week, 30 minutes max

A weekly sync — what's done, what's stuck, what's next, what should we change about the system? — keeps quality high without micromanaging. Don't skip it; don't extend it.

### Rule 4: Track time-saved, weekly

For the first month, write down each Friday: how many hours did this VA save me this week? If the answer is "less than what I'm paying them in hourly equivalent," fix it (better instructions, different tasks) or fire and try again.

## Save the Output

Write `outsourcing-plan.md`:

```markdown
# Outsourcing Plan

_Started: YYYY-MM-DD_

## Tasks delegated

| Task type | Frequency | VA  | Estimated weekly hours saved |
| --------- | --------- | --- | ---------------------------- |
| ...       | ...       | ... | ...                          |

## Procedures library

- [task name] — see procedures/[task].md
- ...

## VA(s)

- Name / service: ...
- Channel: [Slack / email / app]
- Working hours: ...
- Authority limits: ...

## Weekly review notes

- Week 1: hours saved = ...
- Week 2: ...
```

## Common Failure Modes

- **Skipping Step 0 entirely.** The 2026 trap: hiring a VA for tasks an AI agent does in 90 seconds for free. Always run the triage first.
- **Treating "AI did 80% of it" as "I'm done."** The remaining 20% — judgment, taste, edge cases — is often the part that mattered. Calibrate.
- **Hiring before having tasks ready.** First week is unproductive on both sides.
- **One-shot tasks without procedures.** No leverage. Each task is a from-scratch lift.
- **Withholding decision authority.** VA becomes a request router back to the user.
- **Delegating the actual core work too early.** Start with low-stakes, well-defined tasks.
- **Not firing fast.** A bad VA is worse than no VA. If after 2 weeks the work is still wrong, fire and re-hire.
- **Failing to refer to your `lifestyle-design.md` constraints.** ("Don't book hotels with no bathtub" matters to you and not to the VA — write it down.)
- **Treating AI as a person.** AI doesn't remember last Tuesday and won't text you when your kid's sick. Don't outsource categories that need a human.

## Ethical and Cross-Cultural Notes

- Pay above local-market rate. The exploitation framing of cheap VAs is more often a function of bad employers than the model. Be the good employer.
- Be aware of holidays in their country. Don't be surprised by a 5-day gap during national observances.
- Time zones matter. Decide upfront: do you need same-day overlap, or is async fine?
- Some tasks have data sensitivity (medical, financial, legal). Pick a VA service with appropriate data agreements, or keep that work in-house.

## Related Skills

- **automate-first** — The standalone version of Step 0's triage. Run it any time you catch yourself about to do something twice.
- **make-it-a-skill** — When Step 0 lands on "skill / scheduled task," this skill builds it.
- **deep-research** — When Step 0 lands on "AI agent run," this skill structures it.
- **eighty-twenty** — The "hand off" outputs from the audit go through Step 0 first.
- **interruption-killer** — Empowerment rules for VAs are the same as for teammates.
- **muse** + **income-autopilot** + **muse-launcher** — The natural extension: most of a 2026 muse runs on AI + scheduled tasks, not VAs.
- **batching** — VA tasks should be sent in batches, not as they come up. AI prompts should also be batched (one prompt with 10 inputs > 10 prompts with 1 input).
