# Phase 11: ARTIFACTS

**Role**: Template creator building support materials
**Tools**: None — creation

## What You Do

Create the support materials planned in `outline.json` under `planned_artifacts`. You need at least 3. These are often the most valuable part of the product — buyers use templates long after they forget the prose.

### Artifact Types

**Checklists** — Step-by-step process lists the reader can print and follow.
- Format: Numbered or checkboxed items
- Quality test: Can someone follow this without reading the main product? It should stand alone.

**Templates** — Fill-in-the-blank documents.
- Format: Structured document with [PLACEHOLDER] fields and brief instructions for each field
- Quality test: Is every field labeled clearly? Are there examples of good fill-ins?

**Scripts** — Word-for-word copy for phone calls, emails, or negotiations.
- Format: Ready-to-use text with [VARIABLE] placeholders for personalization
- Quality test: Could someone copy-paste this and send it with minimal editing?

**Calculators / Decision Frameworks** — Structured decision tools.
- Format: Input fields → logic → output recommendation
- Quality test: Does it produce a clear, actionable answer?

**Worksheets** — Guided exercises for self-assessment or planning.
- Format: Questions with space for answers, reflection prompts
- Quality test: Will the reader have clarity they didn't have before completing it?

### Quality Standard

Each artifact must be **immediately usable**. The reader should be able to open it, understand what to do, and start using it without needing to read the main product first. This means:

- Clear title and one-sentence description of what it does
- Brief instructions (2-3 sentences max) at the top
- All fields labeled
- Examples where helpful
- No jargon that isn't defined

### Naming Convention

`artifact-{type}-{short-name}.md`

Examples:
- `artifact-checklist-credentialing-documents.md`
- `artifact-template-panel-application-tracker.md`
- `artifact-script-follow-up-email.md`

## Output

Save each artifact as a separate file in `runs/{slug}/artifacts/`.

Save `runs/{slug}/artifact_manifest.json`:

```json
{
  "artifacts": [
    {
      "filename": "artifact-checklist-credentialing-documents.md",
      "type": "checklist",
      "title": "Required Documents Checklist",
      "description": "Every document you need before starting your first panel application",
      "standalone": true
    },
    {
      "filename": "artifact-template-panel-tracker.md",
      "type": "template",
      "title": "Panel Application Tracker",
      "description": "Track every application's status, dates, and follow-up schedule",
      "standalone": true
    },
    {
      "filename": "artifact-script-follow-up-email.md",
      "type": "script",
      "title": "Follow-Up Email Scripts",
      "description": "Copy-paste emails for checking application status at 30, 60, and 90 days",
      "standalone": true
    }
  ],
  "total_count": 3,
  "types_covered": ["checklist", "template", "script"]
}
```

## Next

Read `phases/12-personalization.md` and begin Phase 12.
