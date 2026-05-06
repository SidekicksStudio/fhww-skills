---
name: muse-launcher
description: Rapid-deployment scaffold for a validated muse — the 2026 build phase. Once /muse and /muse-test pass, this skill stands up a real landing page, payments, email capture, ads, and analytics in hours, not weeks. Use when the user says "I'm ready to build my muse," "launch the muse," "ship it," "scaffold the landing page," "stand up the muse infrastructure," "build the muse for real," or "what stack should I use." Hard gate — refuses to run without a passing /muse-test result, because the most common founder failure is over-building before validating. Cross-references coreyhaines marketing skills (page-cro, copywriting, analytics-tracking, paid-ads) where they exist; otherwise self-contained.
metadata:
  version: 1.0.0
---

# Muse Launcher

You are helping the user **stand up the actual infrastructure** for a muse that has already passed scoring (`/muse`) and demand validation (`/muse-test`). This is the 2026 version of the book's "Income Autopilot I-II" chapters — but compressed from weeks to hours, because in 2026 the technical setup is largely solved.

Your most important job: **prevent over-building**. The single most common founder failure is to skip the test, build for 4 months, and discover at launch that nobody wants it. This skill enforces the order.

## Before Starting — The Hard Gate

Refuse to run unless **both** are true:

1. **A muse evaluation file exists** (`muse-evaluation-*.md`) showing a "Strong" or "Salvageable" verdict.
2. **A muse test file exists** (`muse-test-*.md`) showing a "Strong signal" or, at minimum, recent re-tested signal that's borderline-passing.

If either is missing, do not proceed. Send the user to `/muse` and `/muse-test` first. Be firm:

> "We're not going to build until we've tested. The whole point of the framework is to spend $300 and 5 days finding out if anyone wants this — before spending 80 hours building it. If the test passed, share the file. If it didn't, we go back and reshape."

Once both files exist, proceed.

## What This Skill Builds

A working muse needs 6 layers operational on day one:

| Layer | Purpose | Modern default |
|---|---|---|
| 1. Landing page | Where the offer lives | Next.js + Vercel, or Framer / Carrd for v1 |
| 2. Payments | Take the customer's money | Stripe / Lemonsqueezy / Paddle |
| 3. Email capture | List + post-purchase | MailerLite / ConvertKit / Resend |
| 4. Fulfillment | Deliver the product | Stripe-triggered email + asset, or 3PL |
| 5. Ads / acquisition | Drive cold traffic | Google / Meta / X / Reddit |
| 6. Analytics | Know what's working | PostHog / GA4 + UTM hygiene |

## The Stack — Recommended Defaults

These are opinionated. The user can substitute, but defaults exist so the skill doesn't stall on choice paralysis.

### Path A — "I want to ship today, no code"

Use this if the muse is digital, the user is non-technical, and ship-this-weekend matters more than long-term flexibility.

- **Landing page**: Framer (fastest pretty), Carrd (cheapest), or Squarespace
- **Payments**: Lemonsqueezy or Stripe payment links (no checkout build)
- **Email**: MailerLite (cheapest) or ConvertKit (better automation)
- **Fulfillment**: Lemonsqueezy auto-delivers digital files; or Zapier/Make.com on Stripe webhook → email
- **Ads**: One channel — usually Meta or Google. See `/muse-test` for which
- **Analytics**: GA4 + simple UTM links

Time to live: 4-12 hours.

### Path B — "I want a proper foundation"

Use if the muse will scale and the user is comfortable in code (or with Claude Code / Cursor as a co-builder).

- **Landing page**: Next.js (App Router) deployed on Vercel
- **DB / forms / auth (if needed)**: Supabase
- **Payments**: Stripe (full Checkout + webhooks for fulfillment + dunning)
- **Email**: Resend for transactional + ConvertKit/MailerLite/Loops for marketing
- **Fulfillment**: Stripe webhook → serverless function → email asset / provision access
- **Ads**: Google Ads + Meta + (optionally) Reddit + UTM in every URL
- **Analytics**: PostHog (or Plausible) + GA4 + Meta Pixel + Google Ads conversion API

Time to live: 1-3 days with AI-assisted code.

### Path C — "Physical product"

- **Landing page**: Shopify (themes are fine; don't over-design)
- **Payments**: Shopify Payments + Shop Pay for conversion lift
- **Email**: Klaviyo (Shopify-native flows)
- **Fulfillment**: ShipBob / ShipMonk / regional 3PL — DO NOT self-fulfill past unit 50
- **Ads**: Meta + Google + (if reviewable) Reddit
- **Analytics**: Shopify native + GA4 + Meta CAPI

Time to live: 1-2 weeks, with most of the time waiting for inventory and 3PL onboarding.

Pick the path with the user. Don't agonize. The path is reversible.

## Step 1: Lock the offer

Before any building, capture in writing:

- **The one-liner** (carry over from `/muse`)
- **The price** (the validated price from `/muse-test`)
- **The promise** (what specific outcome does the buyer get?)
- **The mechanism** (in 2 sentences — why does this produce the outcome?)
- **The proof** (one or two specific credibility cues; testimonials if any)
- **The guarantee** (refund window, satisfaction guarantee, etc. — for digital, 14-30 day refund is standard)

This is the substrate every layer uses. Don't open a single editor before this is written.

## Step 2: Build the landing page

For Path A: drag-and-drop in Framer/Carrd from a SaaS landing template.

For Path B: Claude Code / Cursor can scaffold Next.js + Tailwind + a single hero + feature + pricing + FAQ + CTA in 30-60 minutes. Use this prompt as the skeleton:

```
Build a Next.js 15 (App Router) landing page on Vercel for [product]
priced at $[price] for [target market].

Sections in order:
1. Hero — headline (the outcome), subhead (audience + price), primary CTA
2. Three feature/mechanism bullets
3. One specific testimonial with photo + name + outcome
4. Pricing card with Stripe Checkout link / button
5. FAQ — 5 questions: refund, shipping/delivery, who it's for, who
   it's not for, why this not [obvious alternative]
6. Footer with company name, contact, terms, privacy

Use Tailwind. Mobile-first. Single page, no nav. No animations. No
modal popups. No cookie banner unless user is in EU.

Add UTM-aware tracking: capture utm_source/medium/campaign/content/term
and pass through to the Stripe metadata. Add data layer events for:
page_view, cta_click, checkout_started, checkout_completed.
```

Cross-reference: if you have access to `coreyhaines/marketingskills/copywriting` and `page-cro` skills, hand the headline and section-by-section copy to them — they're better at this part.

## Step 3: Wire payments

For Path B (Stripe):

1. Create a product + price in Stripe ($X recurring or one-time, matching `/muse-test`)
2. Use Stripe Checkout (don't build a custom checkout for v1)
3. Wire a webhook to a serverless function (Vercel route handler `/api/stripe-webhook`):
   - On `checkout.session.completed`: deliver the asset / provision access / send the welcome email
   - On `charge.failed`: trigger dunning sequence
4. Test with a real $0.50 charge to your own card. Refund. Confirm the webhook fired.

For Path A (Lemonsqueezy or Stripe Payment Link):

- Lemonsqueezy: built-in checkout, auto-delivers digital products. Configure in their UI.
- Stripe Payment Link: faster than Checkout, less customizable. Good for v1.

## Step 4: Wire email

Two flows:

### Transactional (Resend / Postmark / SendGrid)

- Order confirmation
- Asset delivery (with download link or access link)
- Refund confirmation (when applicable)
- Failed payment + recovery

### Marketing (MailerLite / ConvertKit / Loops)

- Welcome sequence (3-5 emails over 14 days)
- Pre-purchase nurture (for the email list capture, which converts later)
- Win-back / upsell sequences (build later — not at launch)

For Path A: MailerLite has the simplest free tier. ConvertKit has better automation.

For Path B: Resend for transactional, ConvertKit/MailerLite/Loops for marketing.

Cross-reference: `coreyhaines/marketingskills/email-sequence` if available — much better at the actual writing.

## Step 5: Wire ads

Pick **one** ad channel per the `/muse-test` finding. Don't multi-channel at launch.

For Google Ads:
- 1 campaign, 2-3 ad groups based on the keyword themes
- Search ads: 3 RSAs per ad group
- UTMs auto-tagged
- Conversion tracking via tag manager OR Conversion API (server-side)
- Daily budget: 1.5-2x the `/muse-test` daily budget for the first 14 days

For Meta Ads:
- 1 campaign, 1-2 ad sets
- 3-5 creative variants in each
- Conversion API (server-side via Stripe webhook → Meta CAPI)
- Daily budget: same as Google guidance

For Reddit / TikTok / LinkedIn / YouTube — pick one only if `/muse-test` showed it's where the audience is.

Cross-reference: `coreyhaines/marketingskills/paid-ads` and `ad-creative` if available.

## Step 6: Analytics — UTMs in every URL, events on every action

The most-skipped layer. Without it, every following decision is guessing.

Required events (minimum):

- `page_view` (with UTM data captured)
- `email_capture`
- `checkout_started`
- `checkout_completed`
- `refund_issued`

Required reports:

- Cost per checkout-completed by campaign / ad / creative
- Day-of-week pattern
- Refund rate
- Email-capture-to-purchase rate

Path A: GA4 + UTM tagging is fine for v1.
Path B: PostHog (better funnels) + GA4 (Google Ads attribution) + Meta Pixel.

Cross-reference: `coreyhaines/marketingskills/analytics-tracking` if available.

## Step 7: The 4-week launch loop

Once live, the loop runs every Friday for 4 weeks:

| Week | Action |
|---|---|
| Week 1 | Watch CAC. Kill any ad above 80% of price. Test 1 new headline variant. |
| Week 2 | Optimize the top 1-2 ads. Cut the bottom. Test 1 page variant (headline or CTA). |
| Week 3 | Decide: scaling work or product-market mismatch? If CAC ≤ 30% of price, scale. |
| Week 4 | If scaling: triple the daily ad budget. If not: reshape (back to `/muse`). |

After 4 weeks, route to:
- **Strong**: `/income-autopilot` — make it run without you
- **Mixed**: `/muse-test` again with a different angle
- **Weak**: `/muse` — full reshape, possibly different muse

## Step 8: Save the launch state

Write `muse-launch-[name]-[date].md`:

```markdown
# Muse Launch: [name]

_Launched: YYYY-MM-DD_

## Offer
- One-liner: ...
- Price: $...
- Promise: ...
- Mechanism: ...
- Proof: ...
- Guarantee: ...

## Stack
- Path: A / B / C
- Landing: [URL] ([platform])
- Payments: [provider, product ID]
- Email: [marketing tool, transactional tool]
- Fulfillment: [method]
- Ads: [channel(s), campaign IDs]
- Analytics: [tools, dashboard URL]

## Day-1 metrics
- Page CVR: ...%
- Cost per checkout: $...
- Refund rate: ...%

## 4-week loop
- Week 1: ...
- Week 2: ...
- Week 3: ...
- Week 4: ...

## Decision after 4 weeks
[Scale / Reshape / Kill]
```

## What to Avoid (the over-building patterns)

These are the most common founder failure modes at this stage. Push back hard on any of them:

- **Custom design system before launch.** No. Use a template.
- **Custom checkout flow before launch.** No. Use Stripe Checkout / Lemonsqueezy.
- **Multi-tier pricing on day one.** No. Single tier, single price.
- **Multi-product on day one.** No. One SKU.
- **Custom email automations beyond welcome.** No. Welcome + asset delivery only.
- **Mobile app before web works.** No.
- **Logo, brand identity, naming exercise.** No. Workable name + 30-min logo. Move on.
- **"Soft launch to friends" before paid traffic.** No. Friends will lie. Run paid.
- **Multi-channel ads day one.** No. One channel until it works.

The user will want to do all of these. Use one phrase: **"That's a Week 5+ problem."**

## Common Failure Modes (in build, not in offer)

- **Building Path B when Path A would have worked.** Don't.
- **Skipping webhook tests.** Stripe webhook silently failing is the #1 launch bug.
- **No UTM hygiene.** Every paid link must have UTMs. Every organic share, too.
- **Not testing the refund flow.** Issue a real refund to yourself. Confirm the email fires, the webhook fires, the access is revoked (if applicable).
- **Not setting up alerts for "no orders today."** Goes 3 days without a sale; user notices on day 4.

## Related Skills

- **muse** — Required gate.
- **muse-test** — Required gate.
- **income-autopilot** — Where you go after 4 weeks of strong signal.
- **automate-first** — Before adding new functionality, run the task through this skill.
- **make-it-a-skill** — Operations of the muse (weekly summary, dunning review, reorder triggers) become skills + scheduled tasks.
- **deep-research** — When you need to grind through competitor pricing, market sizing, etc. before launch.
- **outsourcing** — Step 0 of outsourcing tells you which muse-ops tasks are AI vs. VA.

## External Skills (if installed)

- `coreyhaines/marketingskills/copywriting` — for landing page words
- `coreyhaines/marketingskills/page-cro` — for landing page conversion
- `coreyhaines/marketingskills/paid-ads` — for ad campaign structure
- `coreyhaines/marketingskills/ad-creative` — for ad variants
- `coreyhaines/marketingskills/analytics-tracking` — for analytics setup
- `coreyhaines/marketingskills/email-sequence` — for welcome / nurture flows
- `coreyhaines/marketingskills/launch-strategy` — for launch announcements

If any of these are installed in your agent environment, prefer them over re-implementing the marketing knowledge here. They're more thorough on the marketing-specific details. This skill is the orchestrator that calls them in sequence.
