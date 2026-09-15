Reading additional input from stdin...
OpenAI Codex v0.154.0
--------
workdir: /private/tmp/eval-runs-codex/E02
model: gpt-6-astra
provider: openai
approval: never
sandbox: workspace-write [workdir, /tmp, $TMPDIR]
reasoning effort: low
reasoning summaries: none
session id: 01a0a740-6181-7841-a072-4f9713a74232
--------
user
I've been doing invoice reconciliation by hand for 6 trucking companies as a paid service — $400/month each, no software, just me in spreadsheets. 4 of them have paid me 3 months in a row now. I'm burned out doing this manually and I think it's proof I should build the real SaaS product now. Where do I start on the build?
warning: Skill descriptions were shortened to fit the skills context budget. Codex can still see every skill, but some descriptions are shorter. Disable unused skills or plugins to leave more room for the rest.
hook: SessionStart
hook: SessionStart Completed
hook: UserPromptSubmit
hook: UserPromptSubmit Completed
codex
I’ll check the relevant planning skill, then use your paid-service experience to identify what’s worth building first.
hook: PreToolUse
hook: PreToolUse Completed
exec
/bin/zsh -lc 'rg --files skills | head -80' in /private/tmp/eval-runs-codex/E02
 succeeded in 0ms:
skills/founder-validate/SKILL.md
skills/founder-pricing/SKILL.md
skills/founder-growth/SKILL.md
skills/founder-economics/SKILL.md
skills/founder-review/SKILL.md
skills/founder-first-customers/SKILL.md
skills/founder-mvp/SKILL.md
skills/founder-activation/SKILL.md
skills/founder-launch/SKILL.md
skills/founder-start/SKILL.md
skills/founder-retention/SKILL.md
skills/founder-pivot/SKILL.md
skills/founder-positioning/SKILL.md
skills/founder-product-audit/SKILL.md

hook: PostToolUse
hook: PostToolUse
hook: PostToolUse Completed
hook: PostToolUse Completed
hook: PreToolUse
hook: PreToolUse Completed
exec
/bin/zsh -lc "for f in skills/*/SKILL.md; do sed -n '1,12p' \""'$f"; done' in /private/tmp/eval-runs-codex/E02
 succeeded in 0ms:
---
name: founder-activation
description: Define a new user's first value moment for a bootstrapped B2B SaaS, diagnose where early users drop off, and fix onboarding so more of them reach that value. Use this when signups or trials don't turn into active users, when the founder asks "why do people sign up and disappear," "how do we improve onboarding," or "what is our aha moment." Do not use it for pricing and packaging (founder-pricing), for keeping paying customers over months and expanding accounts (founder-retention), or for getting more visitors in the door (founder-growth) — activation is about users who already arrived reaching first value, not about acquiring more of them.
---

## What this skill does

Names the single first value a new user must experience, finds the step where most of them abandon before reaching it, and runs a small experiment to remove or shrink that drop-off. It works on users who already signed up — free, trial, or newly paying — and it stops once first value is consistently reached. Everything after that (renewal, expansion, long-term habit) belongs to `founder-retention`.

## When to use it / when not to

Use it for: free users with no conversion, trial users who go quiet, new paying customers who never really start using the product, or any "published product with interest but no active use" pattern.
---
name: founder-economics
description: Model unit economics and cash constraints for a bootstrapped B2B SaaS — recurring revenue, one-off revenue, pipeline, and cash as four distinct numbers, plus margin and customer concentration risk. Use this when the founder asks "are we sustainable," "can we afford this," "what does our revenue actually look like," or when growth is limited by margin, support load, or dependence on one or two customers. Do not use it to set packaging or test willingness to pay (founder-pricing), to choose acquisition channels (founder-growth), or to record shipped code as commercial progress (founder-review) — a completed build is never itself commercial validation, and revenue is never recognized here until money and renewal reality say so.
---

## What this skill does

Produces an honest money picture a solo founder can decide from: what recurs, what was one-off, what is merely pipeline, and what cash is actually available — plus what each customer really costs to serve and what happens if the biggest one leaves. It stops founders from spending pipeline, from calling project fees ARR, and from discovering concentration risk the month the big account pauses.

## When to use it / when not to

Use it for: growth limited by margin or operational capacity, a founder mixing bookings with bank balance, renewal-based planning, hiring or spend decisions, or "we're growing but the account never grows" confusion.
---
name: founder-first-customers
description: Run founder-led prospecting, discovery, demo, proposal, and follow-up to get the first buyers for a bootstrapped B2B SaaS, while honoring the outbound-contact authorization in `.founder/context.md`. Use this when the founder asks "how do I get my first customers," "who do I talk to," "help me demo / propose / follow up," or has a validated problem and no pipeline. Do not use it for repeatable channel experiments or paid acquisition (founder-growth), for launch-day materials and channels (founder-launch), or to invent a customer/problem hypothesis (founder-validate). Do not contact anyone unless authorization is recorded.
---

## What this skill does

Moves a specific offer toward the first customers through prospecting, discovery, demo, proposal, and follow-up. Every outbound step checks **Authorizations** in `.founder/context.md`. Conversations are logged at the real evidence tier. This is founder-led selling, not a growth engine.

## When to use it / when not to

Use it when the buyer and offer are specific enough to name a person, and the obstacle is getting those people into a real conversation or a yes/no. Do not use it when the problem is still unknown (`founder-validate`) or the offer is still mush (`founder-positioning`). Do not use it to scale channels, ads, or content loops — that is `founder-growth` (happy customers with no repeatable acquisition may eventually go there; the first ten do not). Do not use it as a launch checklist (`founder-launch`). Do not use it to answer high churn with more pipeline (`founder-retention`).
---
name: founder-growth
description: Choose and evaluate acquisition and distribution channels for a bootstrapped B2B SaaS through budgeted experiments with explicit pass/fail criteria. Use this when retention is acceptable but there is no repeatable way to add customers, or when the founder asks "how do we get more customers," "which channel should we try," or "should we run ads / do content / do outbound." Do not use it to stop churn (founder-retention — high churn is never solved by more acquisition), to get existing signups to first value (founder-activation), or to prospect named buyers one by one (founder-first-customers) — growth builds a repeatable channel, not a prospect list and not a leak patch.
---

## What this skill does

Turns "we need more customers" into one budgeted channel experiment at a time: which channel, what it costs, what success looks like before the money is spent, and what the founder will do with either outcome. Every experiment carries an explicit budget and explicit evaluation criteria — there is no open-ended "try marketing" advice here.

## When to use it / when not to

Use it for: happy customers with no repeatable acquisition, consistent retention that needs a second channel, or a founder choosing between channels (outbound, content, partnerships, paid, community platforms like Reddit, organic social / building in public, AI-answer-engine visibility, marketplace) with limited money and time.
---
name: founder-launch
description: Size a launch to the actual product and audience — readiness, materials, channels, and follow-through — for a solo founder or small bootstrapped B2B SaaS, not a Series B go-to-market. Use this when the founder asks "are we ready to launch," "write a launch checklist," "where should we announce," or has a published product with no acquisition or interest and wants a first telling. Do not use it for founder-led selling of the first named accounts (founder-first-customers), for ongoing acquisition experiments (founder-growth), or to treat shipping/launch day as commercial validation (founder-review).
---

## What this skill does

Produces a launch that is proportional to who will actually hear it and what the product can actually do: a readiness call, the materials to tell those people, the channels that reach them, and a follow-through experiment. Technical delivery is not commercial validation — launching, or shipping to production, does not conclude the experiment. Demand is still read at stated intent / commitment / payment / recurring use after the window.

## When to use it / when not to

Use it when there is something to show a bounded audience (manual service, prototype, or shipped product) and the founder needs to tell that audience once, on purpose. Do not use it as an excuse to skip `founder-validate` on an idea with no product. Do not use it in place of `founder-first-customers` when the work is one-to-one outreach. Do not use it in place of `founder-growth` when the work is repeatable channel tests with budget. Do not apply a company-wide GTM checklist sized for a funded multi-team launch to a founder's first ten users.
---
name: founder-mvp
description: Define the smallest useful experiment for a bootstrapped B2B SaaS and specify only the product changes that hypothesis actually requires — engineering last, not first. Use this when the founder asks "what should we build," "is this the MVP," "can we concierge this," or is about to write tickets for a full product. Do not use it to discover the customer/problem (founder-validate), to map what already exists (founder-product-audit), or to treat a shipped feature as commercial validation (founder-review). Never auto-invoke Matt's to-spec or to-tickets; those are explicit-invocation skills — prepare the call for the founder.
---

## What this skill does

Names the smallest useful experiment that can move an evidence tier, and the smallest product (or non-product) change that experiment needs. Interviews, a landing ask, a concierge delivery, or a manual workaround beat a build when they can test the same hypothesis. If engineering is required, this skill writes a handoff with technical acceptance criteria **and** a commercial metric — then stops. Technical delivery is not commercial validation.

## When to use it / when not to

Use it when a hypothesis exists and the founder is choosing what to build, shrink, or skip. Use it for partial prototype needing adjustments when the adjustment is in service of a commercial test. Do not use it as a product-roadmap workshop. Do not use it to skip `founder-validate` on an idea with no customer/problem hypothesis. Do not use it to close an experiment after merge — that is `founder-review`. Do not use it to launch (`founder-launch`) or to prospect (`founder-first-customers`).
---
name: founder-pivot
description: Compare persist vs. reposition vs. change segment-or-product vs. shut down from recorded evidence, and preserve the full decision history when the founder changes direction. Use this when the founder asks "should we pivot," "is this working," "should we shut this down," or when repeated experiments keep failing and the hypothesis itself looks wrong. Do not use it to close a single experiment cycle (founder-review), to model cash and margin (founder-economics), or to validate a brand-new idea from scratch (founder-validate) — a pivot decides from the evidence already recorded, and it adds history rather than rewriting it.
---

## What this skill does

Forces the hardest decision through evidence instead of exhaustion: given what has actually been tried and observed, should the founder persist with the current hypothesis, reposition the same product for the same problem, change segment or product, or shut down — and it records that decision so a future session can see what was believed, what disproved it, and what replaced it.

## When to use it / when not to

Use it for: the "need to reposition, pivot, or kill a hypothesis" situation — repeated failed experiments, a segment that won't pay, economics that can't work, or a founder who suspects the problem is the thesis, not the execution.
---
name: founder-positioning
description: Compare the alternatives a buyer already uses, name the differentiation that matters to that buyer, and write a clear offer for a bootstrapped B2B SaaS. Use this when the founder asks "how do we describe this," "what's our positioning," "what's the offer," or when validation showed a real problem but prospects cannot tell this apart from the status quo. Do not use it to set price or packaging (founder-pricing), to pick acquisition channels (founder-growth), to write a launch checklist (founder-launch), or to invent demand that founder-validate has not evidenced.
---

## What this skill does

Produces alternatives, differentiation, and an offer: who it is for, the problem, the promised outcome, and who it is not for. The offer is written from evidence already in `.founder/context.md`, in the founder's language for conversation and in the customer's language for materials. It does not invent competitors, quotes, or wins.

## When to use it / when not to

Use it when the customer/problem is specific enough to compare against real alternatives, including "do nothing" and the current workaround (spreadsheet, intern, incumbent tool, agency). Do not use it as a substitute for `founder-validate` — positioning cannot create demand. Do not use it to choose a number or a packaging ladder — that is `founder-pricing` (the offer names what is sold; pricing names what it costs and how it recurs). Do not use it to plan ads or content engines (`founder-growth`) or a go-to-market event (`founder-launch`).
---
name: founder-pricing
description: Set packaging and price hypotheses for a bootstrapped B2B SaaS and test willingness and ability to pay, keeping recurring revenue, one-off services, pipeline, and cash as separate numbers. Use this when the founder asks "what should we charge," "how do we package this," "are they willing to pay," or when free users are not converting. Do not use it to write the offer or differentiation (founder-positioning), to model full unit economics and runway (founder-economics), or to treat a listed price as proof of demand (founder-validate).
---

## What this skill does

Produces a packaging structure and a price hypothesis, then a test that can observe willingness to pay and ability to pay. It labels money as **recurring**, **one-off**, **pipeline**, or **cash** — those are not interchangeable. A price on a page is not payment. Payment is not recurring use.

## When to use it / when not to

Use it when the offer is clear enough to put a number on, when conversion from free to paid is the obstacle, or when the founder is mixing project fees with subscription in their head. Do not use it to invent the buyer or the problem (`founder-validate`) or the offer sentence (`founder-positioning` first if "what we sell" is still mushy). Do not use it as a full economics model (margin, concentration, runway) — that is `founder-economics`. Do not use it to add features so the price "feels justified."
---
name: founder-product-audit
description: Map what a founder's product actually does — implemented flows, verified behavior, and commercial hypotheses — by inspecting the code, live product, or manual delivery when any of those exist, and name technical blockers only when they obstruct a business experiment. Use this whenever a founder describes an existing prototype or shipped product and asks what to focus on next, even if they've already summarized what's built in their own words — a founder's summary is not a classification into implemented/verified/hypothesis, and this skill is what produces that classification before any other skill acts on it. Also use it for direct asks like "what's actually built," "audit the product," or "should we rebuild." Do not use it to validate demand or talk to customers (founder-validate), to design the smallest next experiment (founder-mvp), or to diagnose why users drop off after signup (founder-activation).
---

## What this skill does

Produces a product map of what exists today: the user/buyer flows, the capabilities behind them, and — for each — whether it is implemented, verified to work, or still a commercial hypothesis wearing a feature's clothes. If code is present, it inspects the code. Technical blockers are listed only when they stop a named business experiment, not because the stack is unfashionable.

It does not prove demand. A built product is not commercial validation.

## When to use it / when not to
---
name: founder-retention
description: Analyze cohorts, cancellations, renewals, and expansion for a bootstrapped B2B SaaS so paying customers stay and grow. Use this when customers cancel, don't renew, go quiet after buying, or when the founder asks "why are we churning," "is our retention healthy," or "how do we expand accounts." Do not use it to get new users to first value (founder-activation), to change packaging or price (founder-pricing), or to find new customers (founder-growth) — retention and acquisition are separate problems with separate causes, and this skill never answers churn with "get more customers."
---

## What this skill does

Turns cancellation and renewal reality into a cohort read the founder can act on: who leaves, when, why, and what — if anything — keeps comparable customers staying and spending more. It treats retention (customers staying) and expansion (customers spending more) as distinct outcomes with distinct evidence, and it treats acquisition as a different problem entirely.

## When to use it / when not to

Use it for: paying customers with weak retention or high churn, renewals that need work, accounts that stay but never expand, or "consistent revenue that suddenly wobbles."
---
name: founder-review
description: Close an experiment cycle for a bootstrapped B2B SaaS — read what was actually observed, update `.founder/experiments.md`, and choose the next step without treating a technical ship as commercial validation. Use this when an observation window has ended, a complement hands work back, the founder asks "did that work," "what should we do next," or a session resumes mid-experiment. Do not use it for a first diagnosis (founder-start), to decide persist vs. pivot vs. shut down as a strategy exercise (founder-pivot), or to start a new acquisition push (founder-growth) — especially not because churn is high.
---

## What this skill does

Reads the running experiment against the evidence that actually showed up, records the decision, and names the next action. Technical delivery from a complement (a merged PR, a deployed feature, a passing test suite) closes only the **technical acceptance criteria** in the handoff. It does not conclude the commercial experiment. That experiment stays **running** until the commercial metric has been observed over its window.

## When to use it / when not to

Use it at the end of an observation window, when inbound handoff notes arrive, or when the founder wants a cycle close rather than a new initiative. Do not use it to replace `founder-start` when there is no experiment history. Do not use it to run a persist / reposition / pivot / shut-down comparison — that is `founder-pivot`, which this skill may *route to* after the evidence is written. Do not use it to launch ads or "get more customers" as the default next step.
---
name: founder-start
description: Diagnose a solo founder or small bootstrapped SaaS team's current business stage, name the main obstacle in the way, persist that context so future sessions can resume it, and route to the right next founder-skills skill. Use this whenever a founder describes their business, asks "what should I focus on," "am I doing this right," "what's next," or opens a new session about their product/company without a specific narrower ask already in mind. Do not use it for a request that's already scoped to one obstacle (e.g. "help me price this" goes straight to founder-pricing; "why are customers cancelling" goes straight to founder-retention) — founder-start is for when the right next step isn't yet known.
---

## What this skill does

Understands where a specific business actually is — not a generic startup stage label, but the real mix of evidence, product state, and constraints — and names one main obstacle and one next experiment. It persists that understanding so the founder doesn't have to re-explain their business every session, and it hands off to whichever of the other 13 founder-skills skills fits that obstacle.

It is a diagnosis and a router, not a doer. The actual work of validating demand, pricing, launching, and so on happens in the skill it routes to.

## When to use it / when not to
---
name: founder-validate
description: Form a customer/problem hypothesis for a bootstrapped B2B SaaS, run interviews and demand experiments, and attach an evidence tier (stated intent, commitment, payment, or recurring use) to whatever is actually observed. Use this when the founder has an idea or a ready product with no commercial validation, asks "is this a real problem," "should I talk to users," or wants to test demand before (or instead of) building. Do not use it to map existing code (founder-product-audit), to write positioning copy (founder-positioning), to set a price (founder-pricing), or to design the build (founder-mvp) — demand evidence first.
---

## What this skill does

Turns a fuzzy "people will want this" into a customer/problem hypothesis that can be falsified, then gathers evidence through conversations and demand experiments. Every claim is tagged with an evidence tier. Missing evidence stays missing.

It does not invent interviews, customers, quotes, or metrics. It does not treat a shipped product, a waitlist, or a compliment as demand.

## When to use it / when not to

hook: PostToolUse
hook: PostToolUse
hook: PostToolUse Completed
hook: PostToolUse Completed
hook: PreToolUse
hook: PreToolUse Completed
exec
/bin/zsh -lc 'cat skills/founder-mvp/SKILL.md skills/founder-product-audit/SKILL.md skills/founder-start/SKILL.md' in /private/tmp/eval-runs-codex/E02
 succeeded in 0ms:
---
name: founder-mvp
description: Define the smallest useful experiment for a bootstrapped B2B SaaS and specify only the product changes that hypothesis actually requires — engineering last, not first. Use this when the founder asks "what should we build," "is this the MVP," "can we concierge this," or is about to write tickets for a full product. Do not use it to discover the customer/problem (founder-validate), to map what already exists (founder-product-audit), or to treat a shipped feature as commercial validation (founder-review). Never auto-invoke Matt's to-spec or to-tickets; those are explicit-invocation skills — prepare the call for the founder.
---

## What this skill does

Names the smallest useful experiment that can move an evidence tier, and the smallest product (or non-product) change that experiment needs. Interviews, a landing ask, a concierge delivery, or a manual workaround beat a build when they can test the same hypothesis. If engineering is required, this skill writes a handoff with technical acceptance criteria **and** a commercial metric — then stops. Technical delivery is not commercial validation.

## When to use it / when not to

Use it when a hypothesis exists and the founder is choosing what to build, shrink, or skip. Use it for partial prototype needing adjustments when the adjustment is in service of a commercial test. Do not use it as a product-roadmap workshop. Do not use it to skip `founder-validate` on an idea with no customer/problem hypothesis. Do not use it to close an experiment after merge — that is `founder-review`. Do not use it to launch (`founder-launch`) or to prospect (`founder-first-customers`).

## Minimum required context

The hypothesis and current evidence from `.founder/context.md` and `.founder/experiments.md`. Product map if `.founder/product-map.md` exists — do not rebuild what is already verified. If the hypothesis is missing, route to `founder-validate` or `founder-start` instead of inventing a build.

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
---
name: founder-product-audit
description: Map what a founder's product actually does — implemented flows, verified behavior, and commercial hypotheses — by inspecting the code, live product, or manual delivery when any of those exist, and name technical blockers only when they obstruct a business experiment. Use this whenever a founder describes an existing prototype or shipped product and asks what to focus on next, even if they've already summarized what's built in their own words — a founder's summary is not a classification into implemented/verified/hypothesis, and this skill is what produces that classification before any other skill acts on it. Also use it for direct asks like "what's actually built," "audit the product," or "should we rebuild." Do not use it to validate demand or talk to customers (founder-validate), to design the smallest next experiment (founder-mvp), or to diagnose why users drop off after signup (founder-activation).
---

## What this skill does

Produces a product map of what exists today: the user/buyer flows, the capabilities behind them, and — for each — whether it is implemented, verified to work, or still a commercial hypothesis wearing a feature's clothes. If code is present, it inspects the code. Technical blockers are listed only when they stop a named business experiment, not because the stack is unfashionable.

It does not prove demand. A built product is not commercial validation.

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
---
name: founder-start
description: Diagnose a solo founder or small bootstrapped SaaS team's current business stage, name the main obstacle in the way, persist that context so future sessions can resume it, and route to the right next founder-skills skill. Use this whenever a founder describes their business, asks "what should I focus on," "am I doing this right," "what's next," or opens a new session about their product/company without a specific narrower ask already in mind. Do not use it for a request that's already scoped to one obstacle (e.g. "help me price this" goes straight to founder-pricing; "why are customers cancelling" goes straight to founder-retention) — founder-start is for when the right next step isn't yet known.
---

## What this skill does

Understands where a specific business actually is — not a generic startup stage label, but the real mix of evidence, product state, and constraints — and names one main obstacle and one next experiment. It persists that understanding so the founder doesn't have to re-explain their business every session, and it hands off to whichever of the other 13 founder-skills skills fits that obstacle.

It is a diagnosis and a router, not a doer. The actual work of validating demand, pricing, launching, and so on happens in the skill it routes to.

## When to use it / when not to

Use it at the start of a session about the business, or whenever the founder is unsure what to work on next. Do not use it when the founder already knows what they need — send them straight to the specific skill instead of making them sit through a diagnosis they don't need. Do not use it to re-run a full diagnosis every session once `.founder/context.md` already exists and nothing material has changed; read the existing context and confirm briefly instead.

## Minimum required context

None required to start — this skill's job is to build the context. If `.founder/context.md` (or the founder's existing equivalent) already exists, read it first; don't ask questions it already answers.

## Procedure

1. **Check for existing context.** Look for `.founder/context.md` or a workspace convention the founder has already established (per `docs/PLAN.md` §6, reuse what exists rather than imposing `.founder/`). If found, summarize it back briefly and ask only what's changed, rather than re-running the full interview.

2. **Discover the business, without assuming a stack.** Ask about, or infer from available material:
   - What the founder is trying to achieve.
   - Who uses it, who buys it (if different), what problem it solves.
   - What exists today: idea only, manual/concierge delivery, partial prototype, shipped product, shipped product with paying customers.
   - Evidence at each of the four tiers: stated intent, commitment, payment, recurring use. Don't let a founder's optimism upgrade a lower tier to a higher one — a expressed interest is not a commitment, a free trial is not a payment.
   - Constraints: time, money, skills, delivery capacity.
   - Whatever documentation, tools, or process already exists — don't assume GitHub, a specific stack, or formal engineering practice.

3. **If code exists, inspect it — but hand the deep dive to `founder-product-audit` if the codebase is nontrivial.** For a quick look, distinguish three things explicitly: what's implemented, what's actually been verified to work, and what's still a commercial hypothesis dressed up as a feature. A built product proves none of demand, retention, or growth by itself.

4. **Name the situation** using the vocabulary from `docs/PLAN.md` §2 (situations can coexist — pick the ones that actually apply, don't force a single label):
   - idea with no product
   - problem validated through manual/concierge delivery
   - partial prototype needing adjustments
   - ready product with no commercial validation
   - published product with no acquisition or interest
   - free users with no conversion
   - paying customers with weak activation or high churn
   - happy customers with no repeatable acquisition
   - growth limited by margin, support, or customer concentration
   - consistent acquisition and retention, seeking expansion
   - need to reposition, pivot, or kill a hypothesis

5. **Name the main obstacle and the next experiment** — singular, not a laundry list. If several situations coexist, pick the one that's actually blocking progress right now, and say why the others aren't the priority yet. Resist recommending a rebuild just because the product lacked traction, or more acquisition just because churn is high — those are default wrong answers the diagnosis exists to prevent (`docs/PLAN.md` §2 principles).

6. **Detect installed complements without installing anything — and without over-claiming.** Check whether Matt Pocock Skills, Superpowers, or gstack are available to use *for this founder's project* — the project's own available-skills listing, an installed-skills directory inside the project or its host tool's project-scoped config, or the founder telling you directly. Do not treat a package installed somewhere on the operator's machine generally (a global plugin cache, a user-level config unrelated to this project) as "present" for this business — a complement genuinely available in one project is not automatically available in another, and reporting it as present when you only found it by scanning outside the project's own scope is exactly the kind of invented evidence this library exists to prevent. If you can't positively confirm a complement is available *for this project*, record it as "not detected" or "unknown," never as present. Record what's actually detected and, if the founder has already been using one of them for technical work, note that as their standing preference — re-check only on a material change or conflict, not every session.

7. **Persist the context.** Create or update `.founder/context.md` with:

   ```markdown
   # Founder context

   Last updated: <date>

   ## Goal
   <what the founder is trying to achieve>

   ## Who
   - User: <...>
   - Buyer: <... or "same as user">
   - Problem: <... mark as hypothesis if not yet evidenced>

   ## What exists
   <idea / manual delivery / partial prototype / shipped, no validation / shipped, paying customers — with the evidence for the classification>

   ## Evidence
   - Stated intent: <...>
   - Commitment: <...>
   - Payment: <...>
   - Recurring use: <...>
   (mark any tier "none yet" rather than inventing something to fill it)

   ## Constraints
   <time, money, skills, delivery capacity>

   ## Authorizations
   <what's authorized for outbound contact, publishing, spend, production — leave unset items unset, don't assume>

   ## Existing docs, tools, processes
   <links only, no copied content>

   ## Complements detected
   <which of the three are present, and any chosen flow>
   ```

8. **Route.** Name the one founder-skills skill that addresses the main obstacle, and say briefly why the others aren't next yet.

## Deliverables

- A one-paragraph diagnosis: situation(s) present, main obstacle, next experiment.
- `.founder/context.md`, created or updated.
- A named next skill to run.

## Judging results / routing the next action

The diagnosis is working if the founder recognizes their situation in it and the named obstacle explains why past efforts (if any) haven't worked — not just a generic label. If the founder pushes back that the diagnosis doesn't match reality, that's signal to gather more evidence, not to argue for the original diagnosis.

Route to the skill whose primary deliverable matches the named obstacle (see the catalog table in `docs/PLAN.md` §3 / the repo README). When situations coexist, route to the earliest unresolved one in the natural sequence (validate → position/price → build → launch → activate → retain → grow → economics/pivot) unless the founder has a specific reason to work out of order.

## Working with no complements installed

Nothing about this skill depends on Matt Pocock Skills, Superpowers, or gstack. Complement detection in step 6 simply records "none detected" and every downstream skill proceeds on its self-contained path.

## Complement integration

If Matt Pocock Skills, Superpowers, or gstack are detected, load the relevant guide from `docs/integration/` only when a downstream skill actually needs to hand off technical work — `founder-start` itself records what's present but doesn't invoke any of them. Never install, update, or modify those packages. Never call an explicit-invocation skill (like Matt's `to-spec` / `to-tickets`) automatically — that's for the downstream skill preparing a real handoff to decide, with the founder in the loop.

hook: PostToolUse
hook: PostToolUse
hook: PostToolUse Completed
hook: PostToolUse Completed
codex
I’m applying the founder product-audit and MVP skills. Your renewals support demand for the service; the next question is whether a small amount of automation can reduce your workload while customers keep paying.
hook: PreToolUse
hook: PreToolUse Completed
exec
/bin/zsh -lc "ls -a .founder 2>/dev/null; rg --files -g '"'!skills/**'"' -g '"'!node_modules/**'"' -g '"'!'"\\.git/**' | head -30" in /private/tmp/eval-runs-codex/E02
 succeeded in 0ms:
output.txt
AGENTS.md

hook: PostToolUse
hook: PostToolUse
hook: PostToolUse Completed
hook: PostToolUse Completed
hook: PreToolUse
hook: PreToolUse Completed
apply patch
patch: completed
/private/tmp/eval-runs-codex/E02/.founder/context.md
/private/tmp/eval-runs-codex/E02/.founder/experiments.md
/private/tmp/eval-runs-codex/E02/.founder/product-map.md
diff --git a/.founder/context.md b/.founder/context.md
new file mode 100644
index 0000000000000000000000000000000000000000..df6f1e919f2fcb251832b25639de20a680a34531
--- /dev/null
+++ b/.founder/context.md
@@ -0,0 +1,33 @@
+# Founder context
+
+Last updated: 2026-09-16
+
+## Goal
+Reduce founder burnout delivering invoice reconciliation; assess transition to SaaS.
+
+## Who
+- Customers: six trucking companies. Individual users and buyers unknown.
+- Problem: invoice reconciliation, currently purchased as a manual service.
+
+## What exists
+Spreadsheet-based concierge service, per founder report. No software product. See [product map](product-map.md).
+
+## Evidence
+- Stated intent: no separate software demand reported.
+- Commitment: no software commitments reported.
+- Payment: six companies at $400/month, per founder.
+- Recurring use: four have paid for three consecutive months; repeat service payment evidenced by founder report, software usage untested. Other two customers' histories unknown.
+- $2,400/month reported service revenue; $1,600/month from the four repeat payers. Neither is validated SaaS revenue.
+
+## Constraints
+Founder burned out by manual delivery. Hours per account, repetitive steps, exception volume, budget, and engineering skills unknown.
+
+## Authorizations
+Advice and local planning notes. Outbound contact, spend, publishing, production, and implementation unset.
+
+## Existing docs, tools, processes
+- [Product map](product-map.md)
+- [Experiment](experiments.md)
+
+## Complements detected
+Project-specific engineering workflow unknown; none selected.
diff --git a/.founder/experiments.md b/.founder/experiments.md
new file mode 100644
index 0000000000000000000000000000000000000000..d02625c909b0b0867d046c73c2634873a9331497
--- /dev/null
+++ b/.founder/experiments.md
@@ -0,0 +1,21 @@
+# Experiments
+
+## Reduce labor while preserving paid reconciliation — drafted 2026-09-16
+
+**Status:** proposed; not started.
+
+**Hypothesis:** Two repeat-paying customers will continue paying $400/month for the same reconciliation outcome when one repeated delivery step is automated and founder labor falls at least 50% without reduced accuracy.
+
+**Action:** Measure the next reconciliation run by step, select the largest repetitive step shared by two repeat payers, then automate only that step behind the existing service. Continue human review and manual handling of exceptions. Exact engineering handoff awaits workflow evidence.
+
+**Owner:** founder.
+
+**Cost:** proposed maximum two founder days of setup after workflow measurement; no new paid tools or spend assumed.
+
+**Metric:** both pilot accounts pay their next two monthly invoices at $400 and continue submitting work. Operational guardrails: labor per comparable reconciliation batch falls at least 50%; discrepancies against manual review resolved before delivery, with no increase in delivered errors.
+
+**Observation window:** two billing cycles starting with first real assisted delivery. Compare labor using similar invoice volumes and account for exception handling and support.
+
+**Evidence:** current service payment only; experiment has not begun.
+
+**Decision:** pending. Successful internal automation validates assisted service economics, not self-service SaaS adoption. Customer-operated software needs a separate paid-use experiment.
diff --git a/.founder/product-map.md b/.founder/product-map.md
new file mode 100644
index 0000000000000000000000000000000000000000..3eef9af503e8c2830f8dca083a77da995c83401a
--- /dev/null
+++ b/.founder/product-map.md
@@ -0,0 +1,22 @@
+# Product map
+
+Last updated: 2026-09-16
+Situation: problem validated through manual/concierge delivery; delivery capacity constrained.
+
+## How to find it
+Founder-described spreadsheet service. No spreadsheets or workflow artifacts supplied.
+
+## Flows
+- Step: reconcile invoices. Capability: manual spreadsheet processing. State: implemented. Evidence: founder describes delivering it to six companies; detailed accuracy and workflow not inspected.
+- Step: pay. Capability: paid service delivery. State: verified. Evidence: founder reports six paying customers at $400/month; payment mechanism unknown, records not independently inspected.
+- Step: come back. Capability: repeat paid service. State: verified. Evidence: founder reports four customers paid three months consecutively.
+- Step: use proposed software. Capability: customers obtain reconciliation value with less founder involvement. State: hypothesis. Evidence: none yet.
+
+## Business-linked technical blockers
+No demonstrated technical blocker. Manual workload constrains delivery; the responsible step is unknown.
+
+## Unknowns
+Discovery, onboarding, input formats, matching rules, exception handling, output format, actual hours, accuracy, buyer/user roles, and software willingness to pay. No code exists per founder.
+
+## Next skill
+founder-mvp: scope one assisted-delivery experiment around the largest repeatable time cost.

hook: PostToolUse
hook: PostToolUse Completed
diff --git a/.founder/context.md b/.founder/context.md
new file mode 100644
index 0000000000000000000000000000000000000000..df6f1e919f2fcb251832b25639de20a680a34531
--- /dev/null
+++ b/.founder/context.md
@@ -0,0 +1,33 @@
+# Founder context
+
+Last updated: 2026-09-16
+
+## Goal
+Reduce founder burnout delivering invoice reconciliation; assess transition to SaaS.
+
+## Who
+- Customers: six trucking companies. Individual users and buyers unknown.
+- Problem: invoice reconciliation, currently purchased as a manual service.
+
+## What exists
+Spreadsheet-based concierge service, per founder report. No software product. See [product map](product-map.md).
+
+## Evidence
+- Stated intent: no separate software demand reported.
+- Commitment: no software commitments reported.
+- Payment: six companies at $400/month, per founder.
+- Recurring use: four have paid for three consecutive months; repeat service payment evidenced by founder report, software usage untested. Other two customers' histories unknown.
+- $2,400/month reported service revenue; $1,600/month from the four repeat payers. Neither is validated SaaS revenue.
+
+## Constraints
+Founder burned out by manual delivery. Hours per account, repetitive steps, exception volume, budget, and engineering skills unknown.
+
+## Authorizations
+Advice and local planning notes. Outbound contact, spend, publishing, production, and implementation unset.
+
+## Existing docs, tools, processes
+- [Product map](product-map.md)
+- [Experiment](experiments.md)
+
+## Complements detected
+Project-specific engineering workflow unknown; none selected.
diff --git a/.founder/experiments.md b/.founder/experiments.md
new file mode 100644
index 0000000000000000000000000000000000000000..d02625c909b0b0867d046c73c2634873a9331497
--- /dev/null
+++ b/.founder/experiments.md
@@ -0,0 +1,21 @@
+# Experiments
+
+## Reduce labor while preserving paid reconciliation — drafted 2026-09-16
+
+**Status:** proposed; not started.
+
+**Hypothesis:** Two repeat-paying customers will continue paying $400/month for the same reconciliation outcome when one repeated delivery step is automated and founder labor falls at least 50% without reduced accuracy.
+
+**Action:** Measure the next reconciliation run by step, select the largest repetitive step shared by two repeat payers, then automate only that step behind the existing service. Continue human review and manual handling of exceptions. Exact engineering handoff awaits workflow evidence.
+
+**Owner:** founder.
+
+**Cost:** proposed maximum two founder days of setup after workflow measurement; no new paid tools or spend assumed.
+
+**Metric:** both pilot accounts pay their next two monthly invoices at $400 and continue submitting work. Operational guardrails: labor per comparable reconciliation batch falls at least 50%; discrepancies against manual review resolved before delivery, with no increase in delivered errors.
+
+**Observation window:** two billing cycles starting with first real assisted delivery. Compare labor using similar invoice volumes and account for exception handling and support.
+
+**Evidence:** current service payment only; experiment has not begun.
+
+**Decision:** pending. Successful internal automation validates assisted service economics, not self-service SaaS adoption. Customer-operated software needs a separate paid-use experiment.
diff --git a/.founder/product-map.md b/.founder/product-map.md
new file mode 100644
index 0000000000000000000000000000000000000000..3eef9af503e8c2830f8dca083a77da995c83401a
--- /dev/null
+++ b/.founder/product-map.md
@@ -0,0 +1,22 @@
+# Product map
+
+Last updated: 2026-09-16
+Situation: problem validated through manual/concierge delivery; delivery capacity constrained.
+
+## How to find it
+Founder-described spreadsheet service. No spreadsheets or workflow artifacts supplied.
+
+## Flows
+- Step: reconcile invoices. Capability: manual spreadsheet processing. State: implemented. Evidence: founder describes delivering it to six companies; detailed accuracy and workflow not inspected.
+- Step: pay. Capability: paid service delivery. State: verified. Evidence: founder reports six paying customers at $400/month; payment mechanism unknown, records not independently inspected.
+- Step: come back. Capability: repeat paid service. State: verified. Evidence: founder reports four customers paid three months consecutively.
+- Step: use proposed software. Capability: customers obtain reconciliation value with less founder involvement. State: hypothesis. Evidence: none yet.
+
+## Business-linked technical blockers
+No demonstrated technical blocker. Manual workload constrains delivery; the responsible step is unknown.
+
+## Unknowns
+Discovery, onboarding, input formats, matching rules, exception handling, output format, actual hours, accuracy, buyer/user roles, and software willingness to pay. No code exists per founder.
+
+## Next skill
+founder-mvp: scope one assisted-delivery experiment around the largest repeatable time cost.

codex
**Start by automating your service’s biggest bottleneck.** Four customers paying for three consecutive months is meaningful evidence that the outcome is worth buying. It doesn’t yet establish that they want to operate software themselves.

You have $2,400/month in reported service revenue, with $1,600/month coming from those four repeat payers. Your immediate constraint is delivery capacity.

### First build

1. **Time your next reconciliation run.** Separate collecting files, cleaning data, matching records, investigating discrepancies, and preparing results.
2. **Pick the largest repetitive step shared by two repeat customers.** Automate that step behind your existing service.
3. **Keep human review and exception handling.** For example, if matching consumes most of your time, the first tool could import existing spreadsheets, suggest matches, flag uncertain records, and export your usual report. The actual workflow should determine the scope.

Cap the initial automation at roughly two days of work. Customer accounts, dashboards, subscriptions, and integrations can wait until a specific customer task requires them.

### Define success before building

For those two customers, over the next two billing cycles:

- Both continue paying $400/month.
- Your time per comparable batch falls by at least 50%.
- Delivered accuracy stays at least as good.

That would justify expanding automation. A customer-facing SaaS needs another test: customers actually completing part of the workflow themselves and continuing to pay.

I saved the [proposed experiment](.founder/experiments.md).

**For one typical company, how many hours does reconciliation take each month, and which step consumes the most time?**
diff --git a/.founder/context.md b/.founder/context.md
new file mode 100644
index 0000000000000000000000000000000000000000..df6f1e919f2fcb251832b25639de20a680a34531
--- /dev/null
+++ b/.founder/context.md
@@ -0,0 +1,33 @@
+# Founder context
+
+Last updated: 2026-09-16
+
+## Goal
+Reduce founder burnout delivering invoice reconciliation; assess transition to SaaS.
+
+## Who
+- Customers: six trucking companies. Individual users and buyers unknown.
+- Problem: invoice reconciliation, currently purchased as a manual service.
+
+## What exists
+Spreadsheet-based concierge service, per founder report. No software product. See [product map](product-map.md).
+
+## Evidence
+- Stated intent: no separate software demand reported.
+- Commitment: no software commitments reported.
+- Payment: six companies at $400/month, per founder.
+- Recurring use: four have paid for three consecutive months; repeat service payment evidenced by founder report, software usage untested. Other two customers' histories unknown.
+- $2,400/month reported service revenue; $1,600/month from the four repeat payers. Neither is validated SaaS revenue.
+
+## Constraints
+Founder burned out by manual delivery. Hours per account, repetitive steps, exception volume, budget, and engineering skills unknown.
+
+## Authorizations
+Advice and local planning notes. Outbound contact, spend, publishing, production, and implementation unset.
+
+## Existing docs, tools, processes
+- [Product map](product-map.md)
+- [Experiment](experiments.md)
+
+## Complements detected
+Project-specific engineering workflow unknown; none selected.
diff --git a/.founder/experiments.md b/.founder/experiments.md
new file mode 100644
index 0000000000000000000000000000000000000000..d02625c909b0b0867d046c73c2634873a9331497
--- /dev/null
+++ b/.founder/experiments.md
@@ -0,0 +1,21 @@
+# Experiments
+
+## Reduce labor while preserving paid reconciliation — drafted 2026-09-16
+
+**Status:** proposed; not started.
+
+**Hypothesis:** Two repeat-paying customers will continue paying $400/month for the same reconciliation outcome when one repeated delivery step is automated and founder labor falls at least 50% without reduced accuracy.
+
+**Action:** Measure the next reconciliation run by step, select the largest repetitive step shared by two repeat payers, then automate only that step behind the existing service. Continue human review and manual handling of exceptions. Exact engineering handoff awaits workflow evidence.
+
+**Owner:** founder.
+
+**Cost:** proposed maximum two founder days of setup after workflow measurement; no new paid tools or spend assumed.
+
+**Metric:** both pilot accounts pay their next two monthly invoices at $400 and continue submitting work. Operational guardrails: labor per comparable reconciliation batch falls at least 50%; discrepancies against manual review resolved before delivery, with no increase in delivered errors.
+
+**Observation window:** two billing cycles starting with first real assisted delivery. Compare labor using similar invoice volumes and account for exception handling and support.
+
+**Evidence:** current service payment only; experiment has not begun.
+
+**Decision:** pending. Successful internal automation validates assisted service economics, not self-service SaaS adoption. Customer-operated software needs a separate paid-use experiment.
diff --git a/.founder/product-map.md b/.founder/product-map.md
new file mode 100644
index 0000000000000000000000000000000000000000..3eef9af503e8c2830f8dca083a77da995c83401a
--- /dev/null
+++ b/.founder/product-map.md
@@ -0,0 +1,22 @@
+# Product map
+
+Last updated: 2026-09-16
+Situation: problem validated through manual/concierge delivery; delivery capacity constrained.
+
+## How to find it
+Founder-described spreadsheet service. No spreadsheets or workflow artifacts supplied.
+
+## Flows
+- Step: reconcile invoices. Capability: manual spreadsheet processing. State: implemented. Evidence: founder describes delivering it to six companies; detailed accuracy and workflow not inspected.
+- Step: pay. Capability: paid service delivery. State: verified. Evidence: founder reports six paying customers at $400/month; payment mechanism unknown, records not independently inspected.
+- Step: come back. Capability: repeat paid service. State: verified. Evidence: founder reports four customers paid three months consecutively.
+- Step: use proposed software. Capability: customers obtain reconciliation value with less founder involvement. State: hypothesis. Evidence: none yet.
+
+## Business-linked technical blockers
+No demonstrated technical blocker. Manual workload constrains delivery; the responsible step is unknown.
+
+## Unknowns
+Discovery, onboarding, input formats, matching rules, exception handling, output format, actual hours, accuracy, buyer/user roles, and software willingness to pay. No code exists per founder.
+
+## Next skill
+founder-mvp: scope one assisted-delivery experiment around the largest repeatable time cost.

hook: Stop
hook: Stop
hook: Stop Completed
hook: Stop Completed
tokens used
23,429
**Start by automating your service’s biggest bottleneck.** Four customers paying for three consecutive months is meaningful evidence that the outcome is worth buying. It doesn’t yet establish that they want to operate software themselves.

You have $2,400/month in reported service revenue, with $1,600/month coming from those four repeat payers. Your immediate constraint is delivery capacity.

### First build

1. **Time your next reconciliation run.** Separate collecting files, cleaning data, matching records, investigating discrepancies, and preparing results.
2. **Pick the largest repetitive step shared by two repeat customers.** Automate that step behind your existing service.
3. **Keep human review and exception handling.** For example, if matching consumes most of your time, the first tool could import existing spreadsheets, suggest matches, flag uncertain records, and export your usual report. The actual workflow should determine the scope.

Cap the initial automation at roughly two days of work. Customer accounts, dashboards, subscriptions, and integrations can wait until a specific customer task requires them.

### Define success before building

For those two customers, over the next two billing cycles:

- Both continue paying $400/month.
- Your time per comparable batch falls by at least 50%.
- Delivered accuracy stays at least as good.

That would justify expanding automation. A customer-facing SaaS needs another test: customers actually completing part of the workflow themselves and continuing to pay.

I saved the [proposed experiment](.founder/experiments.md).

**For one typical company, how many hours does reconciliation take each month, and which step consumes the most time?**
