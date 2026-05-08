---
name: uni-event-announcement-pipeline
description: Coordinate a multi-channel event push — hackathon, AMA, governance call, conference talk, launch. Generates a coherent set of X threads, LinkedIn post, newsletter section, and landing-page copy that share a locked anchor.
---

# Uniswap — Event Announcement Pipeline (demo)

The most complex skill in the repo. Use when an event needs to land across X, LinkedIn, the newsletter, and a landing page in one coordinated push.

## When to invoke
- Hackathons, governance calls, AMAs, conference appearances (Devcon / EthCC / ETHDenver), product launches, partner announcements.

## Inputs (required)
- **Event:** name, date, format, registration link.
- **Anchor message:** the one sentence the audience should remember.
- **Target ICP:** primary and (optionally) secondary.
- **Channel scope:** which of {X protocol, X devrel, LinkedIn, newsletter, landing page} to produce.
- **Lead time:** days to event. Drives cadence.

## Pipeline

### Stage 1 — Message architecture
Before any drafting, lock:
- **The hook:** one phrase that anchors every channel.
- **The proof:** one number or one named scenario every channel can lean on.
- **The CTA verb:** *register*, *RSVP*, *join*, *deploy* — pick one and use it everywhere.

If the user can't lock these in one round, stop. Do not proceed with a fuzzy anchor.

### Stage 2 — Cadence plan
Default cadence based on lead time:
- **14 days out:** newsletter section + LinkedIn post (institutional framing).
- **7 days out:** X thread (devrel angle, ICP-1).
- **3 days out:** X single post + landing-page CTA refresh.
- **Day-of:** X single post, "starting in 2 hours" version + LinkedIn reminder.

Adjust based on the user's lead time.

### Stage 3 — Drafting (per channel)
- **X posts/threads:** invoke `uni-x-thread-generator` for each, passing the locked hook and proof.
- **LinkedIn:** invoke `uni-linkedin-post-generator`.
- **Newsletter:** invoke `uni-newsletter-pipeline`.
- **Landing page:** invoke `uni-landing-page-generator`.

Each sub-skill consults the brand foundation independently. Do not duplicate that work here.

### Stage 4 — Coherence pass
- Read all generated assets together.
- Verify the hook phrase, proof, and CTA verb match across channels.
- If they drift, revise the outliers.

### Stage 5 — QA gate (mandatory, per asset)
- Each sub-skill already runs `ai-writing-detector`. After the coherence pass, re-run the detector on any asset that was edited in Stage 4.

### Stage 6 — Save
- One folder: `output/events/YYYY-MM-DD-{event-slug}/`.
- One file per asset.
- One `_index.md` summarizing the cadence and the locked anchor message.

## Failure modes to watch
- Each channel ends up with a different "main message" because no anchor was locked.
- Cadence drifts so the protocol-account post lands the day of the event with no buildup.
- Sub-skills generate inconsistent CTA verbs (register / RSVP / join). The coherence pass exists for this.
- ICP-1 and ICP-2 get mashed into the same asset. Split the asset; never split the ICP.
