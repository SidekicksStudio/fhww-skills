---
name: expert-research
description: Find real people who have already done the thing the user wants to do, then design a focused interview to extract what they wish they'd known. Mirrors how Tim Ferriss researched The 4-Hour Workweek itself — by talking to dozens of authors, athletes, entrepreneurs, and outliers to find the patterns hidden behind the public story. Use when the user says "I don't know how to start," "I wish I knew someone who'd done this," "find me people who," "who has done X," "I need to learn from someone real," "I want a mentor," or any time the answer is buried in someone's experience rather than in research. Builds a target list of 5-15 people, ranks them by reach difficulty, and produces an interview agenda. Pairs with /cold-outreach for the actual asking.
metadata:
  version: 1.0.0
---

# Expert Research

You are helping the user **find real people who have already done the thing they want to do** — and then design a short, sharp set of interviews that extract the asymmetric lessons the public record never captures.

This is the skill Tim Ferriss used to write *The 4-Hour Workweek*. Before publishing, he interviewed dozens of authors, athletes, and entrepreneurs to find out what they did differently — what worked, what didn't, what they wished they'd known. Most books, businesses, and life decisions get better when you do this. Most people skip it.

The goal here is not "find a mentor." It is "find 5-15 people who already have the answer to your specific question, and ask them."

## Before Starting

Read `lifestyle-design.md` and `dreamline.md` if they exist. Specifically: which **dream or decision** is this research feeding into?

If unclear, ask:

> "What specific decision or move are you researching this for? In one sentence."

Examples:
- "Whether to take 4 months off to live in Lisbon next year."
- "Whether to launch a $99/year SaaS for marathon coaches."
- "Whether to publish a book traditionally vs. self-publish in 2026."
- "Whether to apply for a Spanish digital nomad visa as a freelancer."

The research is only as sharp as the question.

## Step 1: Define the archetype

You're not looking for "successful people." You're looking for **people who match a specific shape**.

Walk the user through 4 filters:

1. **Outcome filter** — What outcome must they have already produced? ("Published a book that sold 50,000+ copies" / "Lived in Lisbon for 6+ months as a US passport holder" / "Sold a SaaS in the $1-5M range" / "Coached marathon runners professionally for 5+ years")
2. **Context filter** — What context must roughly match? ("Did it without a co-founder" / "Has kids and a partner" / "Was over 35 when they started" / "Did it in the last 5 years, not 2003")
3. **Tier filter** — What level of celebrity makes sense? Aim for the **second tier** down, not the top — see "Tier strategy" below.
4. **Anti-filter** — Who you specifically *don't* want. Often: the loudest voices in a niche, who tend to be selling a worldview rather than reflecting on it.

Capture this as the **archetype card**:

```
Archetype: Someone who [outcome filter], in roughly [context filter],
          ideally [tier], not [anti-filter].
```

## Step 2: Tier strategy

Most people, when asked "name someone who's done X," name the most famous person. That's the wrong target — they get 200 cold messages a day.

Tim's lesson: **the second-tier person is more reachable, often more candid, and frequently has more recent experience** than the canonical name.

Three tiers to consider:

| Tier | Example | Reachability | Trade-off |
|---|---|---|---|
| 1 — Canonical | The famous person in this niche | Very low | If they reply, gold. But ~1% reply rate. |
| 2 — Working pro | Successful, productive, not famous | Medium | Usually best balance — recent experience, replies. |
| 3 — Just-ahead | Did it 1-2 years before you | High | Ground truth on logistics; less wisdom on long arc. |

**Build a list across all three tiers.** Aim for the mix:

- 1-2 Tier 1 (long shots, but ask anyway)
- 5-8 Tier 2 (the workhorse interviews)
- 3-5 Tier 3 (cheap, fast, logistical)

## Step 3: Build the target list

Help the user generate the list. Use whatever's available — web search, LinkedIn, podcast listings, conference speaker pages, niche Slack communities, Reddit, Twitter/X.

For each person, capture:

```
Name | Tier | Outcome match | Context match | Best channel | Public link |
```

Keep going until the list has **at least 10 names**. Push past the obvious 3.

Useful prompts when the user is stuck:

- "Who has been on a podcast about [topic] in the last 24 months?"
- "Who has written a long-form post / case study / Substack about doing this?"
- "Who has spoken at a conference on this — and what about their *opening act*?"
- "Who's the second author on the cited paper?"
- "Who's the COO of the company famous for this — i.e., the person who actually ran the thing?"
- "Who quietly succeeded vs. who is loud about succeeding?"
- "Who *failed at* this and is honest about why?" (Often the best interview.)

Don't skip the failures. People who *attempted and bailed* often give the most useful interviews because they have less ego in defending the path.

## Step 4: Design the interview

This is **not** a generic informational interview. It is a 4-question instrument designed to extract specific decisions, not philosophy.

Walk the user through the **4 questions**:

### Q1: The decision question

> "When you decided to [do the thing], what was the single biggest factor that tipped you? And — was that the *right* factor in retrospect?"

Why: surfaces the actual decision criterion vs. the post-hoc story.

### Q2: The expensive lesson question

> "What did you spend the most time, money, or stress on that, knowing what you know now, you wouldn't repeat?"

Why: this is where almost all the asymmetric value sits. Most people will be candid here because everyone has at least one thing.

### Q3: The hidden-leverage question

> "What did you do that turned out to matter way more than you expected? Something small that compounded?"

Why: the inverse of Q2. Surfaces non-obvious wins.

### Q4: The "if you were me" question

> "If you were me — [restate the user's specific situation, two lines max] — what's the one thing you'd do this month?"

Why: forces the interviewee to tactically engage. People love this question because it's flattering and concrete.

**Optional Q5** — only if there's time and trust:

> "Who else should I talk to who's done this in a meaningfully different way than you?"

This question turns a 1:1 into a snowball.

## Step 5: Outreach plan

Hand off the list and the 4 questions to `/cold-outreach`. The outreach should ask **one** of the four questions — the one most relevant to the user's current decision. Keep the others in reserve for when someone replies.

Important: **do not ask all four questions in the cold email**. Ask one. Earn the next ones by replying to their response with another sharp question.

If a Tier 2 or 3 contact agrees to a call, send all four questions ahead of time. 30 minutes is plenty.

## Step 6: Synthesize

After running 5+ interviews, look for:

- **The 80/20 of the answers** — what shows up in 4+ of 5 conversations?
- **The lone heretic** — who said something nobody else did, and was it credible?
- **The thing nobody said** — sometimes the silence is the signal. (E.g., nobody mentioned the visa being hard. Maybe it's not.)
- **Updated decision** — does this change what the user is going to do? If not, the research wasn't sharp enough or the user was already committed.

## Save the Output

Write `expert-research-[topic-slug]-[date].md`:

```markdown
# Expert Research: [topic]

_Started: YYYY-MM-DD_

## Decision being researched
[one sentence]

## Archetype
Someone who [outcome filter], in roughly [context filter],
ideally [tier], not [anti-filter].

## Target list

| Name | Tier | Outcome match | Context match | Channel | Status |
|---|---|---|---|---|---|
| ... | T1 | ... | ... | email | sent YYYY-MM-DD |
| ... | T2 | ... | ... | LinkedIn | replied — interview YYYY-MM-DD |
| ... | T2 | ... | ... | Twitter DM | no reply — bumped YYYY-MM-DD |
| ... | T3 | ... | ... | email | done — see notes/[name].md |

## Interview agenda
1. Decision: ...
2. Expensive lesson: ...
3. Hidden leverage: ...
4. If you were me: ...

## Notes per person
(separate file each)

## Synthesis
- 80/20 across answers: ...
- Heretic: ...
- Conspicuous silences: ...
- Updated decision: ...
```

## Common Failure Modes

- **Going only after Tier 1.** Almost no replies. List feels prestigious, produces nothing.
- **No archetype** — random successful people, generic answers.
- **Asking philosophical questions** ("how do you think about success?"). They'll answer politely and tell you nothing.
- **Treating the call as networking.** This is research. Be focused. Stop early if you have what you came for.
- **Not synthesizing.** Twelve interviews and no document — the data dies in your inbox.

## Ethics

- Don't quote anyone publicly without permission.
- If they share something candid, don't put it on a podcast or in a tweet without asking.
- Send a thank-you note + one update later showing what you did with their answer. This is how a one-shot interview becomes a relationship.

## Related Skills

- **cold-outreach** — The actual asking. This skill builds the list; that one writes the message.
- **dreamlining** — The decision being researched usually traces back to a dream.
- **fear-setting** — If the user can't bring themselves to send any of the messages, run fear-setting on the act first.
- **muse-test** — Sometimes a 10-person expert interview replaces a paid-ads test for ultra-niche markets.
