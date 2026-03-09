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
  "source_type": "official_documentation",
  "confidence": "HIGH",
  "notes": "Confirmed across 3 independent sources",
  "usable_in_product": true
}
```

Field definitions:
- `fact`: A single, specific, falsifiable claim (not a general observation)
- `source_url`: The URL where this was found. Use `"direct_observation"` if it came from a forum post you read
- `source_type`: One of `official_documentation`, `professional_association`, `academic`, `practitioner_forum`, `competitor_content`, `news_article`
- `confidence`: See levels below
- `notes`: Why you trust (or don't trust) this fact; number of confirming sources
- `usable_in_product`: `true` if you can cite or rely on this in the draft; `false` if too uncertain to include without heavy hedging

Confidence levels:
- **HIGH**: Multiple independent sources agree — use freely in the product
- **MEDIUM**: Single authoritative source (government site, professional association) — use with light attribution ("According to [organization]...")
- **LOW**: Single informal source (forum post, one person's experience) — use as anecdote only, flag explicitly ("Some practitioners report..."), never as fact

**Minimum to synthesize**: Extract at least 10 facts before proceeding. If you have fewer than 10, your Phase 2 and 4 research was thin — consider going back and doing more targeted searches before drafting.

### 2. Note Contradictions

Where does your research disagree with itself? Document both sides:

```json
{
  "topic": "Average credentialing timeline",
  "position_a": "90-120 days (CAQH official documentation)",
  "position_b": "3-6 months (reported by practitioners in forums)",
  "resolution": "Official timeline is 90-120 days but real-world experience is longer due to paperwork delays and resubmissions",
  "how_to_handle_in_draft": "Present both — give the official figure, then acknowledge real-world variance and explain why it occurs"
}
```

The `how_to_handle_in_draft` field is required. Don't leave contradictions unresolved for the writer — make the call now.

### 3. Document Key Decisions

What strategic choices were made in Phases 6-8 and why?

```json
{
  "decision": "Chose playbook format over course format",
  "rationale": "Buyers want to DO the process, not learn about it — a course adds friction",
  "excluded": "State-specific deep dives (too complex for v1, will be v1.1 add-ons)",
  "assumptions": ["Buyer has already decided to credential, not still evaluating whether to", "Buyer is in the US"]
}
```

List every significant choice. Include what you decided NOT to include and why — this prevents scope creep during drafting.

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
