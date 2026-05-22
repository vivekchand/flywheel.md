# Contributing to FLYWHEEL.md

FLYWHEEL.md is an open standard for how autonomous agents (and the humans who run them) ship and improve software. Contributions are welcome.

And yes, we run this repo by its own rules: `main` is protected, every change ships through a pull request, and "done" means verified, not merged.

## Ways to contribute

- **New example archetypes.** Add a `FLYWHEEL.md` for a project type we do not cover yet (mobile app, game, data pipeline, infra / IaC, monorepo, browser extension, ...) under `examples/`. Each example should show that archetype's own loop: stages, done-when, and where a human gates it.
- **Sharpen the manifesto or the site.** Clearer stages, better gates, tighter copy.
- **Translations.** Open a PR with `FLYWHEEL.<lang>.md`.
- **Fixes.** Typos, broken links, site bugs.

## How

1. For anything non-trivial, open an issue first so we can align before you build. Look for issues labelled `good first issue`.
2. Fork the repo, create a branch, make the change.
3. Open a pull request and fill in the template. Keep it focused on one thing.
4. A maintainer reviews and merges. Direct pushes to `main` are off; that is on purpose.

## The bar

The same one the manifesto preaches:

- Keep user-facing copy (site, README, manifesto) free of em dashes; use periods, commas, or colons.
- Verify it actually renders before you say done, do not stop at "it builds."
- Leave a trail: a PR description that explains the why.

Be kind. This is a small, friendly project trying to make agentic development safer.
