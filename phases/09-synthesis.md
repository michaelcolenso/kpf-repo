# Phase 9: SYNTHESIS

**Role**: Research synthesizer organizing all findings into a structured knowledge base
**Tools**: None — synthesis and organization

## What You Do

Before writing begins, organize EVERYTHING you've learned into a single reference document. This prevents the writer (you, in Phase 10) from losing track of research across phases and ensures facts are properly sourced.

### 1. Extract Verified Facts

Go through all prior phase outputs and pull out every factual claim. For each:

```json
{
  "fact": "CAQH credentialing typically takes 90-120 days",
  "source_url": "https://...",
  "confidence": "HIGH",
  "notes": "Confirmed across 3 independent sources"
}
```

Confidence levels:
- **HIGH**: Multiple independent sources agree
- **MEDIUM**: Single source, but authoritative (government site, professional association)
- **LOW**: Single informal source (forum post, one person's experience) — use carefully, flag as anecdotal

### 2. Note Contradictions

Where does your research disagree with itself? Document both sides:

```json
{
  "topic": "Average credentialing timeline",
  "position_a": "90-120 days (CAQH official documentation)",
  "position_b": "3-6 months (reported by practitioners in forums)",
  "resolution": "Official timeline is 90-120 days but real-world experience is longer due to paperwork delays and resubmissions"
}
```

### 3. Document Key Decisions

What strategic choices were made in Phases 6-8 and why?
- Format choice and rationale
- Pricing rationale
- What was explicitly EXCLUDED from scope and why
- Any assumptions that should be validated

### 4. List Pitfalls

What common mistakes does the research reveal?
- What do buyers complain about in competitor reviews?
- What do forum users warn against?
- What errors do beginners typically make?

These become "avoid this" callouts in the product.

## Output

Save `runs/{slug}/knowledge_base.json`:

```json
{
  "verified_facts": [...],
  "contradictions": [...],
  "key_decisions": [...],
  "pitfalls": [...],
  "language_bank_consolidated": ["all exact-language quotes from Phases 2 and 4, deduplicated"]
}
```

## Next

Read `phases/10-drafting.md` and begin Phase 10.
