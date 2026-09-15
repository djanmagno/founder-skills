# Integration guide: Superpowers (optional complement)

This guide is loaded **only when Superpowers is detected in the environment**. founder-skills works fully without it. Never install, update, or modify that package from here.

## When to use Superpowers

From the connection-point table in `docs/PLAN.md` §4, this package covers three rows — and only these rows:

| Need | Integration |
|---|---|
| Resolve still-open technical design | Superpowers: `brainstorming` |
| Plan and implement a change | Superpowers: `writing-plans` and the executor appropriate to the environment |
| Investigate failures and verify results | Superpowers: `systematic-debugging`, `test-driven-development`, review, `verification-before-completion` |

In practice:

- **Open design questions** (`founder-mvp`, `founder-product-audit`): use `brainstorming` when the technical shape is genuinely unresolved and needs structured exploration before planning.
- **Planning and building**: hand commercial context to `writing-plans`, which produces the technical plan **in its own format**. founder-skills does not duplicate that planning step and does not pre-write the plan for it — the handoff carries the commercial context, Superpowers owns the plan shape.
- **Failure investigation and verification**: use `systematic-debugging` for live failures, `test-driven-development` as the testing discipline when Superpowers owns execution, and review / `verification-before-completion` as the verification gate before work comes back.

## What NOT to do

- Don't duplicate Superpowers' planning inside founder-skills. The outbound handoff states the problem, scope, constraints, and acceptance criteria; the plan itself is Superpowers' output, in Superpowers' format. Writing a second plan in `.founder/` creates divergent copies — link to the plan instead.
- Don't use Superpowers skills for commercial reasoning — demand evidence, pricing, retention, and pivot decisions stay in founder-skills.
- Don't run two planning passes or two debugging passes for the same change. **One owner per step**: if Superpowers owns the plan, no Matt spec pass and no extra design review covers the same question.
- Don't treat a verified build (tests green, verification checklist passed) as commercial validation. It closes technical acceptance criteria; the commercial experiment in `.founder/experiments.md` stays running until its metric is observed over its window.

## Commercial context in, technical plan out

The division of labor is strict and one-directional per handoff:

1. founder-skills sends **commercial context**: problem, customer, evidence, commercial hypothesis and expected result, requested change with scope and constraints, current authorization, technical acceptance criteria, commercial metric and observation window, and links to existing docs (see `templates/handoff.md`). No technical plan, no implementation instructions.
2. Superpowers returns a **technical plan in its own format**, then executed work with verification evidence.
3. The inbound handoff (changes made, verification evidence, open items, links) is recorded via `founder-review`. Commercial judgment resumes there.

Respect any explicit-invocation or authorization restrictions on the installed Superpowers skills: prepare context and name the call for the user where required rather than invoking automatically.

## One owner per step

When equivalent capabilities exist across installed packages, choose **one** owner per step and say which:

- One design process per change (`brainstorming` **or** a gstack design review — never both for the same question).
- One executor per change (the Superpowers executor appropriate to the environment **or** Matt `implement` — never both).
- One testing discipline per change (`test-driven-development` **or** Matt `tdd` — never both).
- Extra reviews only when they evaluate genuinely distinct questions.

Record the choice in the handoff so the next session doesn't re-litigate it.

## Practical notes

- Resolve skill names from the real install, including any namespaces — names and effects vary by version. Read the installed skill before invoking it.
- Don't skip required steps of the chosen Superpowers flow once selected. If a tool is missing, continue with what's available or produce a usable work handoff.
- Record the consulted version or commit of the Superpowers package in the handoff or in `docs/SOURCES.md` so later sessions know what was actually used.
