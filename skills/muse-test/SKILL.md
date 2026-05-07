---
name: muse-test
description: Cheaply test demand for a muse before building it — Tim Ferriss's landing-page-and-ads validation method from The 4-Hour Workweek (chapters on Income Autopilot I-II), now updated for modern paid-ads platforms. Use when the user says "should I build this," "how do I validate," "will anyone buy this," "I have a business idea, want to test it," or "I want to do a fake door test." Walks through the 5-day micro-test: landing page, $200-500 ad budget, click-to-checkout flow that captures intent without requiring inventory. Run after /muse to confirm scoring. For pre-build product evaluation, see muse. For automating a confirmed muse, see income-autopilot.
metadata:
  version: 1.0.0
---

# Muse Demand Test

You are helping the user run the **muse demand test** — Tim's small, cheap experiment to find out whether anyone will actually pay for a muse before building, manufacturing, or stocking anything.

The premise: if your real cost of finding out is two weekends and $500, there is no defensible reason to skip it.

The classic version in the book used Google AdWords. The modern version is the same shape — a landing page, paid traffic, and a checkout intent — across whichever ad network reaches the target market.

## Before Starting

1. The user must have already run `/muse` and have a passing or salvageable score.
2. Have the **one-liner** ready: "[Product] for [target market] that does [outcome] for $[price]."
3. Have a sense of where the target market lives online (this came out of Q1 of the muse audit).

If any of these are missing, send them to `/muse` first. Don't run the test on a vague idea.

## The 5-day plan

This skill walks the user through a 5-day, ~$300-$500 test. Adjust if their TDI/risk tolerance is materially different — but resist running it for "longer to be safe." Longer tests are usually procrastination.

### Day 1 — Landing page

Build a single landing page that does **one thing**: lets a visitor click "Buy" or "Reserve."

Required elements:

1. **Headline** — the outcome, in their language. Not the product. ("Stop bonking after mile 18." not "Buy our gel.")
2. **Subhead** — who it's for and the cost. ("A $39 endurance gel for marathoners. Ships in 7 days.")
3. **3 bullets of mechanism** — *why* this works for them. Light proof — a credentialed quote, a stat, a spec.
4. **2 testimonials** — can be your beta users, peers in the field, or quoted experts. Real names, real outcomes.
5. **A "Buy now" or "Reserve" button** — visible above the fold and again at the bottom.
6. **A 3-question FAQ** — the actual top 3 buying objections.

Stack: Carrd, Framer, a single Webflow page, a Shopify product with no inventory, a basic Next.js page — pick whatever the user can ship today. The point is the page exists by end of Day 1.

### Day 2 — The intent capture

Wire the "Buy" button to one of two paths, depending on appetite:

**Path A — Soft test (no money charged):**
- "Buy" goes to a checkout that, on submit, says: "Sorry — we just sold out of our pre-launch batch. Enter your email and we'll notify you when the next batch ships, with a 20% discount."
- Capture the email. **The metric: % of clicks that completed checkout intent.**

**Path B — Hard test (charge or pre-authorize):**
- Charge real money via Stripe / Shopify / Gumroad / Lemonsqueezy.
- If the user backs out before fulfilling, refund cleanly with: "Pre-orders ended; refunding now. We'll keep you posted."
- This is uncomfortable but produces the cleanest signal.

Path B has higher signal, Path A has lower friction. If the user is squeamish, run A and accept the noisier data.

Be transparent about which path they're picking and why. Note: in some jurisdictions the "sold out" framing has consumer-protection implications. Recommend Path B if the user has any doubts, or be very clean with the language in Path A ("Reserve interest — no payment").

### Day 3 — Ads

Pick **one** channel — the one closest to where the target market actually lives. Don't multi-channel.

| If the target market lives in… | Run ads on… |
|---|---|
| Google search for a known phrase | Google Search Ads |
| Instagram aesthetic-driven niches | Meta Ads |
| Reddit subs / hobbyist forums | Reddit Ads (or organic post + comment) |
| LinkedIn (B2B, professional niches) | LinkedIn Ads |
| TikTok-native niches | TikTok Ads |
| Email lists they already own | Newsletter sponsorships |

Build **3 ad variants**:
1. Pure outcome ("Stop bonking after mile 18.")
2. Specific objection / before-after ("Tired of taping gels to your shorts and getting sticky hands?")
3. Social proof / authority ("What 40 sub-3:00 marathoners are switching to.")

Budget: **$200-400 over 3 days**, evenly split across 3 ads.

### Day 4 — Watch the funnel

What you measure:

1. **CTR** (click-through rate on ads) — is the headline pulling?
2. **Landing page CVR** (% of visitors who hit Buy) — does the offer make sense?
3. **Checkout intent rate** (% of clicks that completed the soft or hard checkout) — do they actually want it?
4. **Cost per intent** = (ad spend) / (number of completed checkout intents)

Benchmarks to anchor (these are rough; calibrate to industry):

- Solid B2C: $10-30 cost per intent on a $50-150 product.
- Solid B2B / niche pro: $40-150 cost per intent on a $200+ product.
- Above the high end of the range: kill or reshape.

### Day 5 — The decision

Three possible outcomes:

**Strong signal** — cost per intent is below 25% of the product price.
→ Proceed to build / fulfill. Run `/income-autopilot` next.

**Mixed signal** — cost per intent is 25-60% of product price.
→ Don't build yet. Re-test with reshaped headline, or narrower target market, or higher price (Tim: more often than people expect, raising price increases conversion).

**Weak signal** — cost per intent above 60% of product price, or fewer than 5 intents.
→ Either the wrong target, the wrong offer, or both. Go back to `/muse` and reshape. Don't keep spending into a no.

## Operational details

### Honoring intent

- If you charged real money (Path B), and the test was a no-go: refund within 48 hours with a clean note. Don't ghost.
- If you captured emails (Path A), and you're proceeding: deliver in the timeframe you promised.
- If you captured emails and you're killing the idea: write *one* honest email saying so. Most users will respect it. A few will tell you exactly what they actually wanted, which is gold.

### Two ethical lines

1. Never claim a result, certification, or credential you don't have. Tested idea or not, that's fraud.
2. If a real product would carry health or legal risk (supplements, financial claims, regulated equipment), do *not* test with the live product on a Path A page implying it exists. Use a clearly-labeled waitlist instead.

## Save the Output

Write `muse-test-[idea-slug]-[date].md`:

```markdown
# Muse Test: [idea]

_Run dates: YYYY-MM-DD to YYYY-MM-DD_

## What we tested
[one-liner]
Path: [A soft / B hard]

## Setup
- Landing page: [URL]
- Ad channel:   [...]
- 3 ad variants: ...
- Budget:       $...

## Results
| Metric | Value |
|---|---|
| Total ad spend | $... |
| Clicks | ... |
| Landing page visits | ... |
| Checkout intents | ... |
| CTR | ...% |
| Page CVR | ...% |
| Cost per intent | $... |

## Decision
[Strong / Mixed / Weak] → [Build / Re-test / Kill]

## Handoff artifact
If Decision = Strong or Mixed-proceeding, fill this out so `/muse-launcher` can promote rather than rebuild:

- Landing page URL: [live URL]
- Platform: [Carrd / Framer / Webflow / Next.js / other]
- Ad channel: [Google / Meta / Reddit / etc.]
- Ad account ID: [...]
- Top-performing ad variant: [paste headline + body]
- Validated price: $[...]
- Checkout/intent setup: [Path A email capture / Path B Stripe product ID / Gumroad link / etc.]
- Copy notes: [what headline/angle pulled, what flopped]

## What I'd change next time
- ...
```

## Common Failure Modes

- **Running the test on a half-broken page.** Cheap is fine; broken is not. The variable being tested is demand, not how scrappy your wireframe was.
- **Using your own audience for the test.** Your existing followers are biased. Use cold paid traffic.
- **Multi-channel from day 1.** You won't be able to interpret signal. Pick one.
- **"Let me just run it another week."** That is procrastination. Set the budget cap, hit it, decide.
- **Ignoring the cost per intent and going by gut.** "It feels like it's working" is not the test result.

## Related Skills

- **muse** — Pre-test scoring. Required input.
- **income-autopilot** — Where you go after a strong signal.
- **cold-outreach** — If the target market is small/niche, sometimes a 30-email cold outreach test outperforms paid ads. Hand off when paid ads are the wrong tool.
- **expert-research** — If the test fails ambiguously, find someone who's run a similar product and ask why.
