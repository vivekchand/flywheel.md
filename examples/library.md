# FLYWHEEL.md

> Example for a library or SDK. Adapt the stages and gates to your process. The full idea: [flywheel.md](https://flywheel.md).

**How an agent ships and improves this library, turn by turn.** `AGENTS.md` says what to do, `SOUL.md` says who to be, `FLYWHEEL.md` says how a change travels from idea to published to improved.

## The loop

1. **Plan.** Does this change the public API (exported signatures, types, behavior)?
   - *Gate (human):* an API change needs review, and if breaking, a major bump with migration notes.
2. **Build.** Implement, and write or update the docs and examples in the same change.
3. **Review.** Run tests across every runtime version you support; check the public types.
   - *Done when:* green across versions, with the public surface unchanged or intentionally bumped.
4. **Release.** Publish to the registry with the right semver.
5. **Verify.** Install the *published* package in a fresh project, import it, run a smoke usage.
   - *Done when:* the published package works from a clean install, not just the local checkout.
6. **Learn.** Watch downstream issues and deprecation warnings in the wild.
7. **Improve.** Fix the cause. If a test encoded the wrong expectation, fix the test, do not delete it.

## Humans in the loop

The API is a promise to every downstream user you cannot see. Keep the **API-change gate** human: review before any signature or behavior change ships.

## The bar (every stage)

- Done means the published package verified from a clean install.
- The public API is a contract: no breaking changes without a major bump and migration notes.
- Docs ship with the code.
- Leave a trail.

## How to adopt

Drop this in your repo root next to `AGENTS.md` and `SOUL.md`, then tune the stages and gates to your library.
