---
name: relative-income
description: Calculate relative income — Tim Ferriss's reframe from absolute dollars to dollars-per-hour weighted by mobility, autonomy, and time-of-life from The 4-Hour Workweek. Use when the user says "is this raise worth it," "should I take this job," "compare two job offers," "I make $X but I'm miserable," "the new job pays more but," "am I actually rich," "geo arbitrage," or "what's my real hourly rate." Surfaces the freedom math — the number that often shows a $80K consultant in Lisbon is wealthier than a $200K employee in NYC. Pair with /mini-retirement and /dreamlining when comparing across geographies.
metadata:
  version: 1.0.0
---

# Relative Income

You are walking the user through the **relative income** calculation — Tim's reframe of income from a single absolute number ("$X/year") to a multi-dimensional one that incorporates time, mobility, and freedom.

The book's central claim: a person earning $50K/year while working 30 hours a week from a low-cost beach town is wealthier than someone earning $250K/year working 80 hours in Manhattan. Both can be true. The number you hear about is the absolute one. The one that matters is the relative one.

## The Three Components

Tim's argument: real income (W) = (dollars earned) × (mobility / freedom multiplier) / (hours worked).

Practically:

```
Relative income = (post-tax income) × (purchasing power factor)
                  ÷ (hours actually worked)
                  × (autonomy multiplier)
```

Each of these has to be honestly calculated.

## Before Starting

Read `lifestyle-design.md`.

Ask the user **what they're using this for**. Common cases:

1. Comparing two job offers
2. Comparing current job vs. a hypothetical move
3. Comparing current employment vs. starting a muse
4. Comparing absolute income across geographies (Lisbon vs. NYC)
5. Just curious what their real hourly rate is

The answer changes how rigorously we treat each component.

## Step 1: Calculate post-tax income

Many users carry their gross income in their head and forget the tax wedge.

For each scenario being compared, capture:

- Gross annual income
- Effective tax rate (federal + state + local + payroll)
- Post-tax annual = gross × (1 - effective rate)
- Monthly post-tax = annual / 12

Example:

| | Job A (NYC) | Job B (Austin) | Job C (Lisbon, freelance) |
|---|---|---|---|
| Gross | $250,000 | $200,000 | $130,000 |
| Effective tax | 38% | 30% | 22% (tax treaty + NHR) |
| Post-tax | $155,000 | $140,000 | $101,400 |

The gap shrinks before we even add the freedom math.

## Step 2: Apply purchasing power factor

A dollar in Lisbon buys substantially more than a dollar in New York. Tim's example uses Bay Area vs. Buenos Aires; the principle is the same.

For each scenario, multiply post-tax income by a **cost-of-living factor relative to a baseline** (use the highest-cost scenario as the baseline of 1.0).

Approximate factors (rough, current-ish; calibrate to recent data):

| City | COL factor (lower is more expensive) |
|---|---|
| New York / SF | 1.0 |
| Boston / DC / LA | 0.9 |
| Austin / Chicago / Denver | 0.7 |
| Lisbon | 0.45 |
| Mexico City | 0.4 |
| Bangkok / Chiang Mai | 0.3 |
| Bali | 0.3 |
| Buenos Aires (volatile) | 0.3 |

So $101,400 in Lisbon at 0.45 = effective spending power of **$225,000** in NYC terms — closing most of the gap with Job A.

## Step 3: Divide by hours actually worked

Most people quote a "40-hour" workweek that is closer to 55-65 with commute, evening email, weekend prep, and traveled meetings.

For each scenario, capture:

- Hours of work per week (honest count, not contractual)
- Weeks worked per year (52 minus actual vacation taken)
- Total hours/year

Then: **post-tax × COL factor / total hours = effective hourly rate**

Example continued:

| | Job A | Job B | Job C |
|---|---|---|---|
| Post-tax | $155K | $140K | $101.4K |
| × COL factor | $155K (1.0) | $200K (0.7→) | $225K (0.45→) |
| Hours/week | 60 | 45 | 30 |
| Weeks worked | 50 | 50 | 48 |
| Total hours | 3,000 | 2,250 | 1,440 |
| **$/hour** | **$52** | **$89** | **$156** |

Job C, the lowest absolute income, has 3x the hourly rate.

## Step 4: Apply the autonomy multiplier

The blunt-force version of relative income is Step 3. The complete version adds **autonomy multiplier** — how free you are with each unit of time.

Score each scenario, 0.5 to 2.0, on:

| Factor | Score 0.5 | Score 1.0 | Score 2.0 |
|---|---|---|---|
| Schedule control | Boss sets hours, butts-in-seats | Standard 9-5 with some flex | I set hours; can do mornings off |
| Location control | Office mandatory | Hybrid | Anywhere with WiFi |
| Travel control | Office attendance required | Some travel allowed | Fully untethered |
| Project control | Assigned by manager | Some choice within team | I pick what to work on |
| Time-off control | Permission required | Standard PTO | Take what I need |

Average the scores → autonomy multiplier.

Multiply Step 3's $/hour by the multiplier.

| | Job A | Job B | Job C |
|---|---|---|---|
| Schedule | 0.5 | 1.0 | 2.0 |
| Location | 0.5 | 1.0 | 2.0 |
| Travel | 0.5 | 1.0 | 2.0 |
| Project | 1.0 | 1.0 | 2.0 |
| Time off | 0.5 | 1.0 | 2.0 |
| **Avg** | **0.6** | **1.0** | **2.0** |
| × $/hour | $52 × 0.6 = **$31** | $89 × 1.0 = **$89** | $156 × 2.0 = **$312** |

Job C has roughly 10x the relative income of Job A.

The user's intuition will fight the math. State the math anyway. Then ask if any of the autonomy scores feel wrong — re-score, recompute. The goal is honesty, not pre-cooked answers.

## Step 5: The W formula stress tests

Run two stress tests on the result:

### Test 1: The hour cost

Pick a real recent purchase the user is on the fence about. Convert its cost into hours of life from each scenario.

Example: a $400 weekend trip.
- Job A: 400 / 31 = 12.9 hours of "real" life
- Job C: 400 / 312 = 1.3 hours

It's the same trip. From Job A's hourly rate, it's nearly two days of life. From Job C's, it's lunch.

### Test 2: The "what would I do with 100 free hours" test

Ask the user: "Imagine each scenario gives you 100 free hours next month. What would you actually do with them?"

If Job C gives the user 100 free hours and they don't have a clear answer, freedom is theoretical for them right now — they need `/comfort-challenge` and `/dreamlining`.

If Job A gives the user 100 free hours and they immediately know what they'd do, they have a freedom problem, not an income problem.

## Save the Output

Write `relative-income-[date].md`:

```markdown
# Relative Income Calculation

_Date: YYYY-MM-DD_

## Comparing
- Scenario A: ...
- Scenario B: ...
- Scenario C: ...

## Calculation

| | A | B | C |
|---|---|---|---|
| Gross annual | ... | ... | ... |
| Effective tax | ...% | ...% | ...% |
| Post-tax | ... | ... | ... |
| COL factor | ... | ... | ... |
| Adjusted | ... | ... | ... |
| Hours/week | ... | ... | ... |
| Weeks worked | ... | ... | ... |
| $/hour | ... | ... | ... |
| Autonomy avg | ... | ... | ... |
| **Relative income $/hr** | ... | ... | ... |

## Stress tests
- $400 weekend trip in real-life hours: A=..., B=..., C=...
- 100 free hours next month, what I'd do: ...

## Decision implication
[what this changes]
```

## Common Failure Modes

- **Underreporting hours worked.** Most users say "40" — actual is 50-65 once everything is counted. Push for honesty.
- **Forgetting COL.** Especially when comparing to lower-cost geography. The point of going abroad is partly that the dollar buys more.
- **Padding the autonomy scores.** People score themselves more autonomous than they are. If they couldn't take next Tuesday off without permission, schedule control is not 2.0.
- **Comparing only to current life.** Always include a hypothetical — the user may be locked in by anchoring.

## When relative income reveals something hard

Sometimes the math reveals that a job the user is proud of is, by relative income, paying them poorly. Acknowledge it. Don't argue. The next step is usually `/dreamlining` (what would they do instead?) or `/fear-setting` (the action they've been avoiding).

## What to Avoid

- Pretending the multiplier is exact. It's a rough lens, not a precise tool. The point is to surface a 2-10x gap, not a 5% one.
- Using relative income to convince someone else (a partner, family) to support a decision. Use it to help yourself decide. Sharing it with a partner is fine; weaponizing it is not.

## Related Skills

- **dreamlining** — The TDI in dreamlining is an absolute number. Relative income tells you how easy or hard it is to hit.
- **fear-setting** — When the math reveals the current job is suboptimal but quitting is scary.
- **mini-retirement** — Relative income is most powerful as an argument for spending time abroad.
- **muse** — A muse usually has a much higher relative-income score than a job, even at lower absolute income.
- **lifestyle-design** — Update the foundation context after running this.
