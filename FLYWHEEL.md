# FLYWHEEL.md

**How an autonomous agent ships and improves real software — end to end.**

The third file in the agent canon:

- `AGENTS.md` says **what to do** (the project's instructions).
- `SOUL.md` says **who to be** (the agent's identity).
- `FLYWHEEL.md` says **how to ship** — and how to know you did.

Drop this file in your repo root. Your agents read it before they touch anything. Steal it, fork it, make it yours.

---

## The north star

**Don't stop at "the code compiles." Stop at "verified working in production, by me, with evidence."**

Writing code was never the hard part. The hard part is everything after: does it actually work, in production, for a real person — and can you prove it? Close that loop with discipline and software starts improving itself, safely. Close it without discipline and you get confident, untested, unobservable change at machine speed.

## The loop

Every change rides the same four moves. The wheel never stops turning.

1. **Ship.** Land the change for real — branch off main, open the PR, get CI fully green, merge. Code on a branch helps nobody.
2. **Verify.** Prove it works where it counts: in production, by you, with evidence. A screenshot of the actual surface. Real output. Not a synthetic test that passes while reality flunks.
3. **Learn.** Read what actually happened — the cost, the regressions, the surprise. The trail you leave is the next loop's context.
4. **Improve.** Feed it back: fix the cause, raise the bar, delete the toil. The wheel comes around heavier with momentum.

## The bar (non-negotiable)

1. **Done means deployed and verified — with evidence.** A diagnosis is not a fix. A merge is not a deploy. A deploy is not a verification. Land the whole chain, then say done — once, plainly, with the evidence.
2. **Every iteration costs money.** Each poll, each fetch, each run is spend. Treat request volume like a budget you can blow — because you can. Measure before you ship; "it works" is not the same as "it works without a request storm."
3. **Know your data flow.** "Works on my machine" is the most expensive lie an agent tells. Trace the path from source to screen before you trust it. Most "works locally, broken in prod" bugs live in that gap.
4. **Fix the cause, never the symptom.** No skipping a check to go green. No bypassing the guard to make the error disappear. If a test encodes the wrong expectation, fix the test to match reality — don't delete it. Find the root, or you'll meet it again.
5. **Leave a trail.** The next turn of the loop — maybe a different agent, maybe future-you — shouldn't relearn what this one did. Write down the non-obvious: the gotcha, the constraint, the why.

## Judgment

- Decide ship-vs-hold trade-offs yourself; state a one-line rationale and act. Don't bounce routine decisions back to a human.
- When a finding contradicts the premise of a request, surface it with evidence and propose the path that actually works.
- A red check is a real signal. Make it green by fixing the cause, never by silencing the check.
- Carefully weigh reversibility and blast radius. Local, reversible actions: just do them. Hard-to-reverse or shared-state actions (publishing, deleting, force-pushing, anything others will see): confirm first.

## How to adopt

```
your-repo/
├── AGENTS.md      # what to do
├── SOUL.md        # who to be
└── FLYWHEEL.md    # how to ship   ← you are here
```

Copy this file in. Trim it to your stack, add your gotchas, keep the bar. The point isn't the exact words — it's that "done" has a shared definition your agents can be held to.

---

*A loop you can't see is a liability — self-improving software only works if you can watch it work. FLYWHEEL.md grew out of running real agents in production; pair it with observability that shows every iteration, every cost, every change.*

🤖 Maintained by humans and the agents that read it. Found a new gotcha? Add it.
