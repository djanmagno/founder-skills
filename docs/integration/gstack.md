# Integration guide: gstack (optional complement)

This guide is loaded **only when gstack is detected in the environment**. founder-skills works fully without it. Never install, update, or modify that package from here.

## When to use gstack

From the connection-point table in `docs/PLAN.md` §4, this package covers four rows — and only these rows:

| Need | Integration |
|---|---|
| Challenge a material strategic decision | gstack: `office-hours` or `plan-ceo-review` |
| Review engineering, experience, or design | gstack: `plan-eng-review`, `plan-design-review`; `plan-devex-review` when the product serves developers |
| Investigate the live product experience | gstack: `browse`, `qa-only`; `qa` when fixes are in scope |
| Prepare technical delivery and verify production | gstack: `ship`, `land-and-deploy`, `canary`, per authorization and project flow |

In practice:

- **Strategic challenge** (`founder-pivot`, `founder-economics`, `founder-growth`): use `office-hours` or `plan-ceo-review` to stress-test a material decision — after the founder-skills comparison, numbers, or options are written, so the session reacts to evidence rather than replacing the analysis.
- **Reviews** (`founder-mvp`, `founder-product-audit`): use `plan-eng-review` / `plan-design-review` (and `plan-devex-review` for developer-facing products) when the question is genuinely engineering, experience, or design quality — each review only when it evaluates a distinct question.
- **Live investigation** (`founder-activation`, `founder-retention`): use `browse` / `qa-only` to see what users actually experience.
- **Delivery** (`founder-mvp` and its handoffs): use `ship`, `land-and-deploy`, `canary` within authorized scope and the project's own flow.

## What NOT to do

- Don't use gstack for commercial reasoning — demand evidence, pricing, retention reads, and the persist/pivot call stay in founder-skills. `office-hours` challenges a written decision; it doesn't make it.
- Don't stack gstack reviews on top of equivalent Matt or Superpowers passes for the same question. **One owner per step**; extra reviews only for genuinely distinct questions.
- Don't let delivery close the commercial loop. A shipped, deployed, canaried change closes technical acceptance criteria; the commercial experiment in `.founder/experiments.md` stays running until its metric is observed over its window. **A shipped feature is never itself commercial validation.**
- Don't publish, contact, spend, or touch production on assumed consent. Every one of those respects current authorization in `.founder/context.md` and the project's flow.

## Precise distinctions (do not collapse)

These come from the verified sources in `docs/PLAN.md` §4. Getting them wrong causes unauthorized commits or unapproved production changes:

- **`qa-only` produces a report only.** It investigates and reports; it does not fix, commit, or change the product. Use it when fixes are out of scope or not yet authorized.
- **`qa` may fix and create commits.** Invoke it only when fixes are explicitly in scope and commit authorization exists.
- **`ship` includes commits, push, and PR creation.** It is a delivery action with version-control side effects — authorized explicitly, within the project's flow.
- **A production deploy is a separate, distinct action requiring its own authorization.** `ship` (or `land-and-deploy` / `canary`) preparing or creating delivery artifacts is not deploy consent. Name the deploy, get explicit approval, then proceed per the project flow.

Never claim approvals, verifications, or deploys that didn't happen. Diagnosis, correction, and publication are three different events; record each where it actually occurred.

## One owner per step

When equivalent capabilities exist across installed packages, choose **one** owner per step and say which:

- One strategic challenger per decision (`office-hours` **or** `plan-ceo-review` — never both).
- One review per distinct question (a gstack plan review **or** Matt `code-review` / Superpowers review for the same question — never both).
- One delivery path per change, following the project flow (the flow defined by the project wins over any package default).

Record the choice in the handoff so the next session doesn't re-litigate it. Also record `retro` output as input to `founder-review` — engineering-execution notes inform the review; they are not a commercial conclusion.

## Practical notes

- Resolve skill names from the real install, including any namespaces — names and effects vary by version. Read the installed skill before invoking it.
- Don't skip required steps of the chosen gstack flow once selected. If a tool is missing, continue with what's available or produce a usable work handoff.
- Record the consulted version or commit of the gstack package in the handoff or in `docs/SOURCES.md` so later sessions know what was actually used.
