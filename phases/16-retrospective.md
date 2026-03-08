# Phase 16: RETROSPECTIVE

**Role**: Process improvement analyst
**Tools**: File write (memory updates)

## What You Do

Document what worked, what didn't, and update cross-run memory files so future runs benefit from this experience.

### 1. What Worked

- Which search queries produced the best signals?
- Which phases produced the strongest output on the first try?
- What format/pricing decisions felt right and why?
- What would you do the same way next time?

### 2. What Didn't Work

- Where did research hit dead ends?
- Which phases needed the most revision or rethinking?
- What search queries returned nothing useful?
- What assumptions turned out to be wrong?
- What would you do differently next time?

### 3. Update Cross-Run Memory

**If the pipeline completed successfully (all gates passed):**

Append to `memory/winning_niches.json`:
```json
{
  "niche": "[niche]",
  "date": "[date]",
  "score": [total],
  "format": "[chosen format]",
  "price": "[chosen price]",
  "key_insight": "[one sentence about why this niche worked]"
}
```

**If the pipeline was halted at a gate:**

Append to `memory/failed_niches.json`:
```json
{
  "niche": "[niche]",
  "date": "[date]",
  "failed_at": "gate_[N]",
  "reason": "[why it failed]",
  "salvageable": true/false,
  "pivot_suggestion": "[what might work instead]"
}
```

**Always update `memory/search_patterns.json`:**
```json
{
  "niche": "[niche]",
  "effective_queries": ["queries that found good signals"],
  "dead_end_queries": ["queries that returned nothing useful"],
  "best_sources": ["URLs/platforms that had the most useful content"]
}
```

**If this is the first run of this format type, or if there's new data, update `memory/format_performance.json`:**
```json
{
  "format": "playbook",
  "niches_used_for": ["therapist credentialing", "..."],
  "strengths": "Works well for process-oriented problems with clear steps",
  "weaknesses": "Less effective for open-ended, creative topics",
  "best_paired_with": "template library"
}
```

### 4. Note for Future Runs

If you discovered something during this run that would change how you approach the PIPELINE ITSELF (not just this niche), note it:

```json
{
  "process_improvement": "Description of what to change",
  "discovered_during": "phase_[N]",
  "impact": "Would improve [speed/quality/accuracy] of [which phases]"
}
```

## Output

Save `runs/{slug}/postmortem.json` with all of the above.

Update the memory files listed above.

## Pipeline Complete

Report to the user:
- **Final status**: COMPLETE
- **Files created**: List the run directory contents
- **Key metrics**: Total score, word count, artifact count, run duration
- **Top insight**: The single most interesting thing you learned about this niche
- **Recommendation**: What to do next (review draft, set up Gumroad, write more artifacts, etc.)
