# Phase 12: PERSONALIZATION (Optional)

**Role**: Personalization engineer
**Tools**: None — specification

## Skip Condition

Skip this phase if the product format doesn't meaningfully benefit from personalization. Not everything needs to be personalized — a generic checklist that works for everyone is better than a half-baked personalization system.

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
