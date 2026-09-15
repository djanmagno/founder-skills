---
name: founder-mvp
description: Define the smallest useful experiment for a bootstrapped B2B SaaS and specify only the product changes that hypothesis actually requires — engineering last, not first. Use this when the founder asks "what should we build," "is this the MVP," "can we concierge this," or is about to write tickets for a full product. Do not use it to discover the customer/problem (founder-validate), to map what already exists (founder-product-audit), or to treat a shipped feature as commercial validation (founder-review). Never auto-invoke Matt's to-spec or to-tickets; those are explicit-invocation skills — prepare the call for the founder.
---

## What this skill does

Names the smallest useful experiment that can move an evidence tier, and the smallest product (or non-product) change that experiment needs. Interviews, a landing ask, a concierge delivery, or a manual workaround beat a build when they can test the same hypothesis. If engineering is required, this skill writes a handoff with technical acceptance criteria **and** a commercial metric — then stops. Technical delivery is not commercial validation.

## When to use it / when not to

Use it when a hypothesis exists and the founder is choosing what to build, shrink, or skip. Use it for partial prototype needing adjustments when the adjustment is in service of a commercial test. Do not use it as a product-roadmap workshop. Do not use it to skip `founder-validate` on an idea with no customer/problem hypothesis. Do not use it to close an experiment after merge — that is `founder-review`. Do not use it to launch (`founder-launch`) or to prospect (`founder-first-customers`).

## Minimum required context

The hypothesis and current evidence from `.founder/context.md` and `.founder/experiments.md`. Product map if `.founder/product-map.md` exists — do not rebuild what is already verified. If the hypothesis is missing, route to `founder-validate` or `founder-start` instead of inventing a build. If the evidence includes people or accounts who did **not** convert or renew alongside the ones who did, treat that gap as a data point worth a quick look before scoping — silence on why some didn't stick is easy to drop when the founder's own framing only mentions the wins.

## Procedure

1. **State the hypothesis and the next evidence tier.** What would have to be true, and which tier would move (stated intent → commitment → payment → recurring use)? If that sentence cannot be written, this is not an MVP problem.

2. **Ask whether any engineering is required.** Prefer, in order, anything that tests the hypothesis sooner:
   - A conversation or a written offer.
   - Manual / concierge delivery (problem validated through manual delivery is a reason to keep delivering manually, not to rebuild first).
   - A fake-door or waitlist only if it is scored as stated intent, never as payment.
   - The smallest product change that unblocks the test.

   Do not turn a commercial task into engineering because building is comfortable. Do not recommend a rebuild because traction was weak.

3. **If a product change is required, shrink it to the experiment.** Scope is the capabilities the named user must touch to complete the test. Everything else is out. Use the product map's three states: don't re-implement the implemented; don't treat hypothesis screens as done.

4. **Log the commercial experiment first** in `.founder/experiments.md`:

   ```markdown
   ## <short experiment name> — <date started>

   **Status:** running

   **Hypothesis:** falsifiable commercial claim this MVP exists to test.

   **Action:** concierge / small product change / both — specific enough that "did we do this" is answerable.

   **Owner:** ...

   **Cost:** time and money, including engineering if any.

   **Metric:** the commercial number (commitments, payments, recurring use) — not "feature shipped."

   **Observation window:** starts when the experiment can be shown to a real buyer/user, not when the PR merges.

   **Evidence:** window still open.

   **Decision:** (empty until founder-review)
   ```

   Status stays **running** after the build. Shipping closes technical acceptance only.

5. **If engineering is in scope, write an outbound handoff** (a short-lived note in `.founder/` or pasted into chat). Do not copy technical docs into it:

   ```markdown
   ## Handoff: <short title> — <date>

   **Problem, customer, evidence:** from `.founder/context.md` — not invented for this handoff.

   **Commercial hypothesis and expected result:** the experiment-log entry this serves.

   **Requested change, scope, constraints:** what to build/fix; what is out of scope. Current authorization for spend, publishing, or production.

   **Technical acceptance criteria:** how we know the *technical* work is done.

   **Commercial metric and observation window:** what founder-review will read; shipping does not conclude this.

   **References:** links only.
   ```

6. **Honor explicit-invocation engineering skills.** If Matt Pocock Skills' `to-spec` and/or `to-tickets` are installed, **do not invoke them**. Prepare the handoff and tell the founder the exact call to make. Read the installed skill before describing it; names and effects vary by version. If Superpowers `writing-plans` is the chosen flow, one owner for planning — do not also run Matt planning. If no complements, the handoff *is* the spec: the founder or this agent implements only what it lists, within authorization.

7. **Production and publishing stay gated.** Do not deploy, publish, or spend beyond `.founder/context.md` **Authorizations**. gstack `ship` includes commit/push/PR; production deploy is a distinct, authorized action. Neither is commercial validation.

8. **When work comes back, do not conclude.** Point the inbound note at `founder-review`:

   ```markdown
   ## Handoff result: <short title> — <date>

   **Changes made:** ...
   **Verification evidence:** ...
   **Open items:** ...
   **Links:** spec, tickets, diffs, tests, deploy/PR.
   ```

## Deliverables

- A smallest-experiment decision: build / concierge / conversation, with why the others are larger than needed.
- An experiment-log entry whose metric is commercial, not "shipped."
- An outbound handoff when engineering is required — plus a prepared (not auto-invoked) `to-spec` / `to-tickets` call when those skills are present.
- A named next step: implement within authorization, wait on the founder to invoke a complement, or go to `founder-first-customers` / `founder-validate` if no build was required.

## Judging results / routing the next action

Success: the founder can see why this is the smallest test, and a ship cannot be mistaken for a win. Failure: a roadmap, auto-invoked `to-spec` / `to-tickets`, a rebuild for taste or lack of traction, or an experiment marked concluded because CI passed.

Route:
- No engineering needed → `founder-validate` or `founder-first-customers` (authorization required for outreach).
- Engineering in flight → execute via the chosen complement or the self-contained handoff; then `founder-review`.
- Technical criteria met, commercial window open → observe, then `founder-review`.
- Launch to an audience → `founder-launch`, still not validation by itself.

## Working with no complements installed

The handoff is the whole engineering brief. Implement only if the founder authorized that work in this session; otherwise leave a usable spec. Missing `to-spec` is not a blocker. Missing a design process is not a reason to enlarge the MVP.

## Complement integration

Connection points, used only when detected, with **one owner per step**:

- Matt: `to-spec` / `to-tickets` — **explicit invocation**; prepare the call, do not fire it. `implement` / `tdd` / `code-review` only if that is already the project's flow.
- Superpowers: `brainstorming` for still-open technical design; `writing-plans` and the environment's executor for the change; `test-driven-development` / `verification-before-completion` as that flow requires. Do not skip required steps of the chosen package.
- gstack: `plan-eng-review` (and `plan-design-review` / `plan-devex-review` when they evaluate a different question); `ship` / `land-and-deploy` / `canary` only with publishing/production authorization.

Never install, update, or modify those packages. Load `docs/integration/` guides only when the matching package is present. Do not run three equivalent planning passes.
