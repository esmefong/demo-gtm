# AI Writing Detection — Surface-Level Checklist

A simplified subset of the patterns the production detector flags. Each pattern includes severity, a short rationale, and an example.

## HIGH severity (block until fixed)

### 1. The "It's not just X, it's Y" construction
Why: overused by LLMs as a faux-insight pattern.
Example flagged: *"It's not just about pipeline — it's about predictability."*
Suggested fix: make a single, specific claim instead of a binary reframe.

### 2. Em-dash chaining (3+ in a paragraph)
Why: models lean on em-dashes to simulate cadence; humans rarely cluster them.
Suggested fix: replace with periods or commas; restructure if the paragraph still feels nested.

### 3. "Let me / Let's [verb]" openers
Why: telegraphs a generated answer pattern.
Examples flagged: *"Let me break this down."* / *"Let's dive in."*

### 4. Tricolon abuse (parallel triplets)
Why: LLMs default to threes when uncertain about emphasis.
Example flagged: *"It's faster, smarter, and more reliable."*
Suggested fix: cut to one strong claim, or break into separate sentences with different rhythms.

## MEDIUM severity (revise unless intentional)

### 5. Hollow hedges
Phrases: *"in today's fast-paced world"*, *"in the realm of"*, *"navigating the complexities of"*.
Suggested fix: cut, or replace with a specific noun.

### 6. Word-list flags
A short list of words over-represented in LLM output relative to authentic writing in this brand's domain. The production detector maintains a dynamic list of ~80 terms; this demo includes a base set plus a crypto-domain extension.

**Base list (5):**

- *delve* / *delving*
- *leverage* (as a verb)
- *seamless* / *seamlessly*
- *robust*
- *unlock*

**Crypto-domain extension (4):**

- *ecosystem* (when used to mean "vaguely related projects")
- *primitive* (used loosely instead of pointing at the specific composability)
- *compose* / *composable* (unless the composition is shown, not claimed)
- *rails* (almost always a tell when used metaphorically)

### 7. Empty intensifiers
*"truly"*, *"absolutely"*, *"genuinely"*, *"really"* — flag if more than 1 per 200 words.

## LOW severity (advisory)

### 8. Question-then-answer rhythm
*"What does this mean for revenue teams? It means..."*
Often fine, but if used 2+ times in a short piece it reads as scaffolding.

### 9. Closing summary that restates the open
A near-tautological wrap. Suggested fix: replace with a forward-looking action, a specific question, or a single sentence the reader can quote.

## Candidate patterns (logged here, promoted upstream)

This is the queue. The production detector ingests it; this demo does not.

- (none currently logged in this demo)
