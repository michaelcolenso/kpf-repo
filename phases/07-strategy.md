# Phase 7: STRATEGY

**Role**: Product strategist defining the offer
**Tools**: None — strategic reasoning

## What You Do

Using everything from Phases 2-6, define the complete product offer. This is the brief that guides all creation phases.

### 1. Define Target User

Narrow to a SPECIFIC segment. Not a demographic — a situation.

Bad: "therapists"
Good: "solo private-practice therapists in their first 2 years who need to get on insurance panels but can't afford a $500+ credentialing service"

The target user should be the person whose pain you documented in Phase 4 and whose spending you verified in Phase 3.

### 2. Choose Product Format

Match the format to the shape of the pain:

| Pain Shape | Best Format |
|-----------|-------------|
| "I need to follow a process" | **Playbook** (step-by-step with checklists) |
| "I need tools to do the work" | **Template Library** (fill-in-the-blank docs) |
| "I need to not miss anything" | **Checklist System** (comprehensive process lists) |
| "I need to understand this topic" | **Mini Course** (structured lessons) |
| "I need to find the right resources" | **Resource Guide** (curated, organized links) |

Most strong products combine 2 formats — e.g., a playbook with embedded templates and checklists.

### 3. Set Pricing

Use three inputs:
- **Competitor price anchors** from `competitor_map.json`
- **Spending signals** from `spending_signals.json` — what are people already paying?
- **Value calculation** — if the product saves $500 or 20 hours, pricing at $79-149 is a no-brainer

Rule of thumb: price at 10-20% of the cost of the problem.

### 4. Craft Core Promise

One sentence: "Go from [painful current state] to [desired outcome] in [timeframe]."

Examples:
- "Go from confused about insurance paneling to fully credentialed in 90 days"
- "Go from guessing at FDA labeling to confidently compliant in 2 weeks"

### 5. Define Differentiator

Why buy this instead of the alternatives you found in Phase 5?
- More specific than generic courses?
- Cheaper than hiring a service?
- More actionable than free blog posts?
- More current than outdated books?

### 6. Choose Distribution Channels

Where are target users already spending time? (from Phase 2 communities)
- Reddit (which subreddits?)
- Facebook groups (which ones?)
- Professional associations
- LinkedIn
- Niche forums

## Output

Save `runs/{slug}/product_brief.json`:

```json
{
  "target_user": "Solo private-practice therapists in their first 2 years needing to get on insurance panels",
  "format": "playbook + template library",
  "price": "$97",
  "core_promise": "Go from confused about insurance paneling to fully credentialed — step by step, with every template you need",
  "differentiator": "State-aware, template-heavy, DIY alternative to $500+ credentialing services",
  "distribution_channels": [
    "r/psychotherapy (150k members)",
    "r/therapists (80k members)",
    "Private Practice Facebook groups"
  ],
  "positioning": "Priced between free scattered blogs ($0) and full credentialing services ($500+)"
}
```

## Next

Read `phases/08-outline.md` and begin Phase 8.
