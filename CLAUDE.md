# Agentic KPF — Knowledge Product Factory

You are the agent executing this workflow. You are not calling APIs or orchestrating other agents — you are doing the research, making the decisions, writing the content, and enforcing the gates yourself, using your own tools (search, browse, reason, write).

## How This Repo Works

This file tells you everything you need to know about the pipeline, modes, gates, and state management. It does NOT contain phase-by-phase instructions — those live in `phases/` and you read them just-in-time as each phase begins.

**Rule: Read the phase instruction file at the START of each phase. Do not read ahead.**

```
phases/
├── 01-intake.md
├── 02-discovery.md
├── 03-spending-analysis.md
├── 04-pain-mapping.md
├── 05-competitive-analysis.md
├── 06-opportunity-scoring.md
├── 07-strategy.md
├── 08-outline.md
├── 09-synthesis.md
├── 10-drafting.md
├── 11-artifacts.md
├── 12-personalization.md
├── 13-packaging.md
├── 14-launch-assets.md
├── 15-validation.md
├── 16-retrospective.md
```

## Starting a Run

The user says something like:

- `"Run KPF validate mode on 'therapist insurance credentialing'"`
- `"KPF full mode: hot sauce labeling compliance"`
- `"Discover mode — beekeeping for beginners"`

When you receive a run command:

1. Read `phases/01-intake.md`
2. Execute Phase 1 (validate niche, set constraints, create run directory)
3. Check if the current mode includes the next phase
4. If yes: read the next phase file, execute it
5. If no: stop, summarize findings, save state
6. At any gate: enforce the gate rules below — if FAIL, stop the pipeline

## Execution Modes

Modes control how far the pipeline runs. The user picks a mode at kickoff.

| Mode | Stops After | Use When |
|------|------------|----------|
| **DISCOVER** | Phase 2 (Discovery) | Exploring niches without commitment |
| **VALIDATE** | Phase 6 (Opportunity Scoring) | Testing if a niche is viable before building |
| **BUILD** | Phase 13 (Packaging) | Creating the product without launch assets |
| **LAUNCH** | Phase 15 (Validation) | Product exists, need launch materials |
| **FULL** | Phase 16 (Retrospective) | Complete end-to-end run |

If the user doesn't specify a mode, ask them. Do not assume FULL.

## Phase Sequence

```
Phase 1:  INTAKE ..................... all modes
Phase 2:  DISCOVERY .................. all modes
          ── DISCOVER mode stops here ──
Phase 3:  SPENDING ANALYSIS .......... VALIDATE, BUILD, LAUNCH, FULL
          ── GATE 1: Spending Evidence ──
Phase 4:  PAIN MAPPING ............... VALIDATE, BUILD, LAUNCH, FULL
          ── GATE 2: Pain Specificity ──
Phase 5:  COMPETITIVE ANALYSIS ....... VALIDATE, BUILD, LAUNCH, FULL
Phase 6:  OPPORTUNITY SCORING ........ VALIDATE, BUILD, LAUNCH, FULL
          ── GATE 3: Score Threshold ──
          ── VALIDATE mode stops here ──
Phase 7:  STRATEGY ................... BUILD, LAUNCH, FULL
Phase 8:  OUTLINE .................... BUILD, FULL
Phase 9:  SYNTHESIS .................. BUILD, FULL
Phase 10: DRAFTING ................... BUILD, FULL
Phase 11: ARTIFACTS .................. BUILD, FULL
Phase 12: PERSONALIZATION (optional) . BUILD, FULL
Phase 13: PACKAGING .................. BUILD, LAUNCH, FULL
          ── GATE 4: Artifact Completeness ──
          ── BUILD mode stops here ──
Phase 14: LAUNCH ASSETS .............. LAUNCH, FULL
Phase 15: VALIDATION ................. LAUNCH, FULL
          ── GATE 5: Launch Readiness ──
          ── LAUNCH mode stops here ──
Phase 16: RETROSPECTIVE .............. FULL
          ── FULL mode stops here ──
```

## Gate Rules

There are 5 gates. At each gate you MUST:

1. State the gate name
2. List the evidence
3. Declare PASS, PIVOT, or FAIL
4. Explain your reasoning

Format your gate decisions exactly like this:

```
GATE [N] — [Name]
Evidence: [what you found]
Decision: [PASS / PIVOT / FAIL]
Reasoning: [why]
Action: [what happens next]
```

### Gate Definitions

**GATE 1 — Spending Evidence** (after Phase 3)
- PASS: Found 3+ concrete spending signals with $ amounts or time costs
- FAIL: Only vague interest, no quantified spending
- On FAIL: Stop pipeline. Report "Insufficient spending evidence for [niche]."

**GATE 2 — Pain Specificity** (after Phase 4)
- PASS: Found specific recurring question + documented workaround + quantified cost
- FAIL: Pain is vague or consequences unclear
- On FAIL: Stop pipeline. Report "Pain not specific enough for [niche]."

**GATE 3 — Score Threshold** (after Phase 6)
- CREATE: Score ≥ 18 → proceed to build
- PIVOT: Score 14-17 → pause, explain concerns, ask user whether to proceed or try a different niche
- REJECT: Score < 14 → stop pipeline
- You MAY override thresholds with judgment, but you MUST document why

**GATE 4 — Artifact Completeness** (after Phase 13)
- PASS: Main draft exists + 3 or more support artifacts + package manifest
- FAIL: Missing key components
- On FAIL: Return to Phase 11 and create missing artifacts

**GATE 5 — Launch Readiness** (after Phase 15)
- PASS: All prior gates passed + launch assets complete
- REVISE: Some issues but fixable — fix them and re-check
- FAIL: Fundamental problems — report to user

## State Management

### In Your Context (track mentally)
- Current phase number
- Current mode
- Key findings so far
- Gate decisions made
- Running opportunity score

### On Disk (save after each phase)

Per-run artifacts go in: `runs/{date}_{niche-slug}/`

Create this directory in Phase 1. Save each phase's output file here as you complete it. The phase instruction files specify which output file to create.

### Cross-Run Memory (update after each completed run)

These files live in `memory/` and accumulate across runs:

| File | Purpose |
|------|---------|
| `memory/winning_niches.json` | Niches that passed all gates |
| `memory/failed_niches.json` | Niches that failed at a gate (with which gate and why) |
| `memory/search_patterns.json` | Search queries that produced good results |
| `memory/format_performance.json` | Which product formats worked for which niche types |

Before starting Phase 2 (Discovery), read `memory/search_patterns.json` if it exists — use proven queries first.

Before starting Phase 6 (Scoring), read `memory/winning_niches.json` and `memory/failed_niches.json` if they exist — use pattern matching to calibrate your scoring.

## Philosophy

**OLD**: CLI tool orchestrates API calls to LLMs
**NEW**: You execute the workflow using your tools (search, browse, reason, write)

Why this works:
1. **Real research** — you search for actual spending signals, not synthetic data
2. **Live competitive analysis** — you browse current competitor offerings
3. **Human judgment** — you apply reasoning at gates, not rigid thresholds
4. **Adaptive** — you change course based on what you find
5. **Transparent** — every decision is visible and explainable in the conversation

## Quick Reference: Tool Usage by Phase

| Phase | Tools |
|-------|-------|
| 1 Intake | None (reasoning) |
| 2 Discovery | Web search |
| 3 Spending Analysis | None (analyze Phase 2 data) |
| 4 Pain Mapping | Web search (targeted) |
| 5 Competitive Analysis | Web search + page visits |
| 6 Opportunity Scoring | None (reasoning) |
| 7 Strategy | None (reasoning) |
| 8 Outline | None (planning) |
| 9 Synthesis | None (synthesis) |
| 10 Drafting | None (writing) |
| 11 Artifacts | None (creation) |
| 12 Personalization | None (specification) |
| 13 Packaging | None (organization) |
| 14 Launch Assets | None (copywriting) |
| 15 Validation | None (review) |
| 16 Retrospective | File write (memory updates) |
