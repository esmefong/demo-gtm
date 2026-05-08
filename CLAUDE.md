# Uniswap (demo) — Brand Orchestration

You are Claude, working inside a demonstration go-to-market repository for Uniswap. When the user asks you to write or edit any customer-facing content, follow this orchestration.

> **Demo notice.** This repo is an Atrium-built illustrative sample. It is not official Uniswap material. Do not represent generated content as coming from Uniswap Labs, the Uniswap Foundation, or any team member.

## Routing table

| Intent | Skill to invoke |
|---|---|
| X / Twitter post or thread | `uni-x-thread-generator` |
| LinkedIn post (institutional, regulatory, hiring) | `uni-linkedin-post-generator` |
| Newsletter, governance digest, dev broadcast | `uni-newsletter-pipeline` |
| Landing page, docs landing, hackathon page, hook spotlight | `uni-landing-page-generator` |
| Event / conference / hackathon / AMA — multi-channel push | `uni-event-announcement-pipeline` |
| "Audit our voice" / unscoped review | Invoke `uni-brand-foundation` to surface relevant references, then proceed |

## Mandatory QA gate

Every workflow skill MUST end by invoking `ai-writing-detector`. If any HIGH-severity flag fires, revise and re-run. Do not return content to the user that has not passed the gate.

## Reference precedence

1. `voice-core.md` — universal, never overridden
2. `voice-{channel}.md` — channel-specific overrides
3. `writing-standard.md` — word/phrase rules
4. `brand-kit.md` — visual and naming

## ICP gating

Before generating, identify which ICP from `icp.md` the piece is targeting. If you cannot, stop and ask. Generic-audience content is disallowed — every piece is written for a specific reader, not a market.

## Output convention

Save final drafts to `output/YYYY-MM-DD-{slug}.md` with frontmatter:

```yaml
---
channel: x | linkedin | newsletter | landing | event
icp: hook-dev | treasury
target_kpi: replies, sign-ups, hook-deployments, etc.
detector_status: passed | passed-with-low-flags
notes: any flags the detector raised that the human should sanity-check
---
```
