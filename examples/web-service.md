# FLYWHEEL.md

> Example for a web service or API. Adapt it, keep the bar. The full idea: [flywheel.md](https://flywheel.md).

**How an agent ships and improves this service, end to end.** `AGENTS.md` says what to do, `SOUL.md` says who to be, `FLYWHEEL.md` says how to ship.

## The loop

Ship → verify → learn → improve. Every deploy turns the wheel.

## The bar (non-negotiable)

1. **Done means deployed and verified in production.** Hit the real endpoint after the deploy, confirm the status code, body, and latency. A green test suite and a successful build are not a verification.
2. **The API is a contract.** No breaking changes to routes, payloads, or status codes without a versioned path and a deprecation window. Clients you can't see depend on you.
3. **Observability ships with the change.** New behavior needs logs, metrics, or traces to confirm it works and to debug it later. If you can't see it, you can't say it works.
4. **Migrations are safe under live traffic.** Schema and data changes must survive concurrent reads/writes and have a rollback. Never take a lock that stalls production.
5. **Fix the cause, never the symptom.** No bumping timeouts or retries to paper over a real failure.
6. **Leave a trail.** Changelog plus the why, so the next deploy and the on-call after you start informed.

## How to adopt

Drop this file in your repo root next to `AGENTS.md` and `SOUL.md`, then trim it to your service.
