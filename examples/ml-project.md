# FLYWHEEL.md

> Example for a machine-learning model or data project. Adapt it, keep the bar. The full idea: [flywheel.md](https://flywheel.md).

**How an agent ships and improves this model, end to end.** `AGENTS.md` says what to do, `SOUL.md` says who to be, `FLYWHEEL.md` says how to ship.

## The loop

Ship → verify → learn → improve. This is the data flywheel: each release produces feedback that trains the next, and the loop compounds.

## The bar (non-negotiable)

1. **Done means evaluated on real, held-out data.** Verify on an eval set or live traffic the model never trained on, not on training metrics. A lower training loss is not an improvement.
2. **Reproducible or it didn't happen.** Version the data, the seed, the config, and the weights. Someone else (or future-you) must be able to rerun and get the same number.
3. **No eval regressions.** A win on one metric that quietly breaks another is not a win. Compare against the current production baseline.
4. **Close the data loop, watch for drift.** Capture feedback from real use to improve the next version, and monitor for distribution drift after deploy.
5. **Fix the cause, never the symptom.** When a metric moves, find out whether it was the data, the label, or the model. Don't just tune hyperparameters until the number looks right.
6. **Leave a trail.** A model card or changelog with the data, the eval, and the why.

## How to adopt

Drop this file in your repo root next to `AGENTS.md` and `SOUL.md`, then trim it to your project.
