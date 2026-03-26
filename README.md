# Reddit Opportunity Miner

A Claude skill that turns Reddit discussions into evidence-backed product opportunity assessments.

## What It Does

This skill doesn't summarize Reddit posts. It mines them for **commercial signals** — recurring pain points, DIY workarounds, willingness-to-pay remarks, audience patterns, and trend momentum — then scores and ranks each finding as an actionable product opportunity.

**Input:** A market domain + an analysis goal.  
**Output:** A prioritized opportunity brief with quantitative evidence, ready for product decisions.

## Who It's For

- Founders & indie hackers looking for startup ideas
- Product managers researching unmet needs
- Growth teams hunting for niche SaaS opportunities
- Anyone who wants to go from "Reddit complaints" to "build-or-skip decision"

## How It Works

The skill follows a six-step workflow:

1. **Define scope** — confirm domain, subreddits, keywords, time window
2. **Collect raw signals** — extract pain, workaround, pay-intent, frequency, audience, and trend signals from posts and comments
3. **Cluster into opportunities** — group signals into coherent unmet-need themes
4. **Score each opportunity** — rate on 8 dimensions (pain intensity, recurrence, audience clarity, workaround density, willingness to pay, entry feasibility, differentiation space, trend momentum) for a total score out of 40
5. **Compile evidence proof** — build a quantitative evidence summary for every promising opportunity
6. **Output the brief** — ranking table + detail cards + action recommendations

## Four Analysis Modes

| Mode | Best For |
|---|---|
| **Pain-Point Discovery** | Open-ended exploration, finding what hurts |
| **Idea Validation** | Testing a specific product hypothesis |
| **Competitor-Gap Analysis** | Finding where existing tools fall short |
| **Trend Scan** | Catching rising needs before competition forms |

## File Structure

```
reddit-opportunity-miner/
├── SKILL.md                              # Main skill instructions
└── references/
    ├── signal-taxonomy.md                # Six signal types with detection patterns
    ├── scorecard.md                      # Eight scoring dimensions with rubrics
    └── evidence-template.md              # Evidence table format & comment classification
```

## Installation

Copy this folder into your Claude skill directory, or import it as a `.skill` file if your environment supports packaging.

## Example Usage

> "I'm looking for SaaS opportunities in the HR / recruiting space. Can you mine Reddit for pain points that recruiters keep complaining about?"

> "I have an idea for an AI-powered lesson plan generator for teachers. Can you validate whether there's real demand on Reddit?"

> "What are people on Reddit saying about Notion alternatives? I want to find gaps I could build for."

## License

MIT
