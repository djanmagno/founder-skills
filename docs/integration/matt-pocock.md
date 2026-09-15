# Integration guide: Matt Pocock Skills (optional complement)

This guide is loaded **only when Matt Pocock Skills are detected in the environment**. founder-skills works fully without them. Never install, update, or modify that package from here.

## When to use Matt Pocock Skills

From the connection-point table in `docs/PLAN.md` §4, this package covers three rows — and only these rows:

| Need | Integration |
|---|---|
| Understand domain and code boundaries | Matt: `domain-modeling`, `codebase-design` |
| Turn a commercial change into spec and tickets | Matt: `to-spec`, `to-tickets` (explicit invocation) |
| Execute via the Matt process already adopted | Matt: `implement`, `tdd`, `code-review` |

In practice:

- **Before building** (`founder-product-audit`, `founder-mvp`): use `domain-modeling` / `codebase-design` when the commercial question needs a real read of domain boundaries or code structure — e.g. scoping what a product change touches. Reuse whatever those skills discover; don't re-run discovery founder-skills already did.
- **Turning a commercial decision into buildable work** (`founder-mvp`, `founder-product-audit`): use `to-spec` / `to-tickets` to convert the handoff into a spec and tickets in Matt's format.
- **Building inside an adopted Matt flow**: if the project already uses Matt's `implement` / `tdd` / `code-review` process, execute inside it rather than inventing a parallel one.

## What NOT to do

- Don't use Matt skills for commercial reasoning — customer hypotheses, pricing, positioning, retention reads, and pivot decisions stay in founder-skills.
- Don't run Matt discovery when founder-skills already recorded the answer. Reuse `.founder/context.md` and prior findings; one discovery per question.
- Don't stack Matt planning on top of a Superpowers plan or a gstack review for the same change. **One owner per step**: if Matt's flow owns implementation for this change, it also owns its TDD discipline and its code review.
- Don't treat Matt's output (spec, tickets, merged code, passing tests) as commercial validation. Technical delivery closes technical acceptance criteria; the commercial experiment in `.founder/experiments.md` stays running until its metric is observed over its window.

## Explicit invocation is mandatory for `to-spec` / `to-tickets`

`to-spec` and `to-tickets` carry `disable-model-invocation: true`: the model **must never invoke them automatically**. When a founder-skills skill reaches the point of needing a spec or tickets:

1. Prepare the outbound handoff (problem, customer, evidence, commercial hypothesis, scope, constraints, authorization, technical acceptance criteria, commercial metric and window, references — see `templates/handoff.md`).
2. Name the exact call for the user (e.g. "run `to-spec` on this handoff") and hand them the prepared context.
3. Wait. The user invokes it; the result comes back as an inbound handoff and is recorded via `founder-review`.

Auto-invoking these skills — or silently folding "spec writing" into founder-skills' own output to dodge the restriction — violates the package's invocation contract and this library's authorization rules.

## One owner per step

When equivalent capabilities exist across installed packages, choose **one** owner per step and say which:

- One executor per change (Matt `implement` **or** the Superpowers executor appropriate to the environment — never both).
- One testing discipline per change (Matt `tdd` **or** Superpowers `test-driven-development` — never both).
- One review per distinct question (Matt `code-review` for code correctness **or** a gstack plan review for strategy/design — extra reviews only when they evaluate genuinely different questions).

Record the choice in the handoff so the next session doesn't re-litigate it.

## Practical notes

- Resolve skill names from the real install, including any namespaces — names and effects vary by version. Read the installed skill before invoking (or preparing) it.
- Don't skip required steps of the Matt flow once chosen. If a required tool is missing, continue with what's available or produce a usable work handoff rather than a half-run process.
- Record the consulted version or commit of the Matt package in the handoff or in `docs/SOURCES.md` so later sessions know what was actually used.
