# FLYWHEEL.md

> Example for a command-line tool. Adapt the stages and gates to your process. The full idea: [flywheel.md](https://flywheel.md).

**How an agent ships and improves this CLI, turn by turn.** `AGENTS.md` says what to do, `SOUL.md` says who to be, `FLYWHEEL.md` says how a change travels from idea to released to improved.

## The loop

1. **Plan.** Scope the change. Does it touch the public surface (flags, output format, exit codes)?
   - *Gate (human):* a breaking change to that surface needs a sign-off and a deprecation plan.
2. **Build.** Implement in small steps; update `--help` and docs alongside the code.
3. **Test the matrix.** Run the suite on every OS and shell you support.
   - *Done when:* green on the full matrix, not just your machine.
4. **Release.** Tag a semver version and publish to the package manager(s).
5. **Verify.** Install the *published* artifact in a clean environment, run the real command, confirm output and exit code on each OS.
   - *Done when:* you have run the shipped binary, not the local build.
6. **Learn.** Watch the issue tracker and install failures for the new version.
   - *Gate (often):* give it a day of real installs before the next turn.
7. **Improve.** Fix the cause, add a changelog entry with the why.

## Humans in the loop

The gate that matters most is the **public-surface contract**: scripts and pipelines depend on your flags and output. Pause for a human before anything that could break them.

## The bar (every stage)

- Done means the published artifact verified, not a green test suite.
- Cross-platform or it did not ship.
- Fix the cause, never the symptom.
- Leave a trail.

## How to adopt

Drop this in your repo root next to `AGENTS.md` and `SOUL.md`, then tune the stages and gates to your tool.
