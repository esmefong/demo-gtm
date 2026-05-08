---
name: ai-writing-detector
description: Flags AI-generated patterns in customer-facing copy. Use as the final QA gate before any draft ships. Returns HIGH/MEDIUM/LOW severity flags with line-level evidence.
---

# AI Writing Detector

This skill runs a battery of pattern checks against a draft and returns flagged passages with severity. Use it as the LAST step in any writing workflow — never first, never skipped.

## How to use

1. Pass the full draft to this skill.
2. The skill returns a structured report: `{ severity, pattern_name, line, snippet, suggested_fix }`.
3. If any HIGH flag fires, revise that passage and re-run. Repeat until clean.
4. MEDIUM flags require judgment — usually revise; if the pattern is genuinely intentional, document why in the output frontmatter.
5. LOW flags are advisory.

## What this simplified version checks

This is a **simplified demonstration version**. The patterns it catches live in `references/detection-checklist.md`. They are the surface-level checks — the obvious tells that any reasonable reader can also spot.

## What this demo version does NOT include

- Embedding-based stylistic similarity scoring against the brand's authentic-voice corpus.
- Phrase-frequency drift detection (catching words that ChatGPT/Claude reach for more than humans do, *specifically in this brand's domain*).
- Sentence-rhythm variance analysis.
- Hedge-density and abstraction-level scoring.
- Continuous calibration as new model versions ship.

The production detector is updated weekly. This demo version is frozen.

## Failure mode

If a draft passes this detector and still reads as AI-generated to a human reviewer, that's a calibration signal. Log it in `references/detection-checklist.md` under "candidate patterns". The production detector ingests these signals into its weekly update; this demo does not.
