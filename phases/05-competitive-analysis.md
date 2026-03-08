# Phase 5: COMPETITIVE ANALYSIS

**Role**: Competitive intelligence researcher
**Tools**: Web search, browse/visit pages

## What You Do

Map everything that currently exists in this space. You need to understand what the buyer's alternatives are — not just direct competitors but every way someone might try to solve this problem.

### 1. Search for Direct Competitors

Search queries:
- `"[niche]" course`
- `"[niche]" template`
- `"[niche]" guide`
- `"[niche]" toolkit`
- `"[niche]" service`
- `"[niche]" ebook`
- `"[niche]" gumroad`
- `"[niche]" udemy`

### 2. Visit Competitor Sales Pages

For each competitor you find, visit their page and document:
- **Name and URL**
- **Price** (exact, or range if tiered)
- **Format** (course, ebook, template pack, service, software)
- **Core promise** (what transformation do they sell?)
- **What's included** (modules, templates, bonuses)
- **Weaknesses** (from reviews, obvious gaps, or your assessment):
  - Too generic? (not niche-specific enough)
  - Too expensive? (pricing doesn't match value)
  - Outdated? (old information, broken links)
  - Poor format? (video when templates would be better, etc.)
  - Missing pieces? (covers theory but no templates, etc.)

### 3. Map the Full Alternatives Landscape

| Category | Examples | Typical Cost | Limitations |
|----------|----------|-------------|-------------|
| Free resources | Blog posts, YouTube, government sites | $0 | Scattered, incomplete, often outdated |
| Books | Amazon KDP titles | $10-30 | Generic, no templates, no updates |
| Paid courses | Udemy, Teachable, Skillshare | $50-500 | Often too broad, video-heavy |
| Professional services | Consultants, agencies | $500-5000 | Expensive, creates dependency |
| Software/SaaS | Niche tools | $20-100/mo | Solves one piece, not the whole problem |

### 4. Identify Price Anchors

What are buyers used to paying in this space?
- **Low anchor**: Cheapest option (often a book or basic template)
- **Mid anchor**: Most common price point
- **High anchor**: Premium option (service or comprehensive course)

Your product should be priced relative to these anchors.

### 5. Find White Space

Based on your analysis: what's missing that you can fill?
- Is everyone doing courses when people actually need templates?
- Is everything generic when people need state/industry-specific guidance?
- Are services too expensive, leaving no mid-tier DIY option?
- Is everything outdated?

## Output

Save `runs/{slug}/competitor_map.json`:

```json
{
  "direct_competitors": [
    {
      "name": "Credentialing Made Easy Course",
      "url": "https://...",
      "price": "$199",
      "format": "video course",
      "promise": "Get credentialed in 90 days",
      "included": ["12 video modules", "PDF worksheets"],
      "weaknesses": ["Generic — not state-specific", "No templates, just instruction", "Last updated 2023"],
      "reviews_summary": "Mixed — helpful concepts but too general"
    }
  ],
  "alternatives": {
    "free": ["CAQH registration guide (official but confusing)", "Scattered blog posts"],
    "books": ["Insurance Credentialing for Therapists ($24, Amazon)"],
    "courses": ["Credentialing Made Easy ($199)"],
    "services": ["Credential My Practice ($500-1500)"],
    "tools": ["Medallion ($99/mo SaaS — enterprise focused)"]
  },
  "price_anchors": {
    "low": "$24 (book)",
    "mid": "$97-199 (course/guide)",
    "high": "$500-1500 (service)"
  },
  "white_space": "No state-specific, template-heavy, self-service playbook exists in the $79-149 range. Everyone is either too generic, too expensive, or too scattered."
}
```

## Next

Read `phases/06-opportunity-scoring.md` and begin Phase 6.
