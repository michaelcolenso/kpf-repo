# Phase 15: VALIDATION

**Role**: Quality assurance reviewer
**Tools**: None — review and verification

## What You Do

Final quality check across the entire pipeline. Re-verify every gate and check that all components are complete and consistent.

### Validation Checklist

Go through each check. Mark PASS or FAIL with a brief note.

**Gate 1 — Spending Evidence (Phase 3)**
- [ ] 3+ spending signals documented
- [ ] 2+ signals have quantified $ amounts or time costs
- [ ] Signals come from real, cited sources

**Gate 2 — Pain Specificity (Phase 4)**
- [ ] Specific recurring question identified
- [ ] Current workaround documented
- [ ] Cost of workaround quantified (money and/or time)

**Gate 3 — Score Threshold (Phase 6)**
- [ ] Opportunity score ≥ 18 (or override documented)
- [ ] Decision was CREATE

**Gate 4 — Artifact Completeness (Phase 13)**
- [ ] Main draft exists and is complete (no placeholders, no missing sections)
- [ ] 3+ support artifacts exist
- [ ] Package manifest exists
- [ ] Quick start guide exists

**Gate 5 — Launch Readiness (this gate)**
- [ ] Target audience clearly defined
- [ ] Distribution channels identified (with specific communities/platforms)
- [ ] Pricing set with competitive anchoring
- [ ] Sales page written
- [ ] Gumroad listing written
- [ ] Lead magnet created
- [ ] 3+ launch posts written
- [ ] FAQ addresses top concerns

### Consistency Checks

- [ ] Product name is consistent across all files
- [ ] Pricing is consistent across sales page, Gumroad listing, and package manifest
- [ ] Target audience description is consistent
- [ ] Core promise/transformation statement is consistent
- [ ] No artifacts are referenced in the draft that don't exist

### Quality Spot-Checks

- [ ] Draft opens with the buyer's most urgent pain (not generic intro)
- [ ] At least 3 sections have concrete action items
- [ ] Language bank quotes from research appear in the sales page
- [ ] Lead magnet delivers a genuine quick win (not a teaser)

## GATE 5 — Launch Readiness

**State your gate decision explicitly.**

```
GATE 5 — Launch Readiness

Prior Gates:
  Gate 1 (Spending): [PASS — verified]
  Gate 2 (Pain): [PASS — verified]
  Gate 3 (Score): [PASS — verified]
  Gate 4 (Artifacts): [PASS — verified]

Launch Components:
  Sales page: [COMPLETE / MISSING]
  Gumroad listing: [COMPLETE / MISSING]
  Lead magnet: [COMPLETE / MISSING]
  Launch posts: [N] written
  FAQ: [COMPLETE / MISSING]

Consistency: [PASS / ISSUES FOUND]
Quality: [PASS / ISSUES FOUND]

Decision: [PASS / REVISE / FAIL]
```

**PASS**: All checks pass → proceed to retrospective
**REVISE**: Some issues found but fixable → list them, fix them, re-check
**FAIL**: Fundamental problems → report to user with specific issues

**If REVISE**: Fix the issues yourself if they're within your capability (e.g., inconsistent pricing → update the file). Then re-run the affected checks.

**If FAIL**: Stop and report to the user exactly what's wrong and which phases need rework.

## LAUNCH Mode: Stop Here

If the current mode is LAUNCH, stop after validation passes. Summarize to the user:
- Overall status: READY TO LAUNCH
- Files created and where to find them
- Recommended launch sequence (lead magnet first, then posts, then sales page reveal)
- Any caveats or recommendations

## FULL Mode: Continue

Read `phases/16-retrospective.md` and begin Phase 16.

## Output

Save `runs/{slug}/validation_report.json`:

```json
{
  "gate_1_recheck": "PASS",
  "gate_2_recheck": "PASS",
  "gate_3_recheck": "PASS",
  "gate_4_recheck": "PASS",
  "gate_5": {
    "decision": "PASS",
    "launch_components_complete": true,
    "consistency_check": "PASS",
    "quality_check": "PASS"
  },
  "issues_found": [],
  "issues_fixed": [],
  "overall_status": "READY_TO_LAUNCH"
}
```
