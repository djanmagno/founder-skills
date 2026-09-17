---
name: founder-product-audit
description: Map what a founder's product actually does — implemented flows, verified behavior, and commercial hypotheses — by inspecting the code, live product, or manual delivery when any of those exist, and name technical blockers only when they obstruct a business experiment. Use this whenever a founder describes an existing prototype or shipped product and asks what to focus on next, even if they've already summarized what's built in their own words — a founder's summary is not a classification into implemented/verified/hypothesis, and this skill is what produces that classification before any other skill acts on it. Also use it for direct asks like "what's actually built," "audit the product," or "should we rebuild." Do not use it to validate demand or talk to customers (founder-validate), to design the smallest next experiment (founder-mvp), or to diagnose why users drop off after signup (founder-activation).
---

## What this skill does

Produces a product map of what exists today: the user/buyer flows, the capabilities behind them, and — for each — whether it is implemented, verified to work, or still a commercial hypothesis wearing a feature's clothes. If code is present, it inspects the code. Technical blockers are listed only when they stop a named business experiment, not because the stack is unfashionable.

## When to use it / when not to

Use it when something already exists (partial prototype, shipped product, or a real concierge process that *is* the product) and the next decision depends on knowing what is real. Do not use it on an idea with no product — that is `founder-validate`. Do not use it to choose the smallest experiment or to write the engineering change; map the product, then hand the experiment to `founder-mvp`. Do not treat "the code is messy" as a reason to run this skill, or as a reason to rebuild.

## Minimum required context

Enough to find the product: a repo, a URL, screenshots, docs, or a description of the manual delivery. If `.founder/context.md` exists, read it first — especially **What exists**, **Who**, and **Evidence**. If those sections are empty, ask; do not invent a user, a flow, or a usage number to fill the map.

## Procedure

1. **Reuse context; don't restart diagnosis.** If `.founder/context.md` is missing or the situation is still unnamed, say so and send the founder to `founder-start` — or gather only the missing facts and continue. Do not re-run a full business diagnosis here.

2. **Locate the product without assuming a stack.** Find whatever actually delivers the thing: source code, a deployed app, a no-code tool, a spreadsheet plus inbox, a concierge service. Do not assume GitHub, analytics, tests, or a particular framework. If nothing locatable exists, stop and route to `founder-validate` — there is no product to audit.

3. **Map flows and capabilities from evidence, not from the pitch.** Walk the path a user and (if different) a buyer would take: discover → start → first value → pay → come back. For each step, list the capability that is supposed to make it work. If you cannot walk a step, mark it unknown — do not complete the map from the README or the founder's slide.

4. **Classify every capability into exactly one of three states.** Keep these separate; never collapse them:
   - **Implemented** — the code, config, or manual process exists.
   - **Verified** — someone has actually exercised it (a test, a founder walkthrough with a recorded result, or a real user doing the step). Implementation is not verification.
   - **Hypothesis** — the capability is supposed to produce a commercial outcome (demand, conversion, retention) that has not been observed. A shipped screen with no usage evidence stays a hypothesis.

   Signups, feature count, and "it works on my machine" do not move a hypothesis into verified commercial territory.

5. **Inspect code when it is present.** Read the entry points, routes, jobs, and data model far enough to confirm or correct the map. Distinguish dead UI, unfinished branches, and env-gated features from what a real user can hit. If the codebase is large, scope the inspection to the flows that matter for the current obstacle; say what you did not read.

6. **Name technical blockers only when they are tied to the business.** A blocker is something that prevents the next commercial experiment or the named customer from getting the promised value (cannot onboard, cannot take payment, cannot deliver the job, data loss, cannot observe the metric). Code quality, stack taste, missing abstractions, and "we should rewrite" are not blockers unless they actually stop that experiment. Do not recommend a rebuild because the product lacked traction.

7. **Persist the map.** Create or update `.founder/product-map.md` (or the founder's existing equivalent) with:

   ```markdown
   # Product map

   Last updated: <date>
   Situation(s): <from the shared vocabulary — e.g. partial prototype needing adjustments / ready product with no commercial validation>

   ## How to find it
   <repo, URL, manual process — links only>

   ## Flows
   For each flow (user and buyer if different):
   - Step:
   - Capability:
   - State: implemented / verified / hypothesis
   - Evidence for that state: <what was actually seen — or "none yet">

   ## Capabilities outside a flow
   <admin, billing, integrations, jobs — same three-state classification>

   ## Business-linked technical blockers
   - Blocker:
   - Which commercial experiment or customer job it stops:
   - What is *not* a blocker: <taste items left out of this list on purpose>

   ## Unknowns
   <what was not inspected>
   ```

   Update `.founder/context.md` **What exists** so it matches the map. Do not copy the codebase into `.founder/`.

8. **Route.** One next skill, with why. Typical: no demand evidence → `founder-validate`; offer unclear → `founder-positioning`; the next test needs a product change → `founder-mvp`; users exist but stall after signup → `founder-activation`. Do not stay here to start building.

## Deliverables

- `.founder/product-map.md` (or equivalent), with every capability in one of the three states.
- Business-linked technical blockers, or an explicit statement that there are none.
- Updated **What exists** in `.founder/context.md` when the classification changed.
- A named next skill.

## Judging results / routing the next action

The audit worked if the founder can point at the map and see what is real versus assumed, and if every blocker names the business experiment it stops. It failed if the map is a feature list from marketing copy, if "verified" was granted without a walkthrough or test, or if the recommendation is a rebuild justified by taste or by lack of traction.

A completed audit is not commercial validation. Route to `founder-validate` when demand evidence is still at stated intent or empty; to `founder-mvp` only for the smallest change the next experiment actually requires.

## Working with no complements installed

Inspect the code, the live product, and the docs with whatever is already in the workspace. Write the map by hand. Missing analytics, test suites, or browser tooling is not a reason to skip the audit — walk what you can, mark the rest unknown.

## Complement integration

If complements are detected, use them only to inspect, not to start a rebuild:

- Matt Pocock Skills: `domain-modeling` / `codebase-design` when the domain boundaries are genuinely unclear. Read the installed skill first. One owner for discovery — do not also run an equivalent Superpowers pass.
- gstack: `browse` or `qa-only` to walk the live product. `qa-only` reports; `qa` may fix and commit — do not run `qa` unless fixes are in scope and authorized. Do not run `ship` from an audit.
- Superpowers: `systematic-debugging` only for a specific failure that is blocking the map, not as a general tour.

Never install those packages. Never invoke Matt's `to-spec` / `to-tickets` from this skill — if the map implies an engineering change, prepare a handoff and let the founder invoke those skills, usually via `founder-mvp`. Load `docs/integration/` guides only when the matching package is present.
