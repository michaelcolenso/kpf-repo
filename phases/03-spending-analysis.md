# Phase 3: SPENDING ANALYSIS

**Role**: Evidence analyst quantifying willingness to pay
**Tools**: None — analyze data collected in Phase 2

## What You Do

Review `discovery_report.json` and extract every concrete spending example.

### For Each Signal

Document:
- **Dollar amount**: Exact figure or range
- **Time cost**: Hours spent (convert to approximate dollar value using $50-100/hr for professional time, $25-50/hr for hobbyist time)
- **Purchase type**: Course, service, tool, consultant, template, book, membership
- **Satisfaction**: Happy (would buy again), Neutral, Frustrated (felt overcharged or underserved)

### Identify Jobs-to-Be-Done

From the spending signals, what outcomes are people actually paying for?
- Not "credentialing help" but "get on insurance panels without spending 40 hours figuring it out"
- Not "hot sauce course" but "get my product on shelves without getting shut down by the FDA"

### Summarize

- Total signals found
- How many are quantified (have a $ amount or time cost)
- Spend range (low to high)
- Dominant purchase type
- Dominant satisfaction level

## GATE 1 — Spending Evidence

**You must now make a gate decision. State it explicitly.**

```
GATE 1 — Spending Evidence
Signals found: [N]
Quantified: [N] (with $ amounts or time costs)
Spend range: $[low] - $[high]
Decision: [PASS / FAIL]
Reasoning: [your assessment]
```

**PASS criteria**: 3+ concrete spending signals with dollar amounts or time costs
**FAIL criteria**: Only vague interest, no quantified spending

**If FAIL**: Stop the pipeline. Save what you have. Report to the user:
> "Insufficient spending evidence for [niche]. Found [N] signals but only [N] were quantified. This niche may not have strong enough willingness to pay for a knowledge product. Consider: [suggest adjacent niches that might be stronger]."

**If PASS**: Continue.

## Output

Save `runs/{slug}/spending_signals.json`:

```json
{
  "signals": [
    {
      "amount": "$500",
      "time_equivalent": null,
      "purchase_type": "service",
      "satisfaction": "happy",
      "job_to_be_done": "Get paneled without spending months figuring it out",
      "source_url": "https://..."
    }
  ],
  "summary": {
    "total_signals": 5,
    "quantified": 4,
    "spend_range": "$97 - $2000",
    "dominant_type": "service",
    "dominant_satisfaction": "mixed — happy with results but frustrated by cost"
  },
  "gate_1": {
    "decision": "PASS",
    "reasoning": "4 quantified signals in the $97-$2000 range with clear job-to-be-done"
  }
}
```

## Next

Read `phases/04-pain-mapping.md` and begin Phase 4.
