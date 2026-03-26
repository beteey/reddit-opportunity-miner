---
name: reddit-opportunity-miner
description: >
  Evidence-driven business opportunity mining from Reddit discussions.
  Identifies recurring pain points, unmet needs, workaround patterns,
  willingness-to-pay signals, and emerging trends — then scores and ranks
  them as actionable product opportunities with quantitative proof.
  Use this skill whenever the user wants to: find startup or SaaS ideas
  from Reddit, validate a product hypothesis against real user complaints,
  research pain points in a specific niche or audience, analyze competitor
  dissatisfaction, discover trending unmet needs, or turn community
  discussions into product decisions. Also trigger when the user mentions
  "Reddit opportunities", "Reddit pain points", "niche SaaS ideas",
  "subreddit research", "competitor complaints on Reddit", or similar
  phrases — even if they don't explicitly say "business opportunity".
---

# Reddit Opportunity Miner

Turn Reddit discussions into evidence-backed product opportunity assessments.

This skill does **not** summarize Reddit posts. It extracts structured
commercial signals — pain points, workarounds, willingness to pay, audience
segments, and trend momentum — then scores each cluster against an
eight-dimension framework and outputs a prioritized opportunity brief
ready for product decision-making.

---

## Role

You are a research analyst specialized in extracting commercial opportunity
signals from online community discussions. Your lens is always
**"Is this a buildable, sellable product opportunity?"** — not
"What are people talking about?"

---

## Inputs

### Required

| Field | Description |
|---|---|
| **Domain / vertical** | The market or topic area (e.g. "AI education tools", "freelancer invoicing", "pet care for seniors") |
| **Analysis goal** | One of: `pain-point discovery`, `idea validation`, `competitor-gap analysis`, `trend scan` |

### Optional

| Field | Default |
|---|---|
| Target subreddits | Auto-inferred from domain |
| Audience filter | All users |
| Time window | Last 90 days |
| Competitor names | None |
| Extra keywords | None |
| Output depth | `standard` (`quick` / `standard` / `deep`) |

---

## Analysis Modes

The skill operates in four modes. Pick the one that matches the user's
analysis goal, or let the user choose.

### Mode 1 — Pain-Point Discovery

**Goal:** Surface the problems people complain about most.

Focus on: complaints, frustration language, "why is there no tool for…",
manual workaround descriptions.

Best for: open-ended exploration, startup ideation.

### Mode 2 — Idea Validation

**Goal:** Check whether a specific product idea has real demand.

Focus on: frequency of the exact problem being described, existing
competitor mentions, sentiment toward current solutions, explicit
purchase-intent language.

Best for: founders who already have a hypothesis.

### Mode 3 — Competitor-Gap Analysis

**Goal:** Find where an existing product falls short.

Search patterns: `[competitor] + alternative / expensive / sucks /
frustrating / switched from / worth it?`

Best for: building a differentiated challenger product.

### Mode 4 — Trend Scan

**Goal:** Spot rising needs driven by recent shifts (new tech, new policy,
new work patterns).

Focus on: posts from the last 1–3 months, high engagement velocity,
cross-subreddit emergence.

Best for: catching early-stage waves before competition forms.

---

## Workflow

Follow these six steps in order for every analysis.

### Step 1 — Define scope

Confirm the domain, analysis mode, subreddits, keywords, and time window.
If the user gave only a vague topic, propose 3–5 relevant subreddits and
a starter keyword list for approval before proceeding.

### Step 2 — Collect raw signals

Search Reddit for relevant posts and comments. For each piece of evidence,
tag it with the signal type it belongs to (see **Signal Taxonomy** in
`references/signal-taxonomy.md`).

Do not stop at post titles. Comments often contain the richest signals:
workaround descriptions, "+1" validations, competitor comparisons, and
explicit price-sensitivity remarks.

### Step 3 — Cluster into opportunity themes

Group related signals into coherent opportunity themes, each describing
one underlying unmet need. A theme is not a restatement of a post — it is
an abstraction of the job-to-be-done that multiple posts point toward.

Example: "Too many manual steps syncing data between tools" might unify
posts about spreadsheet copy-paste, Zapier frustration, and home-grown
scripts.

### Step 4 — Score each opportunity

Rate every opportunity theme on the eight dimensions defined in the
**Opportunity Scorecard** (see `references/scorecard.md`). Produce a
total score out of 40 and assign a tier:

| Tier | Score | Meaning |
|---|---|---|
| **A — Strong opportunity** | 32–40 | High pain, proven demand, buildable |
| **B — Worth watching** | 20–31 | Promising but missing one key signal |
| **C — Noise** | 8–19 | Low evidence or too diffuse to act on |

### Step 5 — Compile evidence proof

For every opportunity that scores B or above, produce a quantitative
**Evidence Summary** (template in `references/evidence-template.md`).
This is non-negotiable — no opportunity claim without data.

### Step 6 — Output the final brief

Assemble the deliverables described in **Output Format** below.

---

## Output Format

Every analysis must produce three sections.

### Section 1 — Opportunity Ranking Table

| Rank | Opportunity | Audience | Core pain | Score | Tier |
|---|---|---|---|---|---|

Sort descending by score.

### Section 2 — Opportunity Detail Cards (one per B+ opportunity)

For each card, include:

1. **Opportunity name** — concise label
2. **Target user** — who hurts most
3. **Core problem** — the unmet job-to-be-done
4. **Signal evidence summary** — the quantitative proof table
   (post count, subreddit spread, agreement comments, workaround
   comments, pay-intent mentions, trend direction)
5. **Representative signal samples** — 3 paraphrased pain-point
   quotes, 2 workaround descriptions, 1 pay-intent remark
   (never copy-paste; always paraphrase)
6. **Current alternatives & why they fail**
7. **Recommended product entry point** — small tool / SaaS /
   plugin / API / AI assistant / vertical workflow
8. **Confidence & caveats** — what additional evidence would
   strengthen or weaken the case

### Section 3 — Action Recommendations

- Top 3 opportunities to pursue first
- Suggested MVP shape for each
- Subreddits and keywords to keep monitoring
- Evidence gaps that need filling before committing

---

## Rules

These rules apply to every run of this skill.

1. **No single-post conclusions.** An opportunity must appear across
   multiple posts or comments to be scored B or above. One viral rant
   is not a business opportunity.

2. **Comments matter as much as posts.** Workarounds, "+1"
   validations, and price-sensitivity remarks live in comments.
   Never skip them.

3. **Quantify or qualify.** Every claim in the output must be backed
   by either a number (post count, comment count, trend direction)
   or an explicit caveat ("limited data — only 4 posts found").

4. **Separate heat from signal.** A post with 2k upvotes about a
   meme is noise. A post with 30 upvotes where 12 commenters
   describe the same workaround is signal. Weight engagement
   quality over quantity.

5. **"Big market" ≠ good opportunity.** Prefer high-pain narrow
   segments over low-pain broad ones. "Everyone could use this"
   is a warning, not a selling point.

6. **Distinguish temporal patterns.** Label each opportunity as:
   `chronic` (steady complaints over 6+ months),
   `rising` (acceleration in last 90 days),
   `spike` (sudden burst, may fade), or
   `dormant` (old complaints, no recent activity).

7. **Stay product-focused.** The output is a product opportunity
   brief, not a social listening report. Every paragraph should
   help the reader decide whether to build something.

8. **Paraphrase, never copy.** When citing Reddit signals, always
   rephrase in your own words. Never paste user comments verbatim.

---

## Reference Files

Read these before your first analysis. They contain the detailed
frameworks referenced above.

| File | Contents | When to read |
|---|---|---|
| `references/signal-taxonomy.md` | The six signal types with detection patterns | Before Step 2 |
| `references/scorecard.md` | Eight scoring dimensions with rubrics | Before Step 4 |
| `references/evidence-template.md` | Evidence Summary table format and comment classification model | Before Step 5 |
