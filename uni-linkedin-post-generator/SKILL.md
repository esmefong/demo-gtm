---
name: uni-linkedin-post-generator
description: Generate a LinkedIn post for Uniswap demo content. Targets institutional / regulatory / hiring readers who don't live on X. Final QA via ai-writing-detector.
---

# Uniswap — LinkedIn Post Generator (demo)

## When to invoke
- Institutional positioning, governance/regulatory observations, hiring posts, partner posts aimed at TradFi-adjacent readers.

## Inputs (ask if missing)
- **Topic:** what is the post about?
- **ICP:** for LinkedIn, almost always ICP-2 (treasury / institutional). If the post targets ICP-1 (devs), reconsider — they're on X, not LinkedIn.
- **Surface:** protocol page / a named exec posting in their own voice (rare; verify the user's authority).
- **Hook pattern:** compliance-aware / infra framing / hiring-or-ops framing.

## Workflow

1. **Consult references:**
   - `voice-core.md`
   - `voice-linkedin.md`
   - `icp.md` (ICP-2 by default)
   - `real-examples.md`
   - `writing-standard.md`

2. **Draft v1** — match the hook pattern; strip emojis; respect the 100–180 word target.

3. **Self-review** — confirm zero crypto-meme language; the post should read fluently to someone who has never used a DEX.

4. **QA gate (mandatory)** — `ai-writing-detector`.

5. **Save** — `output/YYYY-MM-DD-linkedin-{slug}.md`.

## Output checklist
- Reads fluently to a TradFi reader. Send to a non-crypto reader if uncertain.
- One stance per post.
- No 🦄 emoji. No GM/WAGMI. No 🚀.
- Detector clean.
