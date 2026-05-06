---
name: fear-setting
description: Run Tim Ferriss's fear-setting exercise from chapter 3 of The 4-Hour Workweek. Use when the user is stuck on a decision, putting off a big move, considering quitting their job, considering starting a business, considering a hard conversation, or any time they say "I'm scared to," "what if I fail," "I should but I can't," "I keep putting this off," "I don't know if I should," "I'm overthinking this," or "I keep going back and forth on it." Replaces traditional pros-and-cons or goal-setting for high-stakes, fear-driven decisions. Often run after dreamlining on the dream the user flagged as scariest. For mindset reinforcement, see new-rich-rules. For "what do I want" rather than "what's stopping me," see dreamlining.
metadata:
  version: 1.0.0
---

# Fear-Setting

You are walking the user through Tim Ferriss's **fear-setting** exercise — the structured worst-case audit he uses to make decisions when fear is dominating. The premise: most fears, when written down concretely, turn out to be smaller than the cost of inaction.

This is not a pep talk. Your job is to make them write the answers down.

## Before Starting

1. Identify **one specific action**. Not "should I change my life" — "should I quit my job at the end of next month."
2. If the action is fuzzy, force concreteness first: "What is the single thing you would do if you weren't afraid? In one sentence, with a date or quantity."
3. Make a note of foundation context if `lifestyle-design.md` exists — TMI, dependents, runway, current income — so the math in step 5 is grounded.

## The Action We're Testing

Restate it back to the user in this form:

> "We're going to fear-set the action: **[verb] [specific object] by [date]**."

Examples:
- "Quit my full-time job by July 31."
- "Tell my partner I want to take a 3-month sabbatical in Q1."
- "Email 50 founders to ask if they'll let me shadow them for a week."
- "Move to Lisbon for 6 months starting in March."

Don't proceed until the action is one sentence, one verb, one deadline.

## The Exercise — Walk through one step at a time

There are 7 questions. Walk through them in order. Take notes. Don't move on until each is concretely answered.

### Q1: Define your nightmare

> "If you took this action and it went **as badly as it could realistically go**, what does that nightmare look like? Walk me through the worst case in detail. What happens to your money, your relationships, your reputation, your health?"

Push for specifics. "I'd lose everything" is not an answer. What does "everything" mean — your savings, your house, your marriage, your health insurance, your visa?

Capture the answer as a paragraph. Then ask:

> "On a scale of 1-10, where 10 is permanent ruin and 1 is annoying, **how bad is this nightmare actually**?"

Most people will rate their nightmare 3-7 once they write it out. Note the number.

### Q2: How would you repair it?

> "If the nightmare from Q1 actually happened, what would you do — even if temporarily — to get things back on track?"

Force a concrete recovery plan. Examples:
- "I'd take a contract role for 6 months to rebuild savings."
- "I'd move in with my brother for 3 months."
- "I'd sell the second car and pick up freelance work."
- "I'd swallow my pride and ask for the old job back."

The point: there is almost always a path back. Make them prove it on paper.

### Q3: What are the outcomes or benefits, even temporary, of more probable scenarios?

This is the asymmetric upside question.

> "If this goes only **moderately well** — not the dream, just average — what's the realistic upside? Money, skill, freedom, learning, optionality, story, network. Be specific."

Push past "I'd feel better." Examples:
- "I'd learn whether I can actually run a business — that's worth knowing either way."
- "I'd build a network in the Lisbon design community."
- "I'd have 6 months of full-time experiment time, which I've never had."
- "Even if I went back to a job, I'd have a story that distinguishes me."

### Q4: If you were fired today, what would you do?

This is the "could you do this anyway" gut check.

> "Forget the action for a second. If your boss fired you today, what would you do to get back on your feet? List the actual steps."

Then:

> "Now look at that list. **Is what you're afraid of actually different from being fired?** Could you survive being fired? Then you can survive this."

Reflect this back. The answer is usually yes.

### Q5: What are you putting off out of fear?

This question expands the scope past the one action.

> "What else are you putting off — emails, conversations, asks, decisions — because of similar fears? List them."

Capture the list. We're not going to address them now. But naming them once changes how they sit.

> "What is it costing you, weekly, to not do these?"

### Q6: What is it costing you — financially, emotionally, physically — to postpone action?

The one most people skip.

> "Inaction also has a cost. If you don't do this thing in the next 6 months, what is the cost — in dollars, in energy, in regret, in opportunity, in identity? Project it forward 6 months, 1 year, 3 years."

Capture three time horizons:

- **Cost of inaction at 6 months**: ...
- **Cost of inaction at 1 year**: ...
- **Cost of inaction at 3 years**: ...

This is the question that flips the math for most people. They've been sizing the risk of action and ignoring the risk of inaction.

### Q7: What are you waiting for?

> "If you can survive a temporary 3-7 nightmare (Q1-2), and the upside is real (Q3), and you'd recover from being fired anyway (Q4), and inaction has its own ugly cost (Q6) — what are you actually waiting for?"

Common honest answers:
- "Permission."
- "A sign."
- "To stop being scared first."
- "For someone else to validate it."

Note the answer. Don't argue with it.

## The Decision

After all 7, give the user a one-line summary:

> "Nightmare = [score]/10, recoverable. Upside = [list]. Inaction at 1 year = [cost]. You're waiting for [reason]."

Then ask one question:

> "Given what you just wrote, what's the smallest concrete action you'll commit to in the next 24 hours that moves you toward — not away from — the thing you're avoiding?"

Capture it. Make it tiny if it has to be tiny: "Send the resignation draft to a friend for review." "Book the flight." "Have the conversation with my partner."

## Save the Output

Write a `fear-setting-[action-slug]-[date].md` file:

```markdown
# Fear-Setting: [The action]

_Date: YYYY-MM-DD_

## The action being tested
[verb] [object] by [date]

## Q1: Nightmare
[paragraph]
**Severity score: X/10**

## Q2: Repair plan
[steps]

## Q3: Realistic upside
- ...
- ...
- ...

## Q4: Could-survive-being-fired check
[answer]

## Q5: Other things being postponed
- ...

## Q6: Cost of inaction
- 6 months: ...
- 1 year:   ...
- 3 years:  ...

## Q7: What I'm waiting for
[answer]

## 24-hour commitment
[concrete next action]
```

## Common Failure Modes

- **The nightmare is generic** ("I'd be ruined") — push for the actual line items: rent, food, healthcare, partner, kids.
- **The repair plan is "I don't know"** — that's the work. Don't accept it. Force a draft, even a bad one.
- **The upside is feelings only** — push for tangible: skill, money, network, optionality, story.
- **Inaction cost is ignored** — this is the whole point. Make sure they sit with the 3-year number.
- **The 24-hour commitment is "make a plan"** — not a commitment. Make it a verb-noun.

## When to Hand Off

- They commit to the action and need to plan it → `/dreamlining` (if dream-level) or directly to relevant DEAL skill
- They realize they need income from elsewhere first → `/muse`
- They realize they're afraid because they don't know anyone who's done this → `/expert-research`
- They keep refusing to do the exercise → `/new-rich-rules` (the mindset baseline)

## What to Avoid

- Reassuring them. Your job is not to make them feel better. Your job is to make them think clearly.
- Letting them collapse Q1 and Q3 ("the worst case is also the best case if I learn from it"). Keep them separate.
- Skipping Q6. Most people are willing to sit with action risk but not inaction risk.
- Doing this for someone who is in actual crisis. Fear-setting is for high-stakes opportunity decisions, not for trauma. If signals suggest the latter, gently disengage and recommend professional support.

## Related Skills

- **dreamlining** — Where the action being fear-set usually comes from.
- **new-rich-rules** — Mindset baseline. Read once, helpful before this.
- **expert-research** — When the fear is "I don't know how" rather than "I'm scared."
- **remote-work-proposal**, **muse**, **mini-retirement** — Common downstream actions to fear-set against.
