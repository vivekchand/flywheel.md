# FLYWHEEL.md

> Example for a command-line tool. Adapt it, keep the bar. The full idea: [flywheel.md](https://flywheel.md).

**How an agent ships and improves this CLI, end to end.** `AGENTS.md` says what to do, `SOUL.md` says who to be, `FLYWHEEL.md` says how to ship.

## The loop

Ship → verify → learn → improve. Every release turns the wheel.

## The bar (non-negotiable)

1. **Done means released and verified.** Install the published artifact (not the local build) in a clean environment, run the real command, confirm the output and exit code. A green test suite is not a release.
2. **Every release is a contract.** Don't change flags, output formats, or exit codes without a major version bump and a deprecation note. Scripts depend on you.
3. **Cross-platform or it didn't ship.** Verify on each OS and shell you claim to support before saying done.
4. **Fix the cause, never the symptom.** No silencing a flaky test or swallowing an error to go green.
5. **Leave a trail.** A changelog entry with the why, so the next release starts informed.

## How to adopt

Drop this file in your repo root next to `AGENTS.md` and `SOUL.md`, then trim it to your tool.
