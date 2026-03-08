# Phase 8: OUTLINE

**Role**: Content architect structuring the product
**Tools**: None — planning

## What You Do

Create the structural skeleton. Every downstream phase (writing, artifacts, packaging) follows this outline.

### Structure Principles

1. **Every section earns its place.** No filler, no "Introduction to [obvious concept]."
2. **Lead with the most urgent pain.** Don't build up — start with the thing they're desperate to know.
3. **Progress: Understand → Solve → Optimize.** First help them grasp the problem, then walk through the solution, then show them how to do it better/faster.
4. **End with quick wins and next steps.** Leave them feeling capable, not overwhelmed.

### For Each Section, Define:

```json
{
  "section_number": 1,
  "title": "Which Panels to Apply to First (And Why Order Matters)",
  "purpose": "Eliminate the biggest source of paralysis — not knowing where to start",
  "key_deliverables": ["Priority matrix template", "State-specific panel list"],
  "estimated_words": "800-1200",
  "research_references": ["pain_map: recurring question about which panels first", "competitor weakness: no one addresses sequencing"],
  "action_item": "Complete the Priority Matrix for your state and specialty"
}
```

### Scope Check

For each section, ask: "Can this be written in 1-2 focused hours?" If not, split it.

Total word count should be in the range that matches the product format:
- Playbook: 8,000-15,000 words
- Template library: 3,000-6,000 words (templates are the main value, text is instructional)
- Checklist system: 4,000-8,000 words
- Mini course: 10,000-20,000 words
- Resource guide: 5,000-10,000 words

### Artifact Planning

For each section, note what support artifacts will be needed. These get created in Phase 11, but plan for them now:
- Checklists referenced in the text
- Templates the reader will fill out
- Scripts they'll use word-for-word
- Calculators or decision frameworks

## Output

Save `runs/{slug}/outline.json`:

```json
{
  "product_title": "The Insurance Paneling Playbook",
  "format": "playbook + template library",
  "total_sections": 7,
  "estimated_total_words": 10000,
  "sections": [
    {
      "section_number": 1,
      "title": "...",
      "purpose": "...",
      "key_deliverables": ["..."],
      "estimated_words": 1200,
      "research_references": ["..."],
      "action_item": "..."
    }
  ],
  "planned_artifacts": [
    "Priority Matrix Template",
    "Application Tracking Spreadsheet",
    "Follow-Up Email Scripts",
    "Required Documents Checklist"
  ]
}
```

## Next

Read `phases/09-synthesis.md` and begin Phase 9.
