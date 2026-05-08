# Uniswap — Writing Standard (demo)

The mechanical rules. Apply after the voice rules.

## 1. Words we use
- Specific verbs: *deploy, fork, swap, route, settle, attest, propose, delegate, audit, ship, pin.*
- Concrete nouns: *pool, hook, swap, route, pair, fee tier, proposal, delegate, voter, audit, multisig, treasury.*
- Sample in-voice line: *"You can fork the pool, deploy the hook, and run a fork test in under an hour."*

## 2. Words we avoid
- *Leverage* (verb), *unlock, empower, seamless, robust, innovative, transformative.*
- *Ecosystem* used to mean "everyone we vaguely know".
- *Primitive* used loosely. Use it only when discussing on-chain composability with care.
- *Compose* / *composable* — overused; use only when the composition is specific and shown.

## 3. Sentence rules
- Active voice unless passivity is the point.
- Numbers as digits when ≥10 (and always in stats).
- Contractions are fine and expected. *We're, you'll, doesn't.*

## 4. Formatting rules
- One idea per paragraph.
- Bullets only when items are genuinely parallel.
- Bold reserved for genuine UI/structural callouts. Not for emphasis.
- Code samples in backticks. Function names in `monospace`.

## 5. Capitalization
- Sentence case for headlines. Always.
- Product / protocol names: *Uniswap*, *Uniswap v4*, *UniswapX*. Lowercase *v* in *v2 / v3 / v4*. *UNI* (all-caps) for the token.
- Feature names: lowercase common nouns unless they are trademarks. *hooks*, *flash accounting* (lowercase).

## 6. Number formatting
- *$1.2M*, not *$1,200,000*.
- *84%*, not *eighty-four percent*.
- TVL, volume, fees: in USD by default; specify chain or pool when relevant.
- Round only to a precision the reader can act on.
