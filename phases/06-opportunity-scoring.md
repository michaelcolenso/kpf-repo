# Phase 6: OPPORTUNITY SCORING

**Role**: Investment analyst making the go/no-go decision
**Tools**: None — reasoning only

## Before You Start

Check if `memory/winning_niches.json` and `memory/failed_niches.json` exist. If they do, read them to calibrate your scoring — look for patterns in what scored well vs. what failed.

## What You Do

Score the opportunity on 5 dimensions. Use all evidence from Phases 2-5.

### Scoring Rubric

**1. Spending Clarity** — How clear is the willingness to pay?
| Score | Criteria |
|-------|----------|
| 5 | Multiple $500+ purchases documented |
| 4 | Multiple $100-500 purchases documented |
| 3 | Some $50-200 purchases |
| 2 | Small purchases only (<$50) or just time costs |
| 1 | No spending evidence |

**2. Information Gap** — How strong is the knowledge need?
| Score | Criteria |
|-------|----------|
| 5 | Recurring unanswered questions, widespread confusion |
| 4 | Clear questions with only partial answers available |
| 3 | Some questions but decent free resources exist |
| 2 | Most information available, just poorly organized |
| 1 | Information readily available and well-organized |

**3. Urgency** — How pressing is the problem?
| Score | Criteria |
|-------|----------|
| 5 | Revenue-impacting, time-sensitive, or compliance-driven |
| 4 | Significant money or time at stake |
| 3 | Important but not urgent |
| 2 | Moderate inconvenience |
| 1 | Nice-to-have, no real consequences for delay |

**4. Create Feasibility** — Can we build this in 2-4 weeks?
| Score | Criteria |
|-------|----------|
| 5 | Clear scope, templatable, subject matter is well-defined |
| 4 | Mostly clear, some research needed during creation |
| 3 | Moderate complexity, may need expert input |
| 2 | Complex subject, hard to simplify |
| 1 | Too complex, too vague, or requires credentials to be credible |

**5. AI Multiplier** — Can AI enhance this product?
| Score | Criteria |
|-------|----------|
| 5 | Strong personalization opportunity (state-specific, role-specific, situation-specific) |
| 4 | Good automation potential (calculators, generators, custom checklists) |
| 3 | Some AI enhancement possible |
| 2 | Minimal AI leverage |
| 1 | No AI advantage |

### Calculate and Decide

Total your scores (max 25).

## GATE 3 — Score Threshold

**State your gate decision explicitly.**

```
GATE 3 — Score Threshold

Spending Clarity:    [X]/5 — [brief justification]
Information Gap:     [X]/5 — [brief justification]
Urgency:            [X]/5 — [brief justification]
Create Feasibility:  [X]/5 — [brief justification]
AI Multiplier:       [X]/5 — [brief justification]

Total: [XX]/25
Decision: [CREATE / PIVOT / REJECT]
Reasoning: [overall assessment]
```

| Total | Decision | Action |
|-------|----------|--------|
| ≥ 18 | **CREATE** | Proceed to build |
| 14-17 | **PIVOT** | Pause. Explain concerns. Ask user: proceed anyway or try a different niche? |
| < 14 | **REJECT** | Stop pipeline. Report findings. Suggest better niches. |

**Override rule**: You MAY override the threshold if you have a strong reason, but overrides should be rare. Use them when a score is distorted by data availability, not by actual market conditions.

Valid override reasons:
- A dimension scored low because **data was hard to find**, not because the signal is weak (e.g., a niche with few online communities but clear offline spending)
- One dimension is structurally low for all products in this category (e.g., Create Feasibility is always 3 for regulated topics) but the other dimensions are exceptional

Invalid override reasons:
- "I just think this niche is good" — gut feel without evidence
- Wanting to proceed despite two or more weak dimensions
- The niche is personally interesting

Limit yourself to one override per run. If you feel you need more than one, that's a signal to PIVOT or REJECT. You MUST document the override in the `opportunity_score.json` output under the `override` key.

**If REJECT**: Stop the pipeline. Report:
> "[Niche] scored [X]/25. Key weakness: [lowest dimension]. This niche [doesn't have enough spending evidence / isn't urgent enough / is too complex to build quickly / etc.]. Consider instead: [2-3 alternative niches based on what you learned]."

**If PIVOT**: Ask the user:
> "[Niche] scored [X]/25. Concern: [explain the weak dimension(s)]. I can proceed but the product may face [specific risk]. Want to continue, or explore [suggested alternative]?"

**If CREATE**: Continue.

## VALIDATE Mode: Stop Here

If the current mode is VALIDATE, stop after saving the score. Summarize to the user:
- The score breakdown
- Your recommendation
- If CREATE: what the product might look like (format, price range, core promise)
- If REJECT/PIVOT: why, and what alternatives to consider

## All Other Modes: Continue

Read `phases/07-strategy.md` and begin Phase 7.

## Output

Save `runs/{slug}/opportunity_score.json`:

```json
{
  "scores": {
    "spending_clarity": { "score": 5, "reasoning": "Multiple $500+ service purchases documented" },
    "information_gap": { "score": 5, "reasoning": "Widespread confusion, recurring questions" },
    "urgency": { "score": 4, "reasoning": "Revenue impact — can't bill insurance without panels" },
    "create_feasibility": { "score": 5, "reasoning": "Clear scope, templatable process" },
    "ai_multiplier": { "score": 4, "reasoning": "State-specific personalization possible" }
  },
  "total": 23,
  "decision": "CREATE",
  "reasoning": "Strong opportunity across all dimensions. Clear willingness to pay, specific pain, and a gap in the market for a template-heavy DIY playbook in the $79-149 range.",
  "override": null
}
```
