---
name: uni-brand-foundation
description: Reference library for Uniswap demo content. Use this skill before generating any customer-facing copy. Surfaces voice, ICP, writing standard, and example references for the channel and intent at hand.
---

# Uniswap Brand Foundation (demo)

The source of truth for voice, audience, and writing rules in this demo repo. Every workflow skill consults this skill first.

## When to invoke

- Before drafting any content (every workflow skill calls this)
- "Audit our voice" / "review this draft"
- When the user references brand identity, ICP, or messaging

## Reference files

| File | What it contains |
|---|---|
| `references/voice-core.md` | Universal voice, tonal pillars, banned defaults |
| `references/voice-x.md` | X / Twitter post + thread structure, opener patterns |
| `references/voice-linkedin.md` | LinkedIn structure for institutional + regulatory voice |
| `references/voice-email.md` | Newsletter / governance digest cadence |
| `references/voice-landing-page.md` | Above-the-fold pattern, section grammar, forbidden tropes |
| `references/icp.md` | Two ICPs: v4 hook developers, DAO treasuries / institutions |
| `references/writing-standard.md` | Words to use / avoid, sentence rules |
| `references/brand-kit.md` | Colors, typography, naming, taglines |
| `references/real-examples.md` | In-voice content samples |
| `references/analytics-benchmarks.md` | Per-channel KPI floors and stretch targets |

## Precedence

When references conflict, follow the order in `CLAUDE.md` → "Reference precedence".
