# FLYWHEEL.md

> Example for a machine-learning model or data project. Adapt the stages and gates to your process. The full idea: [flywheel.md](https://flywheel.md).

**How an agent ships and improves this model, turn by turn.** This is the data flywheel: each turn's real-world feedback trains the next. `AGENTS.md` says what to do, `SOUL.md` says who to be, `FLYWHEEL.md` says how it travels from hypothesis to deployed to improved.

## The loop

1. **Plan.** State the hypothesis, the eval that will judge it, and the baseline to beat.
2. **Train.** Train the model; version the data, config, seed, and weights together.
   - *Done when:* the run is reproducible by someone else.
3. **Evaluate.** Run on held-out or live data the model never trained on; compare to the production baseline; check secondary metrics for regressions.
   - *Gate (human):* a person reviews the eval before promotion. A lower training loss is not an improvement.
4. **Ship.** Promote the model, often shadow or A/B first.
5. **Verify.** Confirm live metrics on real traffic match the offline eval.
6. **Learn.** Capture real-world feedback and monitor for drift. This feedback is the next turn's training data.
   - *Gate (often):* collect enough signal before retraining.
7. **Improve.** Retrain with the new data. When a metric moves, find whether it was the data, the label, or the model, not just the hyperparameters.

## Humans in the loop

Keep the **eval-review gate before promotion** human: metrics mislead, and a win on one can hide a loss on another. The loop itself runs on a world-feedback gate at Learn.

## The bar (every stage)

- Done means evaluated on real, held-out data, then verified live.
- Reproducible or it did not happen: version data, seed, config, weights.
- No eval regressions against the production baseline.
- Leave a trail: a model card with the data, the eval, and the why.

## How to adopt

Drop this in your repo root next to `AGENTS.md` and `SOUL.md`, then tune the stages and gates to your project.
