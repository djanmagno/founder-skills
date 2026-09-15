Reading additional input from stdin...
OpenAI Codex v0.154.0
--------
workdir: /private/tmp/eval-runs-codex/E06
model: gpt-6-astra
provider: openai
approval: never
sandbox: workspace-write [workdir, /tmp, $TMPDIR]
reasoning effort: low
reasoning summaries: none
session id: 01a0a746-246c-7273-9cef-f759088e1845
--------
user
We have 40 people using the free version of Formwise every week — genuinely using it, not just signed up and gone. But literally nobody has upgraded to paid in 2 months. I think the paid tier just doesn't have enough extra features yet, so I want to spend the next few weeks building 3-4 more paid-only features before pushing conversion again. Good plan?
warning: Skill descriptions were shortened to fit the skills context budget. Codex can still see every skill, but some descriptions are shorter. Disable unused skills or plugins to leave more room for the rest.
hook: SessionStart
hook: SessionStart Completed
hook: UserPromptSubmit
hook: UserPromptSubmit Completed
codex
I’ll check the relevant strategy skill, then assess whether more features are the right next step.
hook: PreToolUse
hook: PreToolUse Completed
exec
/bin/zsh -lc 'rg --files skills -g SKILL.md' in /private/tmp/eval-runs-codex/E06
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
/bin/zsh -lc "cat '/Users/user01/.codex/plugins/cache/superpowers-dev/superpowers/6.3.0/skills/using-superpowers/SKILL.md'" in /private/tmp/eval-runs-codex/E06
 succeeded in 0ms:
---
name: using-superpowers
description: Use when starting any conversation - establishes how to find and use skills, requiring skill invocation before ANY response including clarifying questions
---

<SUBAGENT-STOP>
If you were dispatched as a subagent to execute a specific task, ignore this skill.
</SUBAGENT-STOP>

<EXTREMELY-IMPORTANT>
If you think there is even a 1% chance a skill might apply to what you are doing, you ABSOLUTELY MUST invoke the skill.

IF A SKILL APPLIES TO YOUR TASK, YOU DO NOT HAVE A CHOICE. YOU MUST USE IT.

This is not negotiable. You cannot rationalize your way out of this.
</EXTREMELY-IMPORTANT>

## The Rule

**Invoke relevant or requested skills BEFORE any response or action** — including clarifying questions, exploring the codebase, or checking files. If it turns out wrong for the situation, you don't have to use it.

**Before entering plan mode:** if you haven't already brainstormed, invoke the brainstorming skill first.

Then announce "Using [skill] to [purpose]" and follow the skill exactly. If it has a checklist, create a todo per item.

## Skill Priority

When multiple skills apply, process skills come first — they set the approach, then implementation skills (frontend-design, etc.) carry it out. Brainstorming and systematic-debugging are Superpowers' most common process skills, but the rule holds for any of them.

- "Let's build X" → superpowers:brainstorming first, then implementation skills.
- "Fix this bug" → superpowers:systematic-debugging first, then domain skills.

## Red Flags

These thoughts mean STOP—you're rationalizing:

| Thought | Reality |
|---------|---------|
| "This is just a simple question" | Questions are tasks. Check for skills. |
| "I need more context first" | Skill check comes BEFORE clarifying questions. |
| "Let me explore the codebase first" | Skills tell you HOW to explore. Check first. |
| "I can check git/files quickly" | Files lack conversation context. Check for skills. |
| "Let me gather information first" | Skills tell you HOW to gather information. |
| "This doesn't need a formal skill" | If a skill exists, use it. |
| "I remember this skill" | Skills evolve. Read current version. |
| "This doesn't count as a task" | Action = task. Check for skills. |
| "The skill is overkill" | Simple things become complex. Use it. |
| "I'll just do this one thing first" | Check BEFORE doing anything. |
| "This feels productive" | Undisciplined action wastes time. Skills prevent this. |
| "I know what that means" | Knowing the concept ≠ using the skill. Invoke it. |

## Platform Adaptation

If your harness appears here, read its reference file for special instructions:

- Codex: `references/codex-tools.md`
- Pi: `references/pi-tools.md`
- Antigravity: `references/antigravity-tools.md`
- Hermes Agent: `references/hermes-tools.md`

## User Instructions

User instructions (CLAUDE.md, AGENTS.md, GEMINI.md, etc, direct requests) take precedence over skills, which in turn override default behavior. Only skip skill workflows or instructions when your human partner has explicitly told you to.

hook: PostToolUse
hook: PostToolUse
hook: PostToolUse Completed
hook: PostToolUse Completed
hook: PreToolUse
hook: PreToolUse Completed
exec
/bin/zsh -lc "python3 - <<'PY'
from pathlib import Path
for p in Path('skills').rglob('SKILL.md'):
 print(str(p)+'\\n'+p.read_text().split('---')[1])
PY" in /private/tmp/eval-runs-codex/E06
 succeeded in 0ms:
skills/founder-product-audit/SKILL.md

name: founder-product-audit
description: Map what a founder's product actually does — implemented flows, verified behavior, and commercial hypotheses — by inspecting the code, live product, or manual delivery when any of those exist, and name technical blockers only when they obstruct a business experiment. Use this whenever a founder describes an existing prototype or shipped product and asks what to focus on next, even if they've already summarized what's built in their own words — a founder's summary is not a classification into implemented/verified/hypothesis, and this skill is what produces that classification before any other skill acts on it. Also use it for direct asks like "what's actually built," "audit the product," or "should we rebuild." Do not use it to validate demand or talk to customers (founder-validate), to design the smallest next experiment (founder-mvp), or to diagnose why users drop off after signup (founder-activation).

skills/founder-positioning/SKILL.md

name: founder-positioning
description: Compare the alternatives a buyer already uses, name the differentiation that matters to that buyer, and write a clear offer for a bootstrapped B2B SaaS. Use this when the founder asks "how do we describe this," "what's our positioning," "what's the offer," or when validation showed a real problem but prospects cannot tell this apart from the status quo. Do not use it to set price or packaging (founder-pricing), to pick acquisition channels (founder-growth), to write a launch checklist (founder-launch), or to invent demand that founder-validate has not evidenced.

skills/founder-pivot/SKILL.md

name: founder-pivot
description: Compare persist vs. reposition vs. change segment-or-product vs. shut down from recorded evidence, and preserve the full decision history when the founder changes direction. Use this when the founder asks "should we pivot," "is this working," "should we shut this down," or when repeated experiments keep failing and the hypothesis itself looks wrong. Do not use it to close a single experiment cycle (founder-review), to model cash and margin (founder-economics), or to validate a brand-new idea from scratch (founder-validate) — a pivot decides from the evidence already recorded, and it adds history rather than rewriting it.

skills/founder-retention/SKILL.md

name: founder-retention
description: Analyze cohorts, cancellations, renewals, and expansion for a bootstrapped B2B SaaS so paying customers stay and grow. Use this when customers cancel, don't renew, go quiet after buying, or when the founder asks "why are we churning," "is our retention healthy," or "how do we expand accounts." Do not use it to get new users to first value (founder-activation), to change packaging or price (founder-pricing), or to find new customers (founder-growth) — retention and acquisition are separate problems with separate causes, and this skill never answers churn with "get more customers."

skills/founder-start/SKILL.md

name: founder-start
description: Diagnose a solo founder or small bootstrapped SaaS team's current business stage, name the main obstacle in the way, persist that context so future sessions can resume it, and route to the right next founder-skills skill. Use this whenever a founder describes their business, asks "what should I focus on," "am I doing this right," "what's next," or opens a new session about their product/company without a specific narrower ask already in mind. Do not use it for a request that's already scoped to one obstacle (e.g. "help me price this" goes straight to founder-pricing; "why are customers cancelling" goes straight to founder-retention) — founder-start is for when the right next step isn't yet known.

skills/founder-launch/SKILL.md

name: founder-launch
description: Size a launch to the actual product and audience — readiness, materials, channels, and follow-through — for a solo founder or small bootstrapped B2B SaaS, not a Series B go-to-market. Use this when the founder asks "are we ready to launch," "write a launch checklist," "where should we announce," or has a published product with no acquisition or interest and wants a first telling. Do not use it for founder-led selling of the first named accounts (founder-first-customers), for ongoing acquisition experiments (founder-growth), or to treat shipping/launch day as commercial validation (founder-review).

skills/founder-activation/SKILL.md

name: founder-activation
description: Define a new user's first value moment for a bootstrapped B2B SaaS, diagnose where early users drop off, and fix onboarding so more of them reach that value. Use this when signups or trials don't turn into active users, when the founder asks "why do people sign up and disappear," "how do we improve onboarding," or "what is our aha moment." Do not use it for pricing and packaging (founder-pricing), for keeping paying customers over months and expanding accounts (founder-retention), or for getting more visitors in the door (founder-growth) — activation is about users who already arrived reaching first value, not about acquiring more of them.

skills/founder-mvp/SKILL.md

name: founder-mvp
description: Define the smallest useful experiment for a bootstrapped B2B SaaS and specify only the product changes that hypothesis actually requires — engineering last, not first. Use this when the founder asks "what should we build," "is this the MVP," "can we concierge this," or is about to write tickets for a full product. Do not use it to discover the customer/problem (founder-validate), to map what already exists (founder-product-audit), or to treat a shipped feature as commercial validation (founder-review). Never auto-invoke Matt's to-spec or to-tickets; those are explicit-invocation skills — prepare the call for the founder.

skills/founder-first-customers/SKILL.md

name: founder-first-customers
description: Run founder-led prospecting, discovery, demo, proposal, and follow-up to get the first buyers for a bootstrapped B2B SaaS, while honoring the outbound-contact authorization in `.founder/context.md`. Use this when the founder asks "how do I get my first customers," "who do I talk to," "help me demo / propose / follow up," or has a validated problem and no pipeline. Do not use it for repeatable channel experiments or paid acquisition (founder-growth), for launch-day materials and channels (founder-launch), or to invent a customer/problem hypothesis (founder-validate). Do not contact anyone unless authorization is recorded.

skills/founder-review/SKILL.md

name: founder-review
description: Close an experiment cycle for a bootstrapped B2B SaaS — read what was actually observed, update `.founder/experiments.md`, and choose the next step without treating a technical ship as commercial validation. Use this when an observation window has ended, a complement hands work back, the founder asks "did that work," "what should we do next," or a session resumes mid-experiment. Do not use it for a first diagnosis (founder-start), to decide persist vs. pivot vs. shut down as a strategy exercise (founder-pivot), or to start a new acquisition push (founder-growth) — especially not because churn is high.

skills/founder-economics/SKILL.md

name: founder-economics
description: Model unit economics and cash constraints for a bootstrapped B2B SaaS — recurring revenue, one-off revenue, pipeline, and cash as four distinct numbers, plus margin and customer concentration risk. Use this when the founder asks "are we sustainable," "can we afford this," "what does our revenue actually look like," or when growth is limited by margin, support load, or dependence on one or two customers. Do not use it to set packaging or test willingness to pay (founder-pricing), to choose acquisition channels (founder-growth), or to record shipped code as commercial progress (founder-review) — a completed build is never itself commercial validation, and revenue is never recognized here until money and renewal reality say so.

skills/founder-growth/SKILL.md

name: founder-growth
description: Choose and evaluate acquisition and distribution channels for a bootstrapped B2B SaaS through budgeted experiments with explicit pass/fail criteria. Use this when retention is acceptable but there is no repeatable way to add customers, or when the founder asks "how do we get more customers," "which channel should we try," or "should we run ads / do content / do outbound." Do not use it to stop churn (founder-retention — high churn is never solved by more acquisition), to get existing signups to first value (founder-activation), or to prospect named buyers one by one (founder-first-customers) — growth builds a repeatable channel, not a prospect list and not a leak patch.

skills/founder-pricing/SKILL.md

name: founder-pricing
description: Set packaging and price hypotheses for a bootstrapped B2B SaaS and test willingness and ability to pay, keeping recurring revenue, one-off services, pipeline, and cash as separate numbers. Use this when the founder asks "what should we charge," "how do we package this," "are they willing to pay," or when free users are not converting. Do not use it to write the offer or differentiation (founder-positioning), to model full unit economics and runway (founder-economics), or to treat a listed price as proof of demand (founder-validate).

skills/founder-validate/SKILL.md

name: founder-validate
description: Form a customer/problem hypothesis for a bootstrapped B2B SaaS, run interviews and demand experiments, and attach an evidence tier (stated intent, commitment, payment, or recurring use) to whatever is actually observed. Use this when the founder has an idea or a ready product with no commercial validation, asks "is this a real problem," "should I talk to users," or wants to test demand before (or instead of) building. Do not use it to map existing code (founder-product-audit), to write positioning copy (founder-positioning), to set a price (founder-pricing), or to design the build (founder-mvp) — demand evidence first.


hook: PostToolUse
hook: PostToolUse
hook: PostToolUse Completed
hook: PostToolUse Completed
hook: PreToolUse
hook: PreToolUse Completed
exec
/bin/zsh -lc 'cat skills/founder-pricing/SKILL.md skills/founder-product-audit/SKILL.md' in /private/tmp/eval-runs-codex/E06
 succeeded in 0ms:
---
name: founder-pricing
description: Set packaging and price hypotheses for a bootstrapped B2B SaaS and test willingness and ability to pay, keeping recurring revenue, one-off services, pipeline, and cash as separate numbers. Use this when the founder asks "what should we charge," "how do we package this," "are they willing to pay," or when free users are not converting. Do not use it to write the offer or differentiation (founder-positioning), to model full unit economics and runway (founder-economics), or to treat a listed price as proof of demand (founder-validate).
---

## What this skill does

Produces a packaging structure and a price hypothesis, then a test that can observe willingness to pay and ability to pay. It labels money as **recurring**, **one-off**, **pipeline**, or **cash** — those are not interchangeable. A price on a page is not payment. Payment is not recurring use.

## When to use it / when not to

Use it when the offer is clear enough to put a number on, when conversion from free to paid is the obstacle, or when the founder is mixing project fees with subscription in their head. Do not use it to invent the buyer or the problem (`founder-validate`) or the offer sentence (`founder-positioning` first if "what we sell" is still mushy). Do not use it as a full economics model (margin, concentration, runway) — that is `founder-economics`. Do not use it to add features so the price "feels justified."

## Minimum required context

Buyer, offer (or a draft), and **Evidence** from `.founder/context.md`. Read `.founder/positioning.md` if it exists. If the founder cannot name who pays, stop and route to `founder-validate`. Authorizations for quoting a price or taking money must be explicit before anyone is charged.

## Procedure

1. **Separate the money types before choosing a number.** Write down, with actuals or "none yet":
   - **Recurring revenue** — subscription or contract that is expected to renew.
   - **One-off revenue** — setup, concierge, implementation, a single project.
   - **Pipeline** — verbal interest or proposals outstanding; not revenue.
   - **Cash** — what is in the account, independent of bookings.

   Do not add these together into a fake ARR. Do not call a one-off implementation "ARR."

2. **Package around the job, not around feature count.** One or few packages a solo founder can sell and deliver. Each package: who it is for, what is included, what is not, whether the fee is recurring, one-off, or a mix. Constraints (delivery capacity, support) from context bound how much can be sold.

3. **Distinguish willingness from ability.** Willingness: they want this enough to spend. Ability: they have budget, authority, and a path to pay (procurement, card, invoice). A founder-buyer who loves it but cannot sign is not a price confirmation. Record which of the two any conversation actually tested.

4. **Choose a test, not a spreadsheet conclusion.** Put a real number in front of a real buyer (conversation, proposal, paid pilot, checkout). Observation is a commitment or a payment — not "they didn't flinch" as a story with no next step. Do not invent survey percentages. Do not copy a competitor's public price as evidence this buyer will pay it.

5. **Log the experiment** in `.founder/experiments.md`:

   ```markdown
   ## <short experiment name> — <date started>

   **Status:** running / concluded / superseded (if superseded, by which entry and why)

   **Hypothesis:** who pays what, how often (recurring vs one-off), and for which package.

   **Action:** the specific ask (quote, pilot, checkout, proposal).

   **Owner:** ...

   **Cost:** time and any discounts/credits offered.

   **Metric:** commitments and/or payments, labeled recurring vs one-off. Not "interest."

   **Observation window:** when you read the metric.

   **Evidence:** observed — or "window still open" / "none yet."

   **Decision:** fill after the window.
   ```

6. **Persist the packaging.** Create or update `.founder/pricing.md`:

   ```markdown
   # Packaging and price

   Last updated: <date>

   ## Money types (do not mix)
   - Recurring: <actual / hypothesis / none yet>
   - One-off: <...>
   - Pipeline: <...>
   - Cash: <...>

   ## Packages
   For each:
   - Name / who it is for:
   - Included / not included:
   - Price and cadence (recurring vs one-off):
   - Delivery capacity required:

   ## Willingness vs ability
   - What has been tested:
   - Evidence tier reached: stated intent / commitment / payment / recurring use
   - Unknowns:

   ## Claims we will not make
   <no ARR inferred from one-off work; no conversion inferred from free signups>
   ```

   Update `.founder/context.md` **Evidence** and **Constraints** if a real price was accepted or refused. A refusal is evidence; do not hide it.

7. **Do not treat a built billing page as validation.** Shipping Stripe is technical delivery, not commercial validation. The commercial experiment stays open until payment (and, for a subscription hypothesis, until recurring use or renewal evidence exists).

## Deliverables

- `.founder/pricing.md` with packages and money types separated.
- An experiment entry whose metric is commitment or payment, labeled recurring vs one-off.
- Updated evidence in `.founder/context.md` when something was actually charged or refused.
- A named next skill.

## Judging results / routing the next action

Success: a founder can quote a package without mixing ARR and project fees, and the test can fail. Failure: invented WTP, one-off work reported as ARR, free users "validated" by adding a price tag, or more features as the answer to no conversion.

Route:
- Offer still unclear → `founder-positioning`.
- Need authorized conversations/proposals → `founder-first-customers`.
- Price requires a product change (gating, billing) → `founder-mvp`; the commercial test still closes in `founder-review`.
- Free users, paid intent weak → stay here or `founder-activation` if they never reach value.
- Margin/cash/concentration after real prices exist → `founder-economics`.
- Window ended → `founder-review`.

## Working with no complements installed

Quote in conversation, send a proposal, take a wire or a simple invoice. No billing product required to test willingness. If the founder cannot take money yet, test commitment (signed pilot, dated kickoff) and keep the payment tier at "none yet."

## Complement integration

Engineering for checkout, entitlements, or invoicing goes through `founder-mvp` with a handoff — do not invoke `to-spec` / `to-tickets` from here. gstack `office-hours` only if the pricing model itself is a strategic fork (e.g. one-off services vs recurring) after the money types are written down. Never install packages. Load `docs/integration/` guides only when the matching package is present.
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

hook: PostToolUse
hook: PostToolUse
hook: PostToolUse Completed
hook: PostToolUse Completed
hook: PreToolUse
hook: PreToolUse Completed
exec
/bin/zsh -lc 'ls -a' in /private/tmp/eval-runs-codex/E06
 succeeded in 0ms:
.
..
AGENTS.md
output.txt
skills

hook: PostToolUse
hook: PostToolUse
hook: PostToolUse Completed
hook: PostToolUse Completed
codex
I’m using the founder-pricing skill: the unresolved question is why active users won’t pay. More paid features are one possible explanation, but the usage numbers don’t establish it.
hook: PreToolUse
hook: PreToolUse Completed
web search: 
web search: site.ycombinator.com talk to users hypothetical questions specifics life
hook: PostToolUse
hook: PostToolUse Completed
codex
**I wouldn’t commit the next few weeks to that yet.** Forty weekly users is evidence that Formwise is useful. Zero upgrades means the paid offer hasn’t converted them; it doesn’t establish that missing features are the reason.

Several explanations fit:

- Free already covers their entire job.
- Paid extras don’t solve a problem they urgently need solved.
- Users lack budget or purchasing authority.
- They haven’t encountered a clear upgrade offer—or payment is difficult.

**Spend a week testing the paid proposition before expanding it:**

1. **Talk to 5–8 active users.** Ask about their last real use, what it accomplished, what remained difficult, and what they currently spend to solve that difficulty. Focus on actual behavior rather than hypothetical feature requests. [YC’s user interview guidance](https://www.ycombinator.com/library/6g-how-to-talk-to-users).
2. **Check the upgrade path.** How many of those 40 actually saw the paid offer, hit a relevant limit, or attempted checkout?
3. **Make a concrete offer to suitable buyers:** a specific outcome, scope, price, and start date. Test willingness to pay alongside ability to pay.
4. **Set a decision rule beforehand.** For example: two paid pilots from eight qualified offers justifies further testing. That’s a proposed threshold, not an industry benchmark. Compliments and feature requests don’t count as purchases.

Build a missing feature when multiple buyers identify the same blocker and make a concrete purchasing commitment contingent on it. Then build the smallest version that delivers that outcome.

**Who are these users, what does paid currently cost/include, and have you directly asked any of them to upgrade?**
hook: Stop
hook: Stop
hook: Stop Completed
hook: Stop Completed
tokens used
21,723
**I wouldn’t commit the next few weeks to that yet.** Forty weekly users is evidence that Formwise is useful. Zero upgrades means the paid offer hasn’t converted them; it doesn’t establish that missing features are the reason.

Several explanations fit:

- Free already covers their entire job.
- Paid extras don’t solve a problem they urgently need solved.
- Users lack budget or purchasing authority.
- They haven’t encountered a clear upgrade offer—or payment is difficult.

**Spend a week testing the paid proposition before expanding it:**

1. **Talk to 5–8 active users.** Ask about their last real use, what it accomplished, what remained difficult, and what they currently spend to solve that difficulty. Focus on actual behavior rather than hypothetical feature requests. [YC’s user interview guidance](https://www.ycombinator.com/library/6g-how-to-talk-to-users).
2. **Check the upgrade path.** How many of those 40 actually saw the paid offer, hit a relevant limit, or attempted checkout?
3. **Make a concrete offer to suitable buyers:** a specific outcome, scope, price, and start date. Test willingness to pay alongside ability to pay.
4. **Set a decision rule beforehand.** For example: two paid pilots from eight qualified offers justifies further testing. That’s a proposed threshold, not an industry benchmark. Compliments and feature requests don’t count as purchases.

Build a missing feature when multiple buyers identify the same blocker and make a concrete purchasing commitment contingent on it. Then build the smallest version that delivers that outcome.

**Who are these users, what does paid currently cost/include, and have you directly asked any of them to upgrade?**
