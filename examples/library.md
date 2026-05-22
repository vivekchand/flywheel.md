# FLYWHEEL.md

> Example for a library or SDK. Adapt it, keep the bar. The full idea: [flywheel.md](https://flywheel.md).

**How an agent ships and improves this library, end to end.** `AGENTS.md` says what to do, `SOUL.md` says who to be, `FLYWHEEL.md` says how to ship.

## The loop

Ship → verify → learn → improve. Every release turns the wheel.

## The bar (non-negotiable)

1. **Done means published and verified.** Install the published package in a fresh project and import it. A passing local test suite is not a release.
2. **The public API is a promise.** No breaking changes without a major bump and migration notes. Treat exported signatures and types as the contract.
3. **Docs ship with the code.** An undocumented feature is not done. Update the README and examples in the same change.
4. **Fix the cause, never the symptom.** If a test encodes the wrong expectation, fix the test to match reality. Don't delete it.
5. **Leave a trail.** A changelog entry with the why, so the next release and the next contributor start informed.

## How to adopt

Drop this file in your repo root next to `AGENTS.md` and `SOUL.md`, then trim it to your library.
