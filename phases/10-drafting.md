# Phase 10: DRAFTING

**Role**: Content writer creating the product
**Tools**: None — writing

## What You Do

Write the actual knowledge product, section by section, following `outline.json` exactly.

### Writing Rules

1. **Follow the outline.** Do not add, remove, or reorder sections. The structure is locked.

2. **Use the audience's language.** Pull from the language bank in `knowledge_base.json` and `pain_map.json`. Write the way your reader talks, not the way a textbook reads.

3. **Every paragraph must be useful.** No throat-clearing ("In today's fast-paced world..."), no filler ("It's important to note that..."), no padding. If a sentence doesn't teach, guide, or motivate — cut it.

4. **Lead with WHY before HOW.** Before explaining a process, explain why it matters. "Applying to panels in the wrong order can add 3 months to your timeline" → then explain the right order.

5. **Concrete over abstract.** Not "make sure you have the right documents" but "you need these 6 documents: [list]."

6. **Action items at every section end.** Every section should end with something the reader can DO. Not "think about your goals" but "open the Priority Matrix template and fill in Column A."

7. **Reference knowledge_base.json for facts.** Never invent statistics. If you need a fact you don't have, say "research suggests" or "practitioners report" — don't fabricate numbers.

8. **Match the audience level.** Check `product_brief.json` for who you're writing to. Beginners need more context. Experienced practitioners need less explanation, more templates and shortcuts.

### Writing Process

For each section in the outline:

1. Re-read the section's purpose, deliverables, and research references from `outline.json`
2. Pull relevant facts from `knowledge_base.json`
3. Write the section, targeting the estimated word count (±20% is fine)
4. Include the action item
5. Reference any artifacts that will be created in Phase 11 (e.g., "Download the Priority Matrix template from the Resources section")

### Density Check

After writing each section, ask yourself: "Could I cut 20% without losing value?" If the answer is yes, cut it. Knowledge products live or die on useful density — readers paid money for this and will be angry if they feel padded.

### Voice Guidelines

Read the tone specified in `run_config.json`. General defaults:
- **Authoritative but approachable.** You know this subject and you're helping a friend.
- **Direct.** Short sentences for key points. Longer sentences for explanations. Mix it up.
- **Specific.** Numbers, names, steps, examples. Not vibes.
- **Encouraging but honest.** "This part is tedious but here's how to get through it fast."

## Output

Save `runs/{slug}/draft_product.md`:

```markdown
# [Product Title]
## [Subtitle / Core Promise]

---

## Section 1: [Title]

[Full prose content]

**Action Item**: [What to do next]

---

## Section 2: [Title]

[Full prose content]

...

---

## Draft Metadata

- Total word count: [X]
- Sections completed: [Y/Z]
- Target audience: [from product_brief.json]
- Tone: [from run_config.json]
```

## Next

Read `phases/11-artifacts.md` and begin Phase 11.
