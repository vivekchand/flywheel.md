# FLYWHEEL.md

**Your project's loop for shipping and improving software, with humans in the loop where it matters.**

A companion to `AGENTS.md`: it says what to do, `SOUL.md` (if you use one) says who to be, `FLYWHEEL.md` says how a change travels from idea to shipped to improved, turn after turn.

## What a flywheel is

A flywheel is a loop a change travels again and again. Each turn it moves through your stages, pauses where a human needs to weigh in, ships, and feeds what it learned into the next turn. The point is momentum that compounds: every turn makes the next one faster and safer.

This file is where you define that loop, so an agent follows your *process*, not just your goal. It is not a "definition of done" checklist. It is the shape of how you build, release, and evolve.

Why now: when agents write the code, coding stops being the bottleneck. Verification, review, and ownership become it, and the processes built to protect scarce engineering time quietly stop working. This file is where you rewrite them.

## The stages

A change flows through four stages, the same four the wheel turns. The set below is the default. Split a stage (Ship is really plan, build, and review), add, remove, or reorder to match how your project actually ships and evolves. For each stage, write two things:

- **Done when:** the exit criteria, so the agent knows when to move on.
- **Gate:** does the agent proceed on its own, or stop and wait for a human?

1. **Ship.** Plan the approach and name the blast radius, build in small reversible steps, review your own diff, tests, and data flow, then merge, release, and deploy. Land the whole chain, not just the merge.
   - *Done when:* the change is live where users are.
   - *Gate (human):* sign off before anything risky or irreversible, and optionally review before merge.
2. **Verify.** Prove it works in production, by you, with evidence: a real request, a screenshot, real output.
   - *Done when:* you have seen it work for real. A passing test is not proof.
3. **Learn.** Capture what actually happened: cost, regressions, the surprise, user feedback.
   - *Gate (often):* wait for real-world signal before starting the next turn.
4. **Improve.** Feed it back: fix the cause, raise the bar, delete the toil.
   - *Done when:* the next turn starts smarter than this one did.

## Humans stay in the loop

A flywheel is not "let the agent run unattended forever." It makes explicit *where* a human stays in the loop: which stages need a sign-off, and where the agent pauses for feedback and resumes when you reply. Mark those gates. Put them where human judgment still wins: risk and trust boundaries, irreversible changes, legal, and product taste. Everything between them, the agent turns on its own. Loosen the gates as trust grows; tighten them for risky surfaces.

## What makes it compound

The difference between a flywheel and a checklist: **Learn** feeds the next **turn**. Cost data, regressions, and feedback become the context that makes the next change faster and safer. Leave a trail so the wheel comes around heavier each turn.

## The bar (holds at every stage)

A few rules that do not change between stages, whatever stages you choose:

- Done means deployed and verified, with evidence.
- Every iteration costs money.
- Know your data flow.
- Fix the cause, never the symptom.
- Leave a trail, in the codebase, where it stays in the loop. A doc outside the loop rots.
- Audit the loop itself. Processes pile up and nobody deletes them; every few turns, ask of each stage and gate whether it still earns its place, and cut what does not.

## Make it yours

```
your-repo/
├── AGENTS.md      # what to do
├── SOUL.md        # who to be
└── FLYWHEEL.md    # how you ship and evolve, turn by turn
```

Copy this in, then rewrite the stages and gates for your project. A CLI, a model, and a web service have different loops and different human gates. The point is a shared, explicit process your agents and your team can both follow, not these exact words.

---

*A loop you cannot see is a liability. FLYWHEEL.md grew out of running real agents in production; pair it with observability that shows every turn.*

🤖 Maintained by humans and the agents that read it.
