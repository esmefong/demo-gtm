# demo-gtm

*A simplified, illustrative version of an Atrium Academy brand repository.*

This repo demonstrates the structure we set up for the brands we partner with. **Uniswap is used here as a recognizable demonstration brand only.** This is an Atrium-built sample to show prospects what a brand foundation looks like when applied to a domain they already know. Nothing in this repo is official Uniswap material.

Real client repos contain proprietary assets, deeper guardrails, and channel-specific automations. What you see here is a deliberately stripped-down sample so you can see the shape without us giving away the playbook.

## What's inside

- **`CLAUDE.md`** — orchestration layer. Tells Claude which skill to invoke for each intent and enforces the QA gate.
- **`ai-writing-detector/`** — vendored QA skill that flags AI-sounding copy. Simplified for this demo; the live version is more aggressive and gets recalibrated as model behaviour shifts.
- **`uni-brand-foundation/`** — reference library. Voice, ICPs, writing standard, brand kit, examples, and benchmarks. Every workflow skill consults these files before generating a single word.
- **`uni-{channel}-*/`** — content workflow skills. One each for X, LinkedIn, newsletter, landing page, plus a multi-channel event pipeline. Each ends with the AI-writing-detector as the final QA gate.

## How a typical request flows

1. The user asks: *"Write a thread announcing a new v4 hook example for treasury managers."*
2. `CLAUDE.md` routes the request to `uni-x-thread-generator`.
3. The skill consults `voice-core.md`, `voice-x.md`, `icp.md` (treasury ICP), and `real-examples.md`.
4. It drafts.
5. `ai-writing-detector` runs as the final gate. If flags fire, the skill revises and re-runs until clean.
6. Output is saved with frontmatter, ready for human review.

## What you don't see in this sample

- The full reference library. Real ones are 5–10× the size — full ICP research, dev-community interviews, etc.
- Proprietary detection heuristics in the live AI-writing-detector and the weekly recalibration that keeps it sharp.
- Channel-specific automations: X scheduling, governance-forum cross-posting, Mirror, Farcaster.
- Multi-product orchestration when a brand has both a protocol surface and a wallet/app surface to maintain.
- Performance loops that retrain the prompts based on what's actually winning in market.

That's where the real work and the real lift happens.
