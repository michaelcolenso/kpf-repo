# Phase 4: PAIN MAPPING

**Role**: Pain researcher mapping specific problems
**Tools**: Web search (targeted follow-up queries)

## What You Do

Go deeper than Discovery. You're looking for the specific, recurring shape of the pain — not just "people are frustrated" but the exact question they keep asking, what they do right now to cope, and what it costs them.

### 1. Find the Recurring Question

Search for the specific question that gets asked over and over:
- `"[niche]" "how do I"`
- `"[niche]" step by step`
- `"[niche]" for beginners`
- `"[niche]" checklist`
- `"[niche]" "what do I need to"`

You're looking for ONE core question that appears across multiple sources. This becomes the nucleus of your product.

**If multiple competing questions emerge**: Pick the one that is most frequently asked AND has the highest consequence if left unanswered. Use this test: "If a buyer solved only this one question, would the purchase feel worth it?" If two questions both pass that test, they may both belong in the product — but one must be the lead. Document all candidates in `recurring_questions` and note which you chose as `core_question` and why.

### 2. Document Current Workarounds

What do people do RIGHT NOW to solve this problem?
- Hire a professional ($X)
- DIY with scattered free resources (Y hours)
- Buy an expensive course ($X)
- Use a generic tool not designed for this
- Ask in forums and piece together advice
- Ignore it and suffer consequences

For each workaround, note what it costs (money and/or time) and why it's inadequate.

### 3. Quantify Consequences

What happens when the problem isn't solved or is solved badly?
- **Time wasted**: Hours per week/month spent on workarounds
- **Money at risk**: Revenue lost, fines, overpayment, missed opportunities
- **Emotional toll**: Frustration, overwhelm, imposter syndrome, decision paralysis

### 4. Capture Exact Language

Pull direct quotes that express the pain in the user's own words. These become:
- Sales page headlines
- Email subject lines
- Social media hooks
- Product section titles

## GATE 2 — Pain Specificity

**State your gate decision explicitly.**

```
GATE 2 — Pain Specificity
Core question: "[the recurring question you found]"
Workaround: [what people do now]
Quantified cost: [time and/or money]
Decision: [PASS / FAIL]
Reasoning: [your assessment]
```

**PASS criteria**: Specific recurring question + documented workaround + quantified cost
**FAIL criteria**: Pain is vague or consequences are unclear

**If FAIL**: Stop the pipeline. Report:
> "Pain not specific enough for [niche]. Found general frustration but could not identify a specific recurring question with quantifiable consequences. This makes it hard to build a focused product. Consider: [suggest ways to narrow the niche]."

**If PASS**: Continue.

## Output

Save `runs/{slug}/pain_map.json`:

```json
{
  "core_question": "How do I get on insurance panels without spending months figuring it out?",
  "recurring_questions": [
    "Which panels should I apply to first?",
    "How long does credentialing actually take?",
    "What paperwork do I need before I start?"
  ],
  "workarounds": [
    {
      "method": "Hire a credentialing service",
      "cost": "$500-2000",
      "time": "Still takes 3-6 months",
      "inadequacy": "Expensive and you don't learn the process for future panels"
    },
    {
      "method": "DIY with scattered blog posts",
      "cost": "Free",
      "time": "20-40 hours of research",
      "inadequacy": "Information is outdated, incomplete, and state-specific"
    }
  ],
  "consequences": {
    "time_wasted": "20-40 hours over 3-6 months",
    "money_at_risk": "$500-2000 for services, or months of lost insurance revenue",
    "emotional_toll": "Overwhelm, imposter syndrome, fear of doing it wrong"
  },
  "language_bank": [
    "I have no idea where to even start",
    "It feels like everyone else figured this out except me",
    "I just want someone to tell me exactly what to do step by step"
  ],
  "gate_2": {
    "decision": "PASS",
    "reasoning": "Clear recurring question with documented $500-2000 workaround cost"
  }
}
```

## Next

Read `phases/05-competitive-analysis.md` and begin Phase 5.
