---
name: low-info-diet
description: Run the Low-Information Diet protocol from The 4-Hour Workweek (Elimination chapter) — a structured information fast plus an ongoing rule set for what to consume. Use when the user says "I'm doomscrolling," "I read too much news," "I can't focus," "I waste hours on Twitter/X," "selective ignorance," "information overload," "do I really need to know this," or when they want to start a 1-week, 1-month, or permanent low-info regimen. Includes the on-fast rules, what to read instead, the "just-in-time" learning principle, and how to handle FOMO. For broader habit elimination, see not-to-do-list. For batching email specifically, see email-autoresponder.
metadata:
  version: 1.0.0
---

# Low-Information Diet

You are walking the user through Tim Ferriss's **Low-Information Diet** — the deliberate practice of consuming less, more selectively, and on a tighter schedule. From the Elimination chapter of *The 4-Hour Workweek*.

The premise: information is a cost, not a virtue. Most "staying informed" produces no actionable change in the user's behavior — and consumes hours of attention that should have gone to creating, deciding, or living. Selective ignorance, properly applied, is a productivity tool.

The classic version is a 1-week fast. Most people who do it once never go fully back.

## Before Starting

Read `lifestyle-design.md` if it exists.

Ask the user **why now**:

- "I'm losing 2 hours a day to my phone."
- "I read every newsletter and remember none of it."
- "I'm starting a project that needs deep work and I can't get there."
- "I'm anxious about news cycles I can't act on."
- "I'm just curious what would happen if I stopped."

The why matters because it determines the protocol. A user who's overwhelmed by news has a different fast than one who's lost in Slack.

## The 1-Week Fast (the standard protocol)

This is the version most people start with. It's intentionally absolute. Like an elimination diet for media.

### What you cut, completely, for 7 days

- News (websites, apps, push notifications, newspapers, NPR, broadcast TV news)
- Social feeds (Twitter/X, Instagram, TikTok, Facebook, LinkedIn — the **feed**, not DMs to specific people)
- Most podcasts (especially commentary or news; technical / how-to ones are case-by-case)
- Most YouTube (everything except: a specific tutorial you need for active work)
- Books that are not directly tied to a current decision or project
- Newsletters (mark all as read; for the week, do not open)
- Reddit, Hacker News, niche forums
- Any "to read" list you keep — close it, do not open it

### What you keep

- Direct messages from real humans (Slack DMs, email from people you know, texts)
- Working email — but on the email schedule from `/email-autoresponder`
- Fiction (this is a feature, not a bug — Tim recommends one fiction book per week)
- Search results for **specific questions tied to active decisions** (e.g., "what's the typical lease term in Lisbon?" — fine; doomscroll Reddit threads about expat life — not fine)
- One conversation per day with a real human about anything

### One question per day

Once per day, before bed, the user writes one sentence:

> "What did I miss today by not consuming, and did it matter?"

After 7 days, look at the 7 sentences. Almost always: nothing meaningful was missed. That insight is the whole point.

### Common failure points (warn the user upfront)

- **The first 48 hours are jumpy.** Phantom-tab reaches for Twitter, the news app icon, Reddit. Acknowledge it; don't push through with willpower — uninstall apps for the week. Make the friction physical.
- **"But what about [event]."** If a real life-altering event happens, someone you know will tell you. They always do.
- **The replacement urge.** "Now I have time, I'll just read more books / watch more documentaries." That is information-with-extra-steps. The first week, leave the time genuinely empty. See what surfaces.

## The Ongoing Protocol (after the fast)

After the 1-week fast, the user typically wants a permanent posture. The **3 rules**:

### Rule 1: Just-in-time learning, not just-in-case

Consume information when you need it for a specific decision or skill, not "in case it comes up."

- Researching a Lisbon move? Read about Lisbon. Don't accidentally also read about Madrid, Mexico City, Bali.
- Need to ship a marketing test? Read the AdWords docs once, fully. Don't read 10 think pieces about marketing in general.

This rule alone reclaims 5-10 hours/week for most users.

### Rule 2: Two checks per day, max, on any feed

If a feed has any reason to stay in the user's life (e.g., the user is paid to be on Twitter/X for distribution; LinkedIn matters for sales) — cap to **two checks per day**, calendar-blocked, with hard timers.

The math of feeds: every "quick check" costs 23 minutes of recovery before deep work resumes (per a famous Mark UC Irvine study Tim cites in spirit). Eight quick checks = 3+ hours of fragmented attention.

### Rule 3: Subscribe by output, not by topic

Cancel everything that's "for general awareness." Subscribe only to:

- Sources tied to active outputs (the project you're shipping)
- Sources where you can name the specific decision they help with
- One or two "fun" subscriptions for clearly-identified leisure (allowed, but on a single read-it-later app, batched once a week)

For the user, do a quick audit of all current subscriptions. For each, ask:

> "Name a decision this source helped you make in the last 90 days."

If they can't, unsubscribe.

## Permanent FOMO management

The hardest part isn't cutting consumption — it's the social discomfort of not knowing what other people are talking about. The book's argument: **the people you most want to learn from are typically people who consume less, not more.**

A few one-liners the user can use:

- "I haven't seen it — what should I know?"  (This is fine. It's polite. It works.)
- "I'm on a low-info kick right now."  (Honest, ends the social pressure.)
- "Send me the link, I'll get to it later."  (Then file it; review weekly.)

## Save the Output

Write `low-info-diet-[date].md`:

```markdown
# Low-Information Diet

_Started: YYYY-MM-DD_
_Why I'm doing this: ..._

## 1-week fast
- [ ] Day 1 — note: ...
- [ ] Day 2 — note: ...
- [ ] Day 3 — note: ...
- [ ] Day 4 — note: ...
- [ ] Day 5 — note: ...
- [ ] Day 6 — note: ...
- [ ] Day 7 — review

## Apps uninstalled
- ...

## Subscriptions canceled
- ...

## Subscriptions kept (with reason)
- [Source] — helps decide: ...
- [Source] — helps decide: ...

## Two-checks-per-day windows
- [Time 1]
- [Time 2]

## What I missed and whether it mattered (after week 1)
[paragraph]
```

## What to Avoid

- Replacing one feed with another (Twitter → LinkedIn → Substack notes). It's the same problem.
- Making this absolute forever. The point is **selective**, not deprived. If the user genuinely loves a podcast and it doesn't bleed into mindless consumption, keep it.
- Confusing "research mode for a project" with "low-info diet violation." Reading 4 hours about Lisbon visas because you're moving in 6 weeks is just-in-time learning, not falling off the wagon.
- Applying this during travel/holiday/family time. The diet is for working life. Take a break.

## Related Skills

- **email-autoresponder** — Email is its own consumption loop, with its own rules. Run that skill in parallel.
- **not-to-do-list** — Often the user's first not-to-do rules come from the fast.
- **batching** — Specifically, batch reading windows on retained subscriptions.
- **interruption-killer** — The internal interruption (urge to check) needs the same treatment as external ones.
