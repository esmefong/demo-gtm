---
name: uni-newsletter-pipeline
description: Generate a newsletter / governance digest issue, or a broadcast email to the dev list. Multi-stage pipeline with mandatory ai-writing-detector gate.
---

# Uniswap — Newsletter / Governance Digest Pipeline (demo)

## When to invoke
- Periodic newsletter, governance digest, or broadcast to the dev mailing list.

## Inputs (ask if missing)
- **Issue type:** weekly digest / governance update / dev broadcast / launch announcement.
- **Anchor (single most consequential thing this issue covers):** required.
- **Sections to include:** *what shipped*, *governance this week*, *things to read*, *builder's corner*.
- **Primary CTA:** read the proposal / deploy on testnet / RSVP.

## Pipeline stages

### Stage 1 — Subject + preview
- Generate 3 subject candidates. 4–7 words. State, don't tease.
- Preview line extends the subject; never repeats it.
- Pick strongest combo; document why in a one-line note.

### Stage 2 — Body draft
- Open with the anchor in the first sentence. No greeting. No "we hope you're well".
- Section grammar per `voice-email.md`.
- One primary link per section, surfaced inline.

### Stage 3 — Cadence + CTA check
- Match length target in `voice-email.md`.
- Confirm one primary CTA. If two were requested, force a choice.

### Stage 4 — QA gate (mandatory)
- `ai-writing-detector` on the body. Subjects have their own pattern checks; flag if any subject hits HIGH.

### Stage 5 — Save
- `output/YYYY-MM-DD-newsletter-{slug}.md` with frontmatter.

## Failure modes to watch
- Issues that recap last week's issue instead of moving the argument forward.
- Governance updates that explain what a proposal *says* without telling readers who's already weighed in.
- "Builder's corner" sections that drift into general DeFi commentary instead of staying ICP-1-specific.
