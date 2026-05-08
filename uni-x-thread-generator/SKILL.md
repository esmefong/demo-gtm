---
name: uni-x-thread-generator
description: Generate an X (Twitter) post or thread for Uniswap demo content. Consults the brand foundation, drafts using the right ICP and opener pattern, then runs ai-writing-detector as the final QA gate.
---

# Uniswap — X Thread Generator (demo)

## When to invoke
- User asks for an X / Twitter post, thread, or reply.

## Inputs (ask if missing)
- **Format:** single post / thread / reply chain.
- **Topic / claim:** what is this about?
- **ICP:** v4 hook dev / treasury — must match `icp.md`.
- **Surface:** protocol account / devrel account / individual contributor.
- **Opener pattern preference:** unexpected number / named scenario / technical reframe. If unset, pick from topic.

## Workflow

1. **Consult references** in this order:
   - `uni-brand-foundation/references/voice-core.md`
   - `uni-brand-foundation/references/voice-x.md`
   - `uni-brand-foundation/references/icp.md` (only the targeted ICP)
   - `uni-brand-foundation/references/real-examples.md`
   - `uni-brand-foundation/references/writing-standard.md`

2. **Draft v1** — strict adherence to the chosen opener pattern and the structure rules in `voice-x.md`.
   - Single post: <240 chars.
   - Thread: tweet 1 must stand alone if nobody clicks; one link in final tweet only.

3. **Self-review against `writing-standard.md`** — kill banned words, fix length, check vocabulary matches the targeted ICP.

4. **QA gate (mandatory)** — invoke `ai-writing-detector`. Resolve HIGH flags before returning. Up to 3 revision passes; if still flagged, return draft + flag report and ask for human judgment.

5. **Save** — `output/YYYY-MM-DD-x-{slug}.md` with frontmatter (channel: x, ICP, target_kpi, detector_status).

## Output checklist (before returning)
- One specific number; not three.
- Tweet 1 stands alone.
- ICP-1 vocabulary OR ICP-2 vocabulary, never mixed.
- Detector clean.
- 🦄 used at most once and only structurally.
