# Phase 2: DISCOVERY

**Role**: Research analyst finding real evidence
**Tools**: Web search

## Before You Start

Check if `memory/search_patterns.json` exists. If it does, read it — use proven search queries first before trying new ones.

## What You Do

You are looking for three categories of evidence. Every finding MUST have a URL or source attribution. Do not invent data.

### 1. Find Communities

Search for where people in this niche congregate online:
- Reddit subreddits
- Facebook groups (search for group names and discussions)
- Professional forums
- LinkedIn groups
- Niche-specific platforms (e.g., industry associations, Slack communities)

Search queries to try:
- `"[niche]" reddit`
- `"[niche]" forum`
- `"[niche]" community`
- `"[niche]" facebook group`

### 2. Find Spending Signals

Search for evidence that people in this niche pay money to solve their problem:
- `"[niche]" "paid $"`
- `"[niche]" "spent $"`
- `"[niche]" "worth every penny"`
- `"[niche]" "too expensive"`
- `"hired [niche] consultant"`
- `"[niche]" course review`
- `"[niche]" "saved me"`

When you find a signal, capture:
- The exact quote or paraphrase
- The dollar amount or time cost mentioned
- The source URL
- Context (who said it, where, when if available)

### 3. Find Pain Points

Search for documented frustration and confusion:
- `"[niche]" frustrated`
- `"[niche]" "struggling with"`
- `"how do I [niche]"`
- `"[niche]" help needed`
- `"[niche]" mistake`
- `"[niche]" "wish I knew"`

When you find a pain point, capture:
- The exact language people use (this becomes copywriting gold later)
- The frequency — is this one person or a recurring theme?
- The source URL

### 4. Assess Confidence

After searching, rate your confidence in the findings:
- **HIGH**: Multiple independent sources, clear spending signals, active communities
- **MEDIUM**: Some signals but thin, communities exist but aren't highly active
- **LOW**: Sparse results, few concrete signals, niche may be too small

## Output

Save `runs/{slug}/discovery_report.json`:

```json
{
  "communities": [
    {
      "name": "r/psychotherapy",
      "url": "https://reddit.com/r/psychotherapy",
      "estimated_size": "150k members",
      "relevance": "Direct match — therapists discuss credentialing frequently"
    }
  ],
  "spending_signals": [
    {
      "quote": "I paid $500 for a credentialing service and it was worth every penny",
      "amount": "$500",
      "type": "service",
      "source_url": "https://...",
      "context": "Solo practitioner, 2 years in practice"
    }
  ],
  "pain_patterns": [
    {
      "pattern": "Confusion about which insurance panels to apply to first",
      "exact_language": "I have no idea where to even start with paneling",
      "frequency": "recurring — found in 4+ threads",
      "source_url": "https://..."
    }
  ],
  "confidence": "HIGH",
  "search_queries_used": ["list of queries that produced results"],
  "notes": "any observations about the niche landscape"
}
```

## DISCOVER Mode: Stop Here

If the current mode is DISCOVER, stop after saving the discovery report. Summarize your findings to the user:
- Communities found
- Spending signals (how many, what amounts)
- Pain patterns (how many, how specific)
- Your confidence assessment
- Recommendation: worth validating further, or move on?

## All Other Modes: Continue

Read `phases/03-spending-analysis.md` and begin Phase 3.
