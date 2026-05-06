---
name: deep-research
description: Run an AI deep-research agent on a question — the 2026 counterpart to /expert-research, used when the question is answerable from public sources at scale rather than from human interviews. Use when the user says "do deep research on," "research this for me," "find me everything about," "competitive analysis," "market sizing," "compile sources," "summarize the literature," "what's been written about," or after /automate-first lands on Gate 4 (one-shot AI agent run). Includes the prompt structure that produces the highest-quality runs, what NOT to use it for, when to escalate to /expert-research (humans) instead, and how to verify the agent's output before trusting it.
metadata:
  version: 1.0.0
---

# Deep Research

You are helping the user run an **AI deep-research agent** on a specific question — the kind of grind-through-the-internet, compile-sources, produce-a-structured-output task that used to take a VA two days and now takes an agent twenty minutes.

This skill is the AI counterpart to `/expert-research`. The two are complementary, not interchangeable:

- `/expert-research` — used when the answer lives in **someone's head** and you need to ask
- `/deep-research` — used when the answer lives in **public sources** and you need to compile

Use both when the question warrants it. They produce different findings.

## Before Starting

Get from the user:

1. **The actual question** — in one sentence, written precisely. ("What's the typical churn rate for SaaS in the $50-150 ARPU band, by industry?" — not "tell me about churn.")
2. **What decision this feeds** — research without a downstream decision is academic; this skill is for actionable research
3. **What public sources exist** — the user usually knows the categories: forums, Reddit, podcasts, public reports, court records, academic papers, GitHub, public APIs
4. **The output format the user actually wants** — table, ranked list, executive summary, comparison matrix, one-page brief

If the question is fuzzy, sharpen it before running. The agent is only as good as the question.

## When to Use This Skill

The sweet spot for deep-research is questions that meet **all** of these:

- Answerable from public sources (web, public APIs, public docs)
- The work is volume-and-pattern-recognition, not deep judgment
- The user can verify the answer afterward in <30 minutes
- The cost of "good enough but slightly wrong" is low

Examples that fit:

- "Compile every direct competitor of [product] and their pricing tiers"
- "What's been published about [topic] in the last 18 months — papers, posts, podcasts — by relevance"
- "Summarize the regulatory landscape for [product category] in the EU vs. US"
- "Find all the indie hackers who've launched products in [niche] and how they did at launch"
- "Compile expat forum threads on [city] that discuss [specific issue]"
- "Build a comparison matrix of every [X] under $Y with [criteria]"
- "Map every podcast episode that interviewed [person] in the last 24 months"

## When NOT to Use This Skill

Push back if the question is any of these:

- **Requires asking specific humans for their direct experience.** That's `/expert-research`. Deep research can find what people *wrote*; it can't extract what someone *thinks but didn't write*.
- **Requires private / behind-paywall sources** the user can't access. Hand off to a domain expert or research firm.
- **Requires real-time decisions** (legal advice, medical advice, security incident response). Get a qualified professional.
- **The cost of being wrong is high.** Anything where one bad source could create a serious downstream error — financial commitments, medical decisions, legal moves.
- **The question is "how do you feel about this."** That's `/expert-research`, possibly `/cold-outreach`.

## Step 1: Sharpen the question

Take the user's question and refine to a research brief. Walk through:

### A. The single most important sentence

Restate the question in **exactly one sentence**, as specifically as possible. Examples:

- "What is the median monthly all-in cost (rent + utilities + groceries) of living in Lisbon's Príncipe Real neighborhood for a single American freelancer in 2026?"
- "Which 10 newsletters in [niche] have the largest verifiable subscriber counts, and what do their sponsorship rates look like?"
- "What are the 3 most-cited critiques of [methodology] from peer-reviewed sources in the last 5 years?"

### B. The acceptance criteria

What would make the answer "good enough"? Capture:

- Number of sources required (e.g., minimum 15 sources)
- Diversity of sources (e.g., no more than 3 sources from any single domain)
- Recency (e.g., 80%+ of sources from the last 24 months)
- Format (table, list, exec summary)
- Length (1 page / 3 pages / 10 pages)

### C. Out-of-scope flags

What is *not* the question? Naming this saves the agent (and you) hours of going down rabbit holes.

## Step 2: The deep-research prompt template

The single biggest determinant of output quality is the prompt structure. Use this template:

```
DEEP RESEARCH BRIEF

# QUESTION
[The single sentence from Step 1.A]

# CONTEXT
[2-3 sentences — what decision this feeds, why this matters, who's
asking. Don't include personal info beyond what's needed.]

# SCOPE
- Time horizon: [last X months / years]
- Geography: [US only / EU only / global / specific countries]
- Source types to include: [list — academic, forum, news, podcast,
  GitHub, court, regulatory, public datasets]
- Source types to exclude: [if any — paid reports, paywalled academic
  unless freely available, social media speculation]

# OUT OF SCOPE
- [thing 1 not the question]
- [thing 2 not the question]

# OUTPUT
- Format: [table / list / brief / matrix]
- Length: [page count or word count]
- Required fields per item: [columns / bullets]
- Sources: cite each finding with URL + date

# CONFIDENCE FLAGGING
For each finding, label:
- HIGH: 3+ independent sources agree
- MEDIUM: 1-2 sources, plausible
- LOW: single source or inferred

# DELIVERABLE
A markdown document with:
1. Executive summary (3 bullets)
2. The structured output (table / list / matrix)
3. "Things I couldn't find" — explicit gaps
4. "Things that surprised me" — patterns the agent noticed
5. Source list with URLs
```

## Step 3: Run the agent

Hand the brief to the deep-research tool the user has access to. Several options in 2026:

| Tool | Strengths | Notes |
|---|---|---|
| Claude with web search + extended thinking | Strongest reasoning, good for nuanced compilations | Verify currency of sources |
| ChatGPT Deep Research / o3 + browse | Heavy lifting on long lists | Verify sources actually say what's claimed |
| Gemini Deep Research | Wide source surface | Verify reasoning, not just sources |
| Perplexity Deep Research | Fast for quick scopes | Less depth on long compilations |
| A bespoke agent / Claude Code with web tools | Full control over what's searched and how | Most setup |

Run on the user's preferred tool. If unsure, default to whichever is currently best at long-context citation.

If the run takes >30 minutes of agent time, set the user's expectation — and use the time to start `/expert-research` in parallel if humans should also be asked.

## Step 4: Verify the output

This is the step most people skip. AI deep-research is faster than a human VA, **and also more confident when wrong**. Always verify before trusting.

For each HIGH-confidence finding:

- Click through to **at least one** source. Does it actually say what the agent claims?
- Is the source a real source, or a hallucinated URL?
- Is the date current enough?

For MEDIUM/LOW findings:

- Don't act on them without your own additional verification
- Use them as leads, not conclusions

For the gaps:

- "Things I couldn't find" is a real signal. If the agent failed to find pricing for 3 of the 10 competitors, that's not laziness — those competitors may be opaque on purpose. Dig in.

A useful heuristic: spend ~10% of the time the agent took, on verification. 30-min agent run → 3 min of clicking through.

## Step 5: Decide what's next

After verification, the user has 3 paths:

1. **The research answered the question** → make the decision, save the brief
2. **Partial answer + clear gaps** → run `/expert-research` on the gaps (humans for what wasn't writable)
3. **Wrong question** → re-sharpen and re-run, with what was learned

If the research surfaces a question that wasn't the original one, that's normal. Use the new question as the input to either another deep-research run or `/expert-research`.

## Save the Output

Write `deep-research-[topic-slug]-[date].md`:

```markdown
# Deep Research: [topic]

_Date: YYYY-MM-DD_
_Tool: [agent used]_
_Run time: [minutes]_

## Question
[One sentence]

## Brief (sent to agent)
[The full prompt from Step 2]

## Output

### Executive summary
- ...
- ...
- ...

### Findings
[Table / list / matrix from agent — pasted in]

### Things the agent couldn't find
- ...

### Things that surprised the agent (or me)
- ...

### Sources
- ...
- ...

## Verification

| Finding | Confidence | Verified? | Note |
|---|---|---|---|
| ... | HIGH | ✓ | ... |
| ... | MEDIUM | ✗ | needs follow-up |

## Decision implied
[What I'm going to do based on this]

## Follow-up
- Run /expert-research on: [gap]
- Re-run deep-research with sharper question: [new question]
```

## Common Failure Modes

- **Vague question.** "Research my market" produces nothing useful. Sharpen first.
- **No verification.** AI makes up sources. Always click through HIGH findings.
- **Treating gaps as failures.** Gaps are signal — surface them and ask why.
- **Skipping the human follow-up.** Some questions can only be answered by talking to humans. Pair with `/expert-research`.
- **Running on questions that needed a quick answer, not deep research.** Don't deploy a deep-research agent for "what's the tax rate in Portugal for freelancers" — a single search answers that.

## What to Avoid

- Trusting deep-research for legal, medical, or financial advice. The agent doesn't know your situation. Use it for context; consult a professional for decisions.
- Asking for "everything about [topic]." Scope it.
- Running multiple deep-research agents on the same question and averaging. They make correlated errors. Better: one agent + verification + (if needed) `/expert-research`.

## Cost / Time Notes

- A typical deep-research run: 5-30 minutes of agent time, $0.50-$5 in API cost (or covered by your subscription).
- Compared to a human VA: 10-100x faster, 10-1000x cheaper.
- Compared to doing it yourself: 5-50x faster, but with verification overhead.
- Compared to `/expert-research`: complementary, not substitutable. Both, when the question warrants.

## Related Skills

- **expert-research** — For when the answer is in someone's head, not on the internet. Pair with this skill, don't substitute.
- **automate-first** — Lands on this skill when Gate 4 fires (one-shot AI agent run).
- **outsourcing** — Step 0 of outsourcing routes most "research" tasks here, not to a human VA.
- **muse** — Use deep-research to compile competitor matrices and market sizing before scoring.
- **muse-test** — Use deep-research to find ad placements, audience communities, channel benchmarks.
- **muse-launcher** — Use deep-research to compile platform docs, examples, and pricing references for the build.
- **mini-retirement** — Use deep-research to compile destination logistics (visas, neighborhoods, costs).
