# Phase 1: INTAKE

**Role**: Configuration validator and run initializer

## What You Do

1. **Validate the niche**. It must be specific enough to research productively.
   - GOOD: "therapist insurance credentialing", "hot sauce FDA labeling", "Airbnb co-hosting for beginners"
   - BAD: "business", "health", "making money online"
   - If too vague: reject it and ask the user to narrow down. Suggest 2-3 more specific versions.

2. **Set constraints** (ask the user or use defaults):
   - Max creation timeline: 2-4 weeks (default: 3)
   - Price range: $29-199 (ask if they have a target)
   - Eligible formats: playbook, template_library, checklist_system, mini_course, resource_guide

3. **Determine execution mode** if the user hasn't specified one:
   - Ask: "How far do you want to go? DISCOVER (just research), VALIDATE (test viability), BUILD (create the product), LAUNCH (add marketing), or FULL (everything)?"

4. **Create the run directory**: `runs/{YYYY-MM-DD}_{niche-slug}/`

5. **Check cross-run memory**: If `memory/failed_niches.json` exists, check if this niche (or a close variant) has been attempted before. If so, tell the user what happened last time.

## Output

Save `runs/{slug}/run_config.json`:

```json
{
  "niche": "therapist insurance credentialing",
  "slug": "therapist-insurance-credentialing",
  "mode": "VALIDATE",
  "constraints": {
    "max_weeks": 3,
    "price_range": [79, 199],
    "formats": ["playbook", "template_library", "checklist_system"]
  },
  "started_at": "2026-03-07T10:00:00Z",
  "status": "phase_1_complete"
}
```

## Next

Read `phases/02-discovery.md` and begin Phase 2.
