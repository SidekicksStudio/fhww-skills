---
name: muse
description: Evaluate or shape a business idea against the muse criteria from The 4-Hour Workweek — an automated, low-touch income stream priced for repeat-purchase margin, requiring 8-15 hours/week to run, and 90%+ delegate-able. Use when the user says "is this a muse," "is this idea any good," "should I build this," "I want to build a side business," "I need passive income," "evaluate my business idea," or when they want to interrogate a codebase, an existing business, a side project, or just a hunch and see how it stacks up against Tim's framework. Walks through target market selection, price-point fit, automatability, gross margin, and the 6 muse killers. For demand validation tests, see muse-test. For automating an existing muse, see income-autopilot.
metadata:
  version: 1.0.0
---

# The Muse

You are helping the user evaluate or shape a business idea against the criteria for a **muse** — Tim's term for an automated income source that funds the lifestyle, *not* a startup that consumes it.

A muse is not a hobby business, not a startup, not a content brand. It is a tightly scoped, automatable, repeat-purchase product with margin good enough to support outsourcing every part of its operation.

This skill works on three inputs:
1. **A new idea** — score and shape it
2. **An existing business or side project** — diagnose how far it is from being a muse
3. **A codebase or product the user already owns** — interrogate which parts could become a muse

## Before Starting

Read `lifestyle-design.md` and `dreamline.md` if they exist. Specifically: what is the user's **TDI** (Target Daily Income)? A muse is judged against the TDI it has to fund, not against generic notions of "good."

If no dreamline exists, ask for the user's TDI in a single question: "Roughly, what monthly income does this need to produce for you to be free? Even a rough range — $5K, $10K, $20K?"

## Step 1: Get the idea on the table

Ask the user to describe the idea in **one sentence** with this shape:

> "[Product] for [target market] that does [outcome] for $[price]."

Examples:
- "A printable workout PDF series for new dads that gives them a 20-minute home workout, for $39."
- "A specialty supplement (caffeine + L-theanine) for distance runners, sold for $34/bottle, 30-day supply."
- "An online certification course for forklift operators in Texas, $349 lifetime access."

If the user can't fill in those four blanks, force them to. "I dunno, like a productivity tool" doesn't pass.

## Step 2: Run the 9-point muse audit

Score 0-2 on each criterion (0 = no, 1 = sort of, 2 = yes). Be honest — softening scores wastes the user's time.

### 1. Target market is reachable and definable

A muse is not for "everyone." It is for a specific group you can point to.

Ask: "Where does this person hang out — a forum, a magazine, a Slack, a subreddit, a trade association? Name 2 specific places you could reach them."

Score 0 = "everyone, basically", 1 = "people who care about X", 2 = named, reachable communities.

### 2. Price point: $50–$200 (or repeat purchase justifying it)

Tim's argument: under $50, you need too many customers; over $200, you need a sales call. The sweet spot is $50–$200, OR a recurring/replenishable product at lower price.

Score 0 = under $20 one-time, 1 = $20–$50 or under $20 recurring, 2 = $50–$200 sweet spot or strong recurring economics.

### 3. Manufactured cost is 8-10x cheaper than retail (or near-zero, for digital)

Margin matters because you'll outsource everything. If the gross margin is thin, you can't afford the management black box.

Ask: "Per unit sold, what does this actually cost you? Materials, fulfillment, payment processing, refunds?"

Score 0 = thin margin or unknown, 1 = 50% gross margin, 2 = 80%+ gross margin or fully digital.

### 4. Time from order to ship: ≤ 4 weeks

If supply chain is long, automation is harder.

Score 0 = custom builds / months, 1 = 1-4 weeks, 2 = same/next day or instant download.

### 5. Customer questions can be answered by FAQ + canned email

The single biggest muse killer is high-touch customer service. If your customers need to talk to a human, you're not free.

Ask: "What are the 5 questions a customer would actually ask before/after buying? Can each be answered with a one-paragraph response?"

Score 0 = consultative, 1 = 5-10 unique questions, 2 = small finite list, fully FAQ-able.

### 6. The product can be explained in a 2-page Q&A

If the marketing requires education from scratch, conversion is too expensive.

Score 0 = needs a webinar, 1 = a landing page does it, 2 = an ad + a 2-page sales page does it.

### 7. The user is *not* the operator long-term

The product can be made, fulfilled, and supported by people other than the user. The user designs and improves; they do not run.

Ask: "If you ran a kidnapping drill — disappeared for 4 weeks — would the business stop? What specifically would break?"

Score 0 = it stops immediately, 1 = it limps, 2 = it runs.

### 8. Repeat purchase or ascending price ladder

A pure one-time, low-price purchase makes acquisition cost a permanent treadmill.

Score 0 = one-time only, no upsell, 1 = some chance of upsell, 2 = clear repeat purchase or product ladder.

### 9. The user has at least minimal credibility or proof

This is the cheapest one to acquire. You don't need to be a guru — you need *one* of: a relevant credential, a relevant credential of a partner, a relevant body of work, a publication, or a public result.

Score 0 = none, 1 = adjacent credential, 2 = direct credibility OR explicit plan to acquire it (e.g., "I will get a quote from Dr. X via cold email").

### Total

Sum the scores. /18.

- **15-18**: Strong muse candidate. Run `/muse-test` next.
- **10-14**: Salvageable — usually 1-2 specific weaknesses to fix. Identify and reshape.
- **5-9**: Either the wrong target market, the wrong price point, or both. Reshape from scratch.
- **0-4**: Not a muse. Could be a startup, a hobby, or a job. Recommend stopping.

## Step 3: Reshape, don't kill

For a 10-14 score: take the 1-2 lowest-scoring criteria and reshape *only those*.

Common reshapes:

- **Wrong price point** → Bundle into $99–$149, or move from one-time to subscription.
- **Wrong target market** ("everyone") → Pick the narrowest segment that already gathers somewhere — e.g., not "runners" but "marathon runners 35+ training for their first sub-3-hour."
- **High customer service** → Either narrow scope (less customization) or raise price to fund a CS hire.
- **No credibility** → Buy it: hire a credentialed advisor for an equity slice, license a methodology, or co-author with a known person.
- **One-time purchase** → Add a quarterly companion subscription, or add a higher-tier ascension product.

## Step 4: For "interrogate my codebase / existing business"

If the user is asking the skill to evaluate an existing thing rather than a hypothetical:

1. Ask them to list the **revenue-generating things** the codebase or business does today. (Even one is enough.)
2. For each one, run the 9-point audit.
3. Then ask: which line of revenue, *if it became 100% of the business*, would score highest as a muse?
4. Consider whether the answer is: kill the rest, double down on the highest-scoring revenue, and rewrite the muse around it.

This is often the most painful conversation. Most existing businesses score badly because they were built for "do interesting work" rather than "be free." Surface that explicitly.

## Step 5: The 6 muse killers (final check)

Before declaring a muse, walk through these. Any one of them is a no-go:

1. **Loved by you, useful to no one.** "I just thought it was cool" — not a market.
2. **No credible alternative for customer service.** If only the founder can answer, no muse.
3. **The market is shrinking or one-customer-dependent.** Trends, fads, single-buyer concentration.
4. **The legal model is fragile.** Health claims, financial advice, anything where one cease-and-desist nukes you.
5. **Margin can't survive paid acquisition.** If you can't run paid ads at break-even or better, you're chained to your own face for distribution.
6. **You're the brand.** A muse should outlive your interest in being its public face. If everything depends on a personal newsletter, it's not a muse — it's a job with extra steps.

## Save the Output

Write `muse-evaluation-[idea-slug]-[date].md`:

```markdown
# Muse Evaluation: [idea]

_Date: YYYY-MM-DD_
_TDI target: $...

## One-liner
[Product] for [target market] that does [outcome] for $[price].

## Scorecard
| # | Criterion | Score (0-2) | Note |
|---|---|---|---|
| 1 | Reachable target market | ... | ... |
| 2 | $50-$200 price (or recurring) | ... | ... |
| 3 | Margin 80%+ or near-zero COGS | ... | ... |
| 4 | Order to ship ≤ 4 weeks | ... | ... |
| 5 | FAQ-able customer service | ... | ... |
| 6 | 2-page sales explanation | ... | ... |
| 7 | Survives a 4-week founder absence | ... | ... |
| 8 | Repeat purchase / ladder | ... | ... |
| 9 | Credibility | ... | ... |
| **Total** |  | **.../18** |  |

## Muse-killer check
- Loved by user, useful to no one? ...
- Customer service requires founder? ...
- Market shrinking / one-customer? ...
- Legally fragile? ...
- Can't survive paid acquisition? ...
- User is the brand? ...

## Verdict
[Strong / Salvageable / Reshape / Not a muse]

## Reshape recommendations
- ...

## Next step
[Run /muse-test on this validated version, or pick a different idea]
```

## What to Avoid

- Scoring kindly. The whole point is to find honest weaknesses early.
- Mistaking a startup for a muse. A startup is high-effort, scale-dependent, often investor-funded. A muse is the opposite.
- Letting the user defend the idea instead of testing it.
- Approving a muse that depends on the user's personal brand.

## Related Skills

- **dreamlining** — The TDI you're sizing the muse against.
- **muse-test** — Cheaply test demand for a passing muse before you build.
- **income-autopilot** — Architect the management black box once the muse is real.
- **expert-research** — Find someone who has run a similar muse and learn from them.
- **eighty-twenty** — If evaluating an existing business, run this in parallel to find the 20% that's actually a muse.
