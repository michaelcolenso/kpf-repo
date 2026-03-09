# Phase 12: PERSONALIZATION (Optional)

**Role**: Personalization engineer
**Tools**: None — specification

## Skip Decision

Use this decision tree before proceeding:

```
Does the product's VALUE change significantly based on the buyer's
location, role, stage, or budget?
│
├── NO → Skip. Save SKIPPED status and proceed to Phase 13.
│
└── YES → Does addressing that variation require generating
          substantially different content per user?
          │
          ├── NO → Handle it in the main product with a brief
          │        "how to adapt this" section. Skip personalization.
          │
          └── YES → Is the variation finite and mappable?
                    (e.g., 50 states, 5 license types — not infinite)
                    │
                    ├── NO → Skip. Note in the product what the buyer
                    │        needs to verify for their situation.
                    │
                    └── YES → Build personalization. Proceed below.
```

**Common skip signals**:
- The product is a process that works the same regardless of who follows it
- The variation is "beginner vs. advanced" but the product is scoped to one level
- You'd need live data (current rates, current regulations) that goes stale quickly
- The variation is cosmetic, not substantive (e.g., industry jargon differs but steps don't)

If skipping, save a brief note in `runs/{slug}/personalization_spec.json`:
```json
{ "status": "SKIPPED", "reason": "Product is format-agnostic — works without personalization" }
```

Then proceed to Phase 13.

## When Personalization Adds Value

Personalization is worth building when the product's value changes significantly based on:
- **Location** (state-specific regulations, local resources)
- **Role/specialty** (different processes for different professional types)
- **Stage** (beginner vs. experienced, different starting points)
- **Budget** (different recommendations for different spending levels)

## What You Do (If Not Skipping)

### 1. Define Input Fields

What does the user need to provide for personalization to work?

```json
{
  "inputs": [
    {
      "field": "state",
      "type": "select",
      "options": ["All 50 states"],
      "required": true,
      "why": "Insurance panel requirements vary by state"
    },
    {
      "field": "specialty",
      "type": "select",
      "options": ["LCSW", "LMFT", "LPC", "Psychologist"],
      "required": true,
      "why": "Credential requirements differ by license type"
    }
  ]
}
```

### 2. Design Generation Logic

How do inputs transform the product?
- Conditional content: "If state = WA, include section on Apple Health panels"
- Variable substitution: "Your [LICENSE_TYPE] requires [SPECIFIC_CREDENTIAL]"
- Filtered recommendations: "Top 5 panels for [SPECIALTY] in [STATE]"
- Calculated timelines: "Based on your [STATE], expect [X] weeks for processing"

### 3. Specify Outputs

What exactly changes?
- Customized checklist (state-specific document requirements)
- Tailored timeline (state processing times)
- Personalized recommendations (relevant panels for their specialty)
- Custom scripts (with their license type in the email templates)

### 4. Document Update Strategy

How does the personalized content stay current?
- What data sources need monitoring?
- How often should information be refreshed?
- What's the cost of being out of date?

## Output

Save `runs/{slug}/personalization_spec.json`.

## Next

Read `phases/13-packaging.md` and begin Phase 13.
