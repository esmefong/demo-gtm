---
name: uni-landing-page-generator
description: Draft landing-page copy for Uniswap demo content — hook spotlight pages, hackathon pages, docs landings, campaign pages. Generates above-the-fold + section grammar, then runs ai-writing-detector.
---

# Uniswap — Landing Page Generator (demo)

## When to invoke
- Hook spotlight page, hackathon page, campaign page, docs landing, partner page. Not for blog posts.

## Inputs (ask if missing)
- **Page intent:** hook spotlight / hackathon / docs landing / campaign / partner.
- **ICP:** ICP-1 (devs) or ICP-2 (treasury). Both is a smell; pick.
- **Primary CTA:** deploy on testnet / read the docs / view the GitHub / register / RSVP.
- **Source material:** numbers we can name, integrations we can credit, screenshots planned.

## Workflow

### Stage 1 — Above the fold
- H1: format per `voice-landing-page.md` ("what it is + who it's for").
- Subhead: the non-obvious mechanism.
- Primary CTA: verb + outcome.
- "Could-be-anyone" check: if H1 could appear on three other DEX or L2 sites, rewrite.

### Stage 2 — Section grammar
- Default sections: *Why this matters → How it works → What you ship → Proof → Get started*.
- Each section: claim → evidence → friction-removed.

### Stage 3 — Forbidden tropes scan
- Run against the forbidden list in `voice-landing-page.md`.
- Strip generic chart heroes, "next-generation" framing, logo walls without specific numbers attached.

### Stage 4 — Social proof
- Specific numbers, named integrations.
- If a number isn't available, leave `[NUMBER NEEDED]`. Never invent one.

### Stage 5 — QA gate (mandatory)
- `ai-writing-detector` on full page copy.

### Stage 6 — Save
- `output/YYYY-MM-DD-page-{slug}.md`.

## Output checklist
- H1 passes the 3-second test in `voice-core.md`.
- One primary CTA. One secondary. No third.
- Every section either has a number or `[NUMBER NEEDED]`.
- Detector clean.
