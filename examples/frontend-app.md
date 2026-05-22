# FLYWHEEL.md

> Example for a frontend or web app. Adapt the stages and gates to your process. The full idea: [flywheel.md](https://flywheel.md).

**How an agent ships and improves this app, turn by turn.** `AGENTS.md` says what to do, `SOUL.md` says who to be, `FLYWHEEL.md` says how a change travels from idea to deployed to improved.

## The loop

1. **Plan.** Scope the change. Does it touch a critical user flow?
2. **Build.** Implement, watching bundle size and request count as you go.
3. **Review.** Type-check, tests, and the performance budget (bundle, requests, web vitals).
4. **Preview.** Deploy a preview build.
   - *Gate (human):* a person looks at the preview and signs off on the look and feel. UX is judgment, not a test.
5. **Ship.** Deploy to production.
6. **Verify.** Open the real page, walk the golden path in a browser, screenshot it; check your target browsers.
   - *Done when:* you have seen the feature work in a real browser, not just a passing unit test.
7. **Learn.** Real-user monitoring: errors, web vitals, drop-off.
8. **Improve.** Fix the cause. No `!important` or arbitrary timeout to mask a race or layout bug.

## Humans in the loop

Frontends are the most human-gated archetype: the **visual review at Preview**. A test cannot tell you it looks right, so pause there for a human.

## The bar (every stage)

- Done means verified in a real browser, with a screenshot.
- No regressions on the golden path.
- Respect the performance budget; stay accessible and cross-browser.
- Leave a trail.

## How to adopt

Drop this in your repo root next to `AGENTS.md` and `SOUL.md`, then tune the stages and gates to your app.
