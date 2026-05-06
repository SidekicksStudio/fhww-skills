---
name: income-autopilot
description: Architect a muse to run on autopilot — Tim Ferriss's "Income Autopilot III: MBA: Management By Absence" from The 4-Hour Workweek. Use when the user has a working muse and says "I need to step back," "I want to leave the business for a month," "delegate everything," "step away from operations," "the company runs on me right now," "build a black box," or "Management By Absence." Designs the operational architecture (payment, fulfillment, customer service, escalation) and the empowerment policy that lets the founder disappear without the muse breaking. Pairs with /outsourcing (the people layer) and /interruption-killer (the empowerment-rules layer).
metadata:
  version: 1.0.0
---

# Income Autopilot — Management By Absence

You are helping the user architect their muse so it **runs without them**. Tim's term: Management By Absence (MBA), or the management black box.

The premise: a muse that requires the founder's daily attention is a job, not a muse. The whole point of the system — mini-retirements, dreamlines that include "spend 6 months in Lisbon" — depends on the muse running while you are unreachable.

This skill is for users who already have a muse generating revenue. If they don't have one yet, send them to `/muse` and `/muse-test` first.

## Before Starting

Read `lifestyle-design.md` and any existing `muse-evaluation-*.md`.

Get from the user, in one message:

1. **The muse**: one-line description and current monthly revenue
2. **Current weekly hours**: how much time the muse takes today, in their hands
3. **The current bottlenecks**: list of "things only I do"
4. **The kidnap test**: if they vanished for 4 weeks, what specifically would break?

The kidnap test is the decision tree. Whatever breaks is what this skill systematizes away.

## The 4 Layers of the Black Box

The muse is decomposed into 4 operational layers. Each must run without the user.

### Layer 1 — Payment

**Goal**: Money comes in without you being a person in any loop.

Required:

- A payment processor that handles billing, retries, refunds, chargebacks (Stripe, Lemonsqueezy, Paddle, Shopify Payments)
- Automated invoicing where applicable
- Failed-payment dunning email sequence (3-5 messages over 14 days)
- Sales tax handled (TaxJar / Stripe Tax / equivalent)
- Refunds handled by support — within a written policy — without escalation

**Founder absence test**: A new customer can find, buy, and pay for the product without a single message reaching you.

### Layer 2 — Fulfillment

**Goal**: The product gets to the customer without your hands on it.

Three sub-cases:

- **Digital product**: Auto-delivered on payment. (Gumroad, Lemonsqueezy, SendOwl, custom delivery.) Test the failure mode: what happens if the email bounces?
- **Physical product**: Third-party fulfillment (3PL — ShipBob, ShipMonk, Amazon FBA). Inventory monitored automatically. Reorder triggers set.
- **Service**: Productized scope, fixed deliverable, fulfilled by a contractor or VA on a SOP — not the founder.

**Founder absence test**: A customer who buys today receives the product in the standard timeframe with you offline.

### Layer 3 — Customer Service

**Goal**: Customers can get questions answered, refunds processed, and edge cases resolved without you.

Required:

- A help desk / shared inbox (Help Scout, Zendesk, Front, even a shared Gmail label)
- A trained support person or VA (see `/outsourcing`) — even one part-time person
- A written FAQ covering the top 20 issues
- A written refund/replacement policy
- A written escalation policy — what comes to you, what doesn't

The 80/20 of CS: 80% of tickets are 5-10 question types. Document those, train someone, you're done.

**Founder absence test**: For a typical customer issue, the customer's resolution time is the same with or without you online.

### Layer 4 — Decision-making (the empowerment layer)

**Goal**: When something happens that nobody pre-planned for, someone other than you decides.

This is the layer most founders skip and most regret skipping.

Required:

- A clear "second-in-command" — a person, not a role title (could be a contractor, an EA, an operations partner)
- An empowerment document (see `/interruption-killer`) defining what they decide without checking
- A weekly 30-minute review (async update is fine)
- An exception channel — text/SMS — that bypasses the autoresponder *only* for genuinely existential issues

Tim's term: the Lieutenant. Your single point of operational accountability while you are away.

If the muse is small enough that there's no one in this role yet, the skill is to create that role — even at 5-10 hours a week. Without it, no autopilot.

## Step 1: Map the bottlenecks to layers

For each "thing only I do" the user listed, label which layer it belongs to.

| "Only I do" | Layer | Action |
|---|---|---|
| Approve refunds over $50 | 3 (CS) | Raise threshold, document, hand to support |
| Reply to specific VIP customers | 3 (CS) | Build a VIP triage policy, hand to lieutenant |
| Reorder inventory when stock low | 2 (Fulfillment) | Automate reorder triggers |
| Decide which content to ship | 4 (Decisions) | Build a content calendar, empowerment for adjustments |
| Run the payments reconciliation | 1 (Payment) | Outsource to bookkeeper |
| New product decisions | 4 (Decisions) | Founder still does — but only quarterly |

The output of step 1 is a **list of bottlenecks with concrete remediation steps per layer**.

## Step 2: Build the black box, in order

Build the layers in this order. Each takes 2-6 weeks of work.

### Week 1-2: Payment + Fulfillment

These are the most automatable and have the lowest people cost.

- Audit and update payment / fulfillment automation
- Connect payment failures → automated dunning (don't send manual emails about declined cards)
- Set inventory reorder triggers / digital delivery error alerts to a shared inbox, not a personal one

### Week 3-4: Customer Service

- Choose the help desk
- Write the FAQ (the actual top 20 questions, not a generic template)
- Write the refund/replacement policy
- Hire / assign a support person
- Train them on actual past tickets — you reply to 50 tickets *with them watching*, then they reply to 50 *with you watching*, then they own it

### Week 5-8: Decision-making

The hardest layer. The lieutenant is established here.

- Identify the lieutenant (existing team, hire, contractor, partner)
- Write the empowerment document — every decision they own up to a threshold
- Set up the weekly async review
- Set up the exception channel (with hard rules about when to use it)
- Run a **48-hour test absence**: founder fully unreachable except via emergency channel. Capture what came up.
- Adjust the empowerment doc based on the test
- Run a **1-week test absence**. Adjust again.
- Then a 4-week.

## Step 3: The kidnap drill

Before counting the muse as truly autopilot, run the **4-week kidnap drill**:

For 4 weeks, the founder is "kidnapped" — not on email, not on Slack, not approving anything. Phone is checked once a day for the exception channel only, and only for genuinely existential issues.

What "existential" means is pre-defined. Examples:

- The payment processor froze the account
- A press story names the company in a libelous way
- A regulatory letter arrives
- A senior person resigns suddenly
- A serious safety / legal issue

Everything else: handled by the lieutenant, by the support person, by the SOP, by the empowerment doc.

If the muse survives 4 weeks, you have a black box.

If it doesn't — note what broke. That's the next layer to fix. Re-run.

## Step 4: The recurring discipline

Even after the black box exists, the founder will be tempted to log in and "just check." Two rules:

1. **Weekly 30-min review only**, on a fixed day. Otherwise, hands off.
2. **Quarterly strategic session** — pricing, new products, partnerships. Founder reasserts oversight on the things only they can decide.

Otherwise, the autopilot collapses back into "founder does everything" within 90 days.

## Save the Output

Write `income-autopilot.md`:

```markdown
# Income Autopilot — Architecture

_Last updated: YYYY-MM-DD_

## Muse
[one-liner, MRR/MRR run-rate]

## Founder time before
- Hours/week: ...
- Daily presence required for: ...

## The 4 layers

### Layer 1 — Payment
- Processor: ...
- Failed-payment flow: ...
- Tax handled by: ...
- Founder-absence test: PASS / FAIL — ...

### Layer 2 — Fulfillment
- Method: ...
- Vendor / system: ...
- Failure modes monitored by: ...
- Founder-absence test: PASS / FAIL — ...

### Layer 3 — Customer Service
- Help desk: ...
- Support person: ...
- FAQ live at: ...
- Refund policy live at: ...
- Founder-absence test: PASS / FAIL — ...

### Layer 4 — Decision-making
- Lieutenant: [name]
- Empowerment doc: [link]
- Weekly review cadence: ...
- Exception channel: ...
- 48-hour test: PASS / FAIL — note: ...
- 1-week test: PASS / FAIL — note: ...
- 4-week test: PASS / FAIL — note: ...

## Founder time after
- Hours/week: ...
- What I still own: ...

## Mini-retirement readiness
[Y/N — date eligible to leave for [trip name]]
```

## Common Failure Modes

- **Building the layers in the wrong order.** Decision-making before customer service is a recipe for chaos — there's no record of "what already gets decided how."
- **Skipping the kidnap drill.** "I'm sure it'll be fine" is not a test.
- **Naming the lieutenant but not empowering them.** A lieutenant who has to ask is not a lieutenant.
- **Logging in during the test absence.** The point is to find out what breaks. If you save it manually, you've learned nothing.
- **Treating "automated" as "no humans."** Automation often means *fewer* humans, but the right ones with the right tools. Pure-tech autopilot rarely works for anything that touches customers.

## What to Avoid

- Building this for a muse that hasn't yet validated demand. Send to `/muse-test` first.
- Hiring a lieutenant before there's an empowerment doc. They'll either ask too much or decide too much.
- Trying to architect this in 2 weeks. 2 months is normal. 6 months is fine.

## Related Skills

- **outsourcing** — The people layer. Your VA, support person, lieutenant.
- **interruption-killer** — The empowerment-rules portion of layer 4.
- **muse**, **muse-test** — Prerequisites to this skill.
- **mini-retirement** — The actual use of the freedom this skill creates.
- **eighty-twenty** — Apply periodically — what's now consuming the founder's time, even on autopilot, that shouldn't?
