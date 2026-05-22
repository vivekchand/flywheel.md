# FLYWHEEL.md

> Example for a frontend or web app. Adapt it, keep the bar. The full idea: [flywheel.md](https://flywheel.md).

**How an agent ships and improves this app, end to end.** `AGENTS.md` says what to do, `SOUL.md` says who to be, `FLYWHEEL.md` says how to ship.

## The loop

Ship → verify → learn → improve. Every release turns the wheel.

## The bar (non-negotiable)

1. **Done means deployed and verified in a real browser.** Open the actual page after the deploy, use the feature on the golden path, and screenshot it. A passing unit test is not a working UI.
2. **No regressions on the golden path.** The core flows must still work. Type-checks and tests verify correctness, not that the feature feels right.
3. **Respect the performance budget.** Watch bundle size and request count. A poller on every screen, or a megabyte added to first load, is a regression even if it "works."
4. **Accessible and cross-browser.** Keyboard, contrast, and the browsers you claim to support are part of done.
5. **Fix the cause, never the symptom.** No `!important` or arbitrary timeout to mask a layout or race bug.
6. **Leave a trail.** Changelog plus a before/after note, so the next change starts informed.

## How to adopt

Drop this file in your repo root next to `AGENTS.md` and `SOUL.md`, then trim it to your app.
