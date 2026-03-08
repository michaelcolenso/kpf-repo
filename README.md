# Agentic KPF — Knowledge Product Factory

An agentic framework for creating market-ready knowledge products (ebooks, playbooks, template packs, guides) from a single niche input. The agent IS Claude — executing a structured 16-phase workflow using its own tools.

## Philosophy

**OLD**: Code orchestrates API calls to LLMs  
**NEW**: AI agent executes the workflow directly using search, browse, reason, and write

No API costs. No infrastructure. No code to maintain. Just a structured workflow that Claude follows phase by phase, with progressive instruction loading to keep the context window lean.

## How It Works

1. Clone this repo (or point Claude Code at it)
2. Tell Claude: `"Run KPF validate mode on 'therapist insurance credentialing'"`
3. Claude reads `CLAUDE.md`, then loads each phase instruction file just-in-time as it executes
4. Artifacts accumulate in `runs/`. Cross-run learnings accumulate in `memory/`.

## Repo Structure

```
CLAUDE.md                  ← Agent reads this first (pipeline, modes, gates)
phases/
├── 01-intake.md           ← Read at Phase 1 start
├── 02-discovery.md        ← Read at Phase 2 start
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
└── 16-retrospective.md    ← Read at Phase 16 start
memory/
├── winning_niches.json    ← Accumulates across runs
├── failed_niches.json
├── search_patterns.json
└── format_performance.json
runs/                      ← Created per-run (gitignored)
└── {date}_{niche-slug}/
    ├── run_config.json
    ├── discovery_report.json
    ├── ...all phase outputs...
    └── postmortem.json
```

## Execution Modes

| Mode | Stops After | Use When |
|------|------------|----------|
| `DISCOVER` | Phase 2 | Exploring niches without commitment |
| `VALIDATE` | Phase 6 | Testing viability before building |
| `BUILD` | Phase 13 | Creating the product without launch assets |
| `LAUNCH` | Phase 15 | Product exists, need marketing materials |
| `FULL` | Phase 16 | Complete end-to-end run |

## Gates

5 kill switches enforce quality. The agent states evidence, verdict, and reasoning at each gate. If a gate fails, the pipeline stops — it never ships garbage.

| Gate | After Phase | Checks |
|------|------------|--------|
| 1 | Spending Analysis | 3+ quantified spending signals |
| 2 | Pain Mapping | Specific question + workaround + cost |
| 3 | Opportunity Scoring | Score ≥ 18/25 |
| 4 | Packaging | Main draft + 3 artifacts + manifest |
| 5 | Validation | All prior gates + launch readiness |

## Usage

### With Claude Code
```bash
cd knowledge-product-factory
claude "Run KPF validate mode on 'hot sauce FDA labeling'"
```

### With Claude.ai
Upload the repo as a project, or paste `CLAUDE.md` as context and tell Claude where to find the phase files.

### Example Commands
```
"Run KPF discover mode on 'beekeeping compliance'"
"KPF validate: therapist insurance credentialing"
"KPF full mode — ADU permitting in Washington State"
"Continue the last KPF run from Phase 7"
```

## Why This Architecture

- **Progressive loading**: Phase instructions load just-in-time, not all 16 at once. Keeps the context window focused.
- **Durable state**: Every phase saves its output to disk. The agent can resume from any point.
- **Cross-run learning**: Memory files accumulate search patterns and niche outcomes across runs, so each run benefits from prior experience.
- **Fail fast**: 5 gates catch bad niches early. Most rejects happen by Phase 6, saving hours of wasted creation work.
- **Real evidence**: The agent searches for actual spending signals and competitive data, not synthetic output.
