# Phase 13: PACKAGING

**Role**: Product packager assembling the final deliverable
**Tools**: None — organization

## What You Do

Assemble everything into a buyer-facing product stack and verify completeness.

### 1. Define the Product Stack

What the buyer receives:

```
📦 [Product Name]
├── 📄 Main Product (draft_product.md → formatted)
├── 🎁 Bonuses
│   ├── [Bonus 1 — something that increases perceived value]
│   └── [Bonus 2 — something that addresses a secondary pain]
├── 🔧 Support Artifacts
│   ├── [Artifact 1]
│   ├── [Artifact 2]
│   └── [Artifact 3+]
└── 📋 Quick Start Guide (1-page "do this first" instructions)
```

### 2. Create the Quick Start Guide

A one-page document that tells the buyer exactly what to do first. Buyers who open a product and feel overwhelmed → refund. Buyers who open a product and immediately get a win → tell friends.

Format:
```markdown
# Quick Start: [Product Name]

Welcome. Here's what to do right now:

1. **First** (5 minutes): [smallest possible action]
2. **Then** (15 minutes): [next step that builds momentum]
3. **Today** (30 minutes): [action that delivers a visible result]

After that, work through the main guide section by section.
```

### 3. Create the Package Manifest

Everything in the package, with file names, types, and descriptions.

### 4. Set Version

Start at v1.0. Note what would change in v1.1 (based on potential buyer feedback).

## GATE 4 — Artifact Completeness

**State your gate decision explicitly.**

```
GATE 4 — Artifact Completeness
Main draft: [EXISTS / MISSING]
Support artifacts: [N] created (minimum 3)
Quick start guide: [EXISTS / MISSING]
Package manifest: [EXISTS / MISSING]
Decision: [PASS / FAIL]
```

**PASS criteria**: Main draft + 3 or more support artifacts + quick start guide + package manifest
**FAIL criteria**: Any key component missing

**If FAIL**: Return to the relevant phase and create the missing component. Then re-evaluate this gate.

**If PASS**: Continue.

## BUILD Mode: Stop Here

If the current mode is BUILD, stop after saving the package manifest. Summarize to the user:
- What's in the package
- Total word count of main product
- Number and types of artifacts
- Recommended next step (usually: review the draft, then run LAUNCH mode)

## All Other Modes: Continue

Read `phases/14-launch-assets.md` and begin Phase 14.

## Output

Save `runs/{slug}/package_manifest.json`:

```json
{
  "product_name": "The Insurance Paneling Playbook",
  "version": "1.0",
  "price": "$97",
  "contents": [
    {
      "item": "Main Playbook",
      "filename": "draft_product.md",
      "type": "main_product",
      "words": 10500
    },
    {
      "item": "Quick Start Guide",
      "filename": "quick-start.md",
      "type": "quick_start"
    },
    {
      "item": "Required Documents Checklist",
      "filename": "artifacts/artifact-checklist-credentialing-documents.md",
      "type": "artifact"
    }
  ],
  "total_files": 7,
  "delivery_format": "ZIP bundle → Gumroad",
  "v1_1_notes": "Add state-specific appendices based on buyer feedback about which states need them"
}
```
