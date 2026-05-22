# FLYWHEEL.md

> Example for a web service or API. Adapt the stages and gates to your process. The full idea: [flywheel.md](https://flywheel.md).

**How an agent ships and improves this service, turn by turn.** `AGENTS.md` says what to do, `SOUL.md` says who to be, `FLYWHEEL.md` says how a change travels from idea to deployed to improved.

## The loop

1. **Plan.** Assess the blast radius. Schema or data migration? Rollback plan?
   - *Gate (human):* migrations and risky deploys need a sign-off.
2. **Build.** Implement, and add the logs, metrics, or traces that will prove it works.
3. **Review.** Tests pass, and the migration is safe under concurrent reads and writes.
4. **Ship.** Deploy behind a staged rollout or canary, with a rollback ready.
   - *Done when:* live and serving real traffic.
5. **Verify.** Hit the real endpoint after the deploy; confirm status, body, latency, and error rate on the dashboards.
6. **Learn.** Watch metrics, logs, and traces through a bake window.
   - *Gate (often):* wait out the bake window before full rollout or the next turn.
7. **Improve.** Fix the cause. Never bump a timeout or retry to hide a real failure.

## Humans in the loop

**Migrations and rollouts** are where production breaks. Gate them: a human approves the migration plan, and the agent waits out the bake window before calling it done.

## The bar (every stage)

- Done means verified in production, on the real endpoint.
- The API is a contract: version breaking changes.
- Observability ships with the change.
- Leave a trail.

## How to adopt

Drop this in your repo root next to `AGENTS.md` and `SOUL.md`, then tune the stages and gates to your service.
