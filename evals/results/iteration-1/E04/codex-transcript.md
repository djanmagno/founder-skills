Reading additional input from stdin...
OpenAI Codex v0.154.0
--------
workdir: /private/tmp/eval-runs-codex/E04
model: gpt-6-astra
provider: openai
approval: never
sandbox: workspace-write [workdir, /tmp, $TMPDIR]
reasoning effort: low
reasoning summaries: none
session id: 01a0a744-08bf-7dc1-b99c-c9ac37e64da4
--------
user
My product is basically done — full auth, billing works, the core matching feature works end to end, I've tested it myself for weeks. I'm proud of what I built. What's my next move to start getting revenue?
warning: Skill descriptions were shortened to fit the skills context budget. Codex can still see every skill, but some descriptions are shorter. Disable unused skills or plugins to leave more room for the rest.
hook: SessionStart
hook: SessionStart Completed
hook: UserPromptSubmit
hook: UserPromptSubmit Completed
codex
I’ll check the relevant guidance, then focus on the next step toward paying customers.
hook: PreToolUse
hook: PreToolUse Completed
exec
/bin/zsh -lc 'rg --files skills -g SKILL.md' in /private/tmp/eval-runs-codex/E04
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
/bin/zsh -lc "rg -n -A 5 '"'^description:'"' skills/*/SKILL.md" in /private/tmp/eval-runs-codex/E04
 succeeded in 0ms:
skills/founder-launch/SKILL.md:3:description: Size a launch to the actual product and audience — readiness, materials, channels, and follow-through — for a solo founder or small bootstrapped B2B SaaS, not a Series B go-to-market. Use this when the founder asks "are we ready to launch," "write a launch checklist," "where should we announce," or has a published product with no acquisition or interest and wants a first telling. Do not use it for founder-led selling of the first named accounts (founder-first-customers), for ongoing acquisition experiments (founder-growth), or to treat shipping/launch day as commercial validation (founder-review).
skills/founder-launch/SKILL.md-4----
skills/founder-launch/SKILL.md-5-
skills/founder-launch/SKILL.md-6-## What this skill does
skills/founder-launch/SKILL.md-7-
skills/founder-launch/SKILL.md-8-Produces a launch that is proportional to who will actually hear it and what the product can actually do: a readiness call, the materials to tell those people, the channels that reach them, and a follow-through experiment. Technical delivery is not commercial validation — launching, or shipping to production, does not conclude the experiment. Demand is still read at stated intent / commitment / payment / recurring use after the window.
--
skills/founder-positioning/SKILL.md:3:description: Compare the alternatives a buyer already uses, name the differentiation that matters to that buyer, and write a clear offer for a bootstrapped B2B SaaS. Use this when the founder asks "how do we describe this," "what's our positioning," "what's the offer," or when validation showed a real problem but prospects cannot tell this apart from the status quo. Do not use it to set price or packaging (founder-pricing), to pick acquisition channels (founder-growth), to write a launch checklist (founder-launch), or to invent demand that founder-validate has not evidenced.
skills/founder-positioning/SKILL.md-4----
skills/founder-positioning/SKILL.md-5-
skills/founder-positioning/SKILL.md-6-## What this skill does
skills/founder-positioning/SKILL.md-7-
skills/founder-positioning/SKILL.md-8-Produces alternatives, differentiation, and an offer: who it is for, the problem, the promised outcome, and who it is not for. The offer is written from evidence already in `.founder/context.md`, in the founder's language for conversation and in the customer's language for materials. It does not invent competitors, quotes, or wins.
--
skills/founder-mvp/SKILL.md:3:description: Define the smallest useful experiment for a bootstrapped B2B SaaS and specify only the product changes that hypothesis actually requires — engineering last, not first. Use this when the founder asks "what should we build," "is this the MVP," "can we concierge this," or is about to write tickets for a full product. Do not use it to discover the customer/problem (founder-validate), to map what already exists (founder-product-audit), or to treat a shipped feature as commercial validation (founder-review). Never auto-invoke Matt's to-spec or to-tickets; those are explicit-invocation skills — prepare the call for the founder.
skills/founder-mvp/SKILL.md-4----
skills/founder-mvp/SKILL.md-5-
skills/founder-mvp/SKILL.md-6-## What this skill does
skills/founder-mvp/SKILL.md-7-
skills/founder-mvp/SKILL.md-8-Names the smallest useful experiment that can move an evidence tier, and the smallest product (or non-product) change that experiment needs. Interviews, a landing ask, a concierge delivery, or a manual workaround beat a build when they can test the same hypothesis. If engineering is required, this skill writes a handoff with technical acceptance criteria **and** a commercial metric — then stops. Technical delivery is not commercial validation.
--
skills/founder-first-customers/SKILL.md:3:description: Run founder-led prospecting, discovery, demo, proposal, and follow-up to get the first buyers for a bootstrapped B2B SaaS, while honoring the outbound-contact authorization in `.founder/context.md`. Use this when the founder asks "how do I get my first customers," "who do I talk to," "help me demo / propose / follow up," or has a validated problem and no pipeline. Do not use it for repeatable channel experiments or paid acquisition (founder-growth), for launch-day materials and channels (founder-launch), or to invent a customer/problem hypothesis (founder-validate). Do not contact anyone unless authorization is recorded.
skills/founder-first-customers/SKILL.md-4----
skills/founder-first-customers/SKILL.md-5-
skills/founder-first-customers/SKILL.md-6-## What this skill does
skills/founder-first-customers/SKILL.md-7-
skills/founder-first-customers/SKILL.md-8-Moves a specific offer toward the first customers through prospecting, discovery, demo, proposal, and follow-up. Every outbound step checks **Authorizations** in `.founder/context.md`. Conversations are logged at the real evidence tier. This is founder-led selling, not a growth engine.
--
skills/founder-growth/SKILL.md:3:description: Choose and evaluate acquisition and distribution channels for a bootstrapped B2B SaaS through budgeted experiments with explicit pass/fail criteria. Use this when retention is acceptable but there is no repeatable way to add customers, or when the founder asks "how do we get more customers," "which channel should we try," or "should we run ads / do content / do outbound." Do not use it to stop churn (founder-retention — high churn is never solved by more acquisition), to get existing signups to first value (founder-activation), or to prospect named buyers one by one (founder-first-customers) — growth builds a repeatable channel, not a prospect list and not a leak patch.
skills/founder-growth/SKILL.md-4----
skills/founder-growth/SKILL.md-5-
skills/founder-growth/SKILL.md-6-## What this skill does
skills/founder-growth/SKILL.md-7-
skills/founder-growth/SKILL.md-8-Turns "we need more customers" into one budgeted channel experiment at a time: which channel, what it costs, what success looks like before the money is spent, and what the founder will do with either outcome. Every experiment carries an explicit budget and explicit evaluation criteria — there is no open-ended "try marketing" advice here.
--
skills/founder-activation/SKILL.md:3:description: Define a new user's first value moment for a bootstrapped B2B SaaS, diagnose where early users drop off, and fix onboarding so more of them reach that value. Use this when signups or trials don't turn into active users, when the founder asks "why do people sign up and disappear," "how do we improve onboarding," or "what is our aha moment." Do not use it for pricing and packaging (founder-pricing), for keeping paying customers over months and expanding accounts (founder-retention), or for getting more visitors in the door (founder-growth) — activation is about users who already arrived reaching first value, not about acquiring more of them.
skills/founder-activation/SKILL.md-4----
skills/founder-activation/SKILL.md-5-
skills/founder-activation/SKILL.md-6-## What this skill does
skills/founder-activation/SKILL.md-7-
skills/founder-activation/SKILL.md-8-Names the single first value a new user must experience, finds the step where most of them abandon before reaching it, and runs a small experiment to remove or shrink that drop-off. It works on users who already signed up — free, trial, or newly paying — and it stops once first value is consistently reached. Everything after that (renewal, expansion, long-term habit) belongs to `founder-retention`.
--
skills/founder-pivot/SKILL.md:3:description: Compare persist vs. reposition vs. change segment-or-product vs. shut down from recorded evidence, and preserve the full decision history when the founder changes direction. Use this when the founder asks "should we pivot," "is this working," "should we shut this down," or when repeated experiments keep failing and the hypothesis itself looks wrong. Do not use it to close a single experiment cycle (founder-review), to model cash and margin (founder-economics), or to validate a brand-new idea from scratch (founder-validate) — a pivot decides from the evidence already recorded, and it adds history rather than rewriting it.
skills/founder-pivot/SKILL.md-4----
skills/founder-pivot/SKILL.md-5-
skills/founder-pivot/SKILL.md-6-## What this skill does
skills/founder-pivot/SKILL.md-7-
skills/founder-pivot/SKILL.md-8-Forces the hardest decision through evidence instead of exhaustion: given what has actually been tried and observed, should the founder persist with the current hypothesis, reposition the same product for the same problem, change segment or product, or shut down — and it records that decision so a future session can see what was believed, what disproved it, and what replaced it.
--
skills/founder-economics/SKILL.md:3:description: Model unit economics and cash constraints for a bootstrapped B2B SaaS — recurring revenue, one-off revenue, pipeline, and cash as four distinct numbers, plus margin and customer concentration risk. Use this when the founder asks "are we sustainable," "can we afford this," "what does our revenue actually look like," or when growth is limited by margin, support load, or dependence on one or two customers. Do not use it to set packaging or test willingness to pay (founder-pricing), to choose acquisition channels (founder-growth), or to record shipped code as commercial progress (founder-review) — a completed build is never itself commercial validation, and revenue is never recognized here until money and renewal reality say so.
skills/founder-economics/SKILL.md-4----
skills/founder-economics/SKILL.md-5-
skills/founder-economics/SKILL.md-6-## What this skill does
skills/founder-economics/SKILL.md-7-
skills/founder-economics/SKILL.md-8-Produces an honest money picture a solo founder can decide from: what recurs, what was one-off, what is merely pipeline, and what cash is actually available — plus what each customer really costs to serve and what happens if the biggest one leaves. It stops founders from spending pipeline, from calling project fees ARR, and from discovering concentration risk the month the big account pauses.
--
skills/founder-start/SKILL.md:3:description: Diagnose a solo founder or small bootstrapped SaaS team's current business stage, name the main obstacle in the way, persist that context so future sessions can resume it, and route to the right next founder-skills skill. Use this whenever a founder describes their business, asks "what should I focus on," "am I doing this right," "what's next," or opens a new session about their product/company without a specific narrower ask already in mind. Do not use it for a request that's already scoped to one obstacle (e.g. "help me price this" goes straight to founder-pricing; "why are customers cancelling" goes straight to founder-retention) — founder-start is for when the right next step isn't yet known.
skills/founder-start/SKILL.md-4----
skills/founder-start/SKILL.md-5-
skills/founder-start/SKILL.md-6-## What this skill does
skills/founder-start/SKILL.md-7-
skills/founder-start/SKILL.md-8-Understands where a specific business actually is — not a generic startup stage label, but the real mix of evidence, product state, and constraints — and names one main obstacle and one next experiment. It persists that understanding so the founder doesn't have to re-explain their business every session, and it hands off to whichever of the other 13 founder-skills skills fits that obstacle.
--
skills/founder-review/SKILL.md:3:description: Close an experiment cycle for a bootstrapped B2B SaaS — read what was actually observed, update `.founder/experiments.md`, and choose the next step without treating a technical ship as commercial validation. Use this when an observation window has ended, a complement hands work back, the founder asks "did that work," "what should we do next," or a session resumes mid-experiment. Do not use it for a first diagnosis (founder-start), to decide persist vs. pivot vs. shut down as a strategy exercise (founder-pivot), or to start a new acquisition push (founder-growth) — especially not because churn is high.
skills/founder-review/SKILL.md-4----
skills/founder-review/SKILL.md-5-
skills/founder-review/SKILL.md-6-## What this skill does
skills/founder-review/SKILL.md-7-
skills/founder-review/SKILL.md-8-Reads the running experiment against the evidence that actually showed up, records the decision, and names the next action. Technical delivery from a complement (a merged PR, a deployed feature, a passing test suite) closes only the **technical acceptance criteria** in the handoff. It does not conclude the commercial experiment. That experiment stays **running** until the commercial metric has been observed over its window.
--
skills/founder-validate/SKILL.md:3:description: Form a customer/problem hypothesis for a bootstrapped B2B SaaS, run interviews and demand experiments, and attach an evidence tier (stated intent, commitment, payment, or recurring use) to whatever is actually observed. Use this when the founder has an idea or a ready product with no commercial validation, asks "is this a real problem," "should I talk to users," or wants to test demand before (or instead of) building. Do not use it to map existing code (founder-product-audit), to write positioning copy (founder-positioning), to set a price (founder-pricing), or to design the build (founder-mvp) — demand evidence first.
skills/founder-validate/SKILL.md-4----
skills/founder-validate/SKILL.md-5-
skills/founder-validate/SKILL.md-6-## What this skill does
skills/founder-validate/SKILL.md-7-
skills/founder-validate/SKILL.md-8-Turns a fuzzy "people will want this" into a customer/problem hypothesis that can be falsified, then gathers evidence through conversations and demand experiments. Every claim is tagged with an evidence tier. Missing evidence stays missing.
--
skills/founder-retention/SKILL.md:3:description: Analyze cohorts, cancellations, renewals, and expansion for a bootstrapped B2B SaaS so paying customers stay and grow. Use this when customers cancel, don't renew, go quiet after buying, or when the founder asks "why are we churning," "is our retention healthy," or "how do we expand accounts." Do not use it to get new users to first value (founder-activation), to change packaging or price (founder-pricing), or to find new customers (founder-growth) — retention and acquisition are separate problems with separate causes, and this skill never answers churn with "get more customers."
skills/founder-retention/SKILL.md-4----
skills/founder-retention/SKILL.md-5-
skills/founder-retention/SKILL.md-6-## What this skill does
skills/founder-retention/SKILL.md-7-
skills/founder-retention/SKILL.md-8-Turns cancellation and renewal reality into a cohort read the founder can act on: who leaves, when, why, and what — if anything — keeps comparable customers staying and spending more. It treats retention (customers staying) and expansion (customers spending more) as distinct outcomes with distinct evidence, and it treats acquisition as a different problem entirely.
--
skills/founder-pricing/SKILL.md:3:description: Set packaging and price hypotheses for a bootstrapped B2B SaaS and test willingness and ability to pay, keeping recurring revenue, one-off services, pipeline, and cash as separate numbers. Use this when the founder asks "what should we charge," "how do we package this," "are they willing to pay," or when free users are not converting. Do not use it to write the offer or differentiation (founder-positioning), to model full unit economics and runway (founder-economics), or to treat a listed price as proof of demand (founder-validate).
skills/founder-pricing/SKILL.md-4----
skills/founder-pricing/SKILL.md-5-
skills/founder-pricing/SKILL.md-6-## What this skill does
skills/founder-pricing/SKILL.md-7-
skills/founder-pricing/SKILL.md-8-Produces a packaging structure and a price hypothesis, then a test that can observe willingness to pay and ability to pay. It labels money as **recurring**, **one-off**, **pipeline**, or **cash** — those are not interchangeable. A price on a page is not payment. Payment is not recurring use.
--
skills/founder-product-audit/SKILL.md:3:description: Map what a founder's product actually does — implemented flows, verified behavior, and commercial hypotheses — by inspecting the code, live product, or manual delivery when any of those exist, and name technical blockers only when they obstruct a business experiment. Use this when the founder has a prototype or shipped product and asks "what's actually built," "audit the product," "should we rebuild," or needs a product map before the next commercial step. Do not use it to validate demand or talk to customers (founder-validate), to design the smallest next experiment (founder-mvp), or to diagnose why users drop off after signup (founder-activation).
skills/founder-product-audit/SKILL.md-4----
skills/founder-product-audit/SKILL.md-5-
skills/founder-product-audit/SKILL.md-6-## What this skill does
skills/founder-product-audit/SKILL.md-7-
skills/founder-product-audit/SKILL.md-8-Produces a product map of what exists today: the user/buyer flows, the capabilities behind them, and — for each — whether it is implemented, verified to work, or still a commercial hypothesis wearing a feature's clothes. If code is present, it inspects the code. Technical blockers are listed only when they stop a named business experiment, not because the stack is unfashionable.

hook: PostToolUse
hook: PostToolUse
hook: PostToolUse Completed
hook: PostToolUse Completed
hook: PreToolUse
hook: PreToolUse Completed
exec
/bin/zsh -lc 'cat skills/founder-start/SKILL.md skills/founder-validate/SKILL.md' in /private/tmp/eval-runs-codex/E04
 succeeded in 0ms:
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

6. **Detect installed complements without installing anything.** Check whether Matt Pocock Skills, Superpowers, or gstack are present in this environment. Record what's detected and, if the founder has already been using one of them for technical work, note that as their standing preference — re-check only on a material change or conflict, not every session.

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
---
name: founder-validate
description: Form a customer/problem hypothesis for a bootstrapped B2B SaaS, run interviews and demand experiments, and attach an evidence tier (stated intent, commitment, payment, or recurring use) to whatever is actually observed. Use this when the founder has an idea or a ready product with no commercial validation, asks "is this a real problem," "should I talk to users," or wants to test demand before (or instead of) building. Do not use it to map existing code (founder-product-audit), to write positioning copy (founder-positioning), to set a price (founder-pricing), or to design the build (founder-mvp) — demand evidence first.
---

## What this skill does

Turns a fuzzy "people will want this" into a customer/problem hypothesis that can be falsified, then gathers evidence through conversations and demand experiments. Every claim is tagged with an evidence tier. Missing evidence stays missing.

It does not invent interviews, customers, quotes, or metrics. It does not treat a shipped product, a waitlist, or a compliment as demand.

## When to use it / when not to

Use it for idea with no product, ready product with no commercial validation, or when existing "validation" is only stated intent. Use it when the founder is about to build because they are excited, not because a named customer has a named problem. Do not use it to audit the codebase (`founder-product-audit`), to pick alternatives and an offer (`founder-positioning`), to package and price (`founder-pricing`), or to specify engineering (`founder-mvp`). Do not use it as a substitute for `founder-first-customers` once the hypothesis is specific enough to sell — interviews are not a pipeline.

## Minimum required context

Who the founder *thinks* the user and buyer are, and the problem in their own words — even if both are still hypotheses. If `.founder/context.md` exists, read **Goal**, **Who**, **What exists**, **Evidence**, and **Authorizations**. If contact with real people is not authorized, do not reach out; work from evidence the founder already has, or get authorization first.

## Procedure

1. **Read before asking.** Reuse `.founder/context.md`. Do not re-interview the founder for facts already recorded. If the situation is unnamed, name it with the shared vocabulary (idea with no product / ready product with no commercial validation / problem validated through manual/concierge delivery, etc.).

2. **Write the hypothesis so it can fail.** One customer (user and buyer if different), one problem, one context in which the problem shows up, one current workaround. Mark every part that is not yet evidenced. A hypothesis is not "SMBs need software"; it is specific enough that talking to the wrong person would not confirm it.

3. **Inventory evidence at the four tiers — and refuse upgrades.** Record only what has already happened:
   - **Stated intent** — someone said they have the problem or would want a solution. Compliments, "cool idea," and survey maybes live here.
   - **Commitment** — a next step they took: a scheduled call, a trial they actually started, a letter of intent, time on a concierge engagement.
   - **Payment** — money changed hands for this problem being solved (including a paid pilot or a manual service fee). A free trial is not payment.
   - **Recurring use** — they came back and used it (or re-hired the concierge) without being chased.

   A signup is not a commitment. A waitlist is not payment. Isolated payment is not recurring use. If a tier is empty, write "none yet."

4. **Talk to people only with authorization, and only about their world.** If **Authorizations** does not include outbound contact, stop and ask. In conversations, prefer past behavior over hypotheticals: last time the problem happened, what they did, what it cost, whether they already pay for a workaround. Do not pitch the product to collect compliments. Do not write quotes the founder "would have heard." If no conversations have happened, the interview count is zero.

5. **Choose a demand experiment that matches the current tier, not a build.** The experiment exists to move (or fail to move) to the next tier. Examples of shape, not of invented results: a concierge offer for a named problem; a paid pilot with a date and a price; a commitment to a kickoff. Engineering is in scope only if the hypothesis cannot be tested without it — then hand to `founder-mvp`. Do not skip to `founder-mvp` because building feels like progress.

6. **Log the experiment** in `.founder/experiments.md` (or `.founder/experiments/<name>.md` if the workspace already uses one file per experiment — pick one layout and keep it):

   ```markdown
   ## <short experiment name> — <date started>

   **Status:** running / concluded / superseded (if superseded, by which entry and why)

   **Hypothesis:** the specific, falsifiable customer/problem claim.

   **Action:** what will actually be done (conversations, offer, concierge, pilot).

   **Owner:** who is driving it.

   **Cost:** money and/or time, even if rough.

   **Metric:** how we will know the tier moved — a count of commitments, payments, or recurring use, not "interest."

   **Observation window:** when the metric is read. Not open-ended.

   **Evidence:** observed facts at the end of the window — or "window still open." Never a made-up number.

   **Decision:** fill only when the window has been read.
   ```

7. **Update `.founder/context.md`.** Refresh **Who**, **Problem** (still a hypothesis until evidenced), and **Evidence**. Leave empty tiers as "none yet."

8. **Do not close validation because code shipped.** A prototype or a launch does not move the evidence tier. Technical delivery is not commercial validation.

## Deliverables

- A written customer/problem hypothesis, with each part marked evidenced or not.
- Evidence listed at the four tiers, including explicit "none yet."
- A running or concluded experiment entry in `.founder/experiments.md`.
- Updated `.founder/context.md`.
- A named next skill.

## Judging results / routing the next action

Validation is working if the hypothesis is specific enough to be wrong, and every commercial claim has a tier attached. It failed if the agent invented a customer, upgraded a compliment to a commitment, or recommended building because interviews felt slow.

Route:
- Hypothesis still vague or only stated intent → stay here, or get contact authorization.
- Problem confirmed via manual/concierge delivery → `founder-mvp` for the smallest useful product, not a rebuild.
- Customer and problem clear, offer fuzzy → `founder-positioning`.
- Willingness/ability to pay is the open question → `founder-pricing`.
- Named prospects, authorized outreach → `founder-first-customers`.
- Ready product, still no demand evidence → do **not** treat shipped as validated; stay here or go to `founder-first-customers`.

## Working with no complements installed

Conversations, notes, and the experiment log are the whole path. No CRM, survey tool, or analytics required. If the founder has no one to talk to, the next action is finding authorized conversations — not installing software and not starting a build.

## Complement integration

This skill's work is commercial. Complements are optional and never a substitute for evidence:

- gstack `office-hours` / `plan-ceo-review` only when the founder wants an adversarial pass on whether the hypothesis is worth pursuing — after the evidence is written down, not instead of gathering it.
- Do not send validation work to `to-spec`, `writing-plans`, or `ship`. Those are for a later product change, via `founder-mvp`, and they do not close this experiment.

Never install packages. Never invent research from a corpus or from "typical SaaS customers." Load `docs/integration/` guides only when the matching package is present.

hook: PostToolUse
hook: PostToolUse
hook: PostToolUse Completed
hook: PostToolUse Completed
hook: PreToolUse
hook: PreToolUse Completed
exec
/bin/zsh -lc 'rg --files --hidden .founder' in /private/tmp/eval-runs-codex/E04
 exited 2 in 0ms:
rg: .founder: IO error for operation on .founder: No such file or directory (os error 2)

hook: PostToolUse
hook: PostToolUse
hook: PostToolUse Completed
hook: PostToolUse Completed
codex
I’m using the founder-start skill. Your testing gives us evidence that the product works for you; the missing piece is what prospective buyers have done so far. That determines whether the next move is testing demand or selling a specific offer.
hook: PreToolUse
hook: PreToolUse Completed
exec
/bin/zsh -lc "rg --files --hidden -g '"'!skills/**'"' -g '"'!.git/**'"' -g '"'!node_modules/**'"' -g '"'!vendor/**'"'" in /private/tmp/eval-runs-codex/E04
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
/private/tmp/eval-runs-codex/E04/.founder/context.md
diff --git a/.founder/context.md b/.founder/context.md
new file mode 100644
index 0000000000000000000000000000000000000000..e50f18695cf5b3e10fd7fd61c23e9ad8a3d63ae4
--- /dev/null
+++ b/.founder/context.md
@@ -0,0 +1,35 @@
+# Founder context
+
+Last updated: 2026-09-16
+
+## Goal
+Start generating product revenue.
+
+## Who
+- User: unknown.
+- Buyer: unknown.
+- Problem: unknown; product includes a core matching feature.
+
+## What exists
+Founder reports a nearly finished product with full authentication, working billing, and end-to-end matching, personally tested for weeks. No product code is present in this workspace; behavior has not been independently verified. Provisional situation: ready product with no commercial validation reported. Publication status unknown.
+
+## Evidence
+- Stated intent: none yet reported.
+- Commitment: none yet reported.
+- Payment: none yet reported; functional billing is technical evidence only.
+- Recurring use: none yet reported from customers; founder self-testing only.
+
+## Constraints
+Time, budget, delivery capacity, and revenue target unknown.
+
+## Authorizations
+Advice requested. Outbound contact, publishing, spend, and production actions unset.
+
+## Existing docs, tools, processes
+- [Workspace instructions](../AGENTS.md)
+
+## Complements detected
+Superpowers and gstack available in session skill catalog. No standing preference reported. Matt Pocock skills not detected.
+
+## Diagnosis and next step
+The main unresolved obstacle is customer demand evidence. Route to founder-validate after clarifying buyer, problem, and existing customer behavior. Proposed next experiment: a bounded week of conversations with one prospective customer segment, investigating recent matching problems and seeking a concrete next step. Specific hypothesis and success threshold await those missing facts; no experiment has started.

hook: PostToolUse
hook: PostToolUse Completed
diff --git a/.founder/context.md b/.founder/context.md
new file mode 100644
index 0000000000000000000000000000000000000000..e50f18695cf5b3e10fd7fd61c23e9ad8a3d63ae4
--- /dev/null
+++ b/.founder/context.md
@@ -0,0 +1,35 @@
+# Founder context
+
+Last updated: 2026-09-16
+
+## Goal
+Start generating product revenue.
+
+## Who
+- User: unknown.
+- Buyer: unknown.
+- Problem: unknown; product includes a core matching feature.
+
+## What exists
+Founder reports a nearly finished product with full authentication, working billing, and end-to-end matching, personally tested for weeks. No product code is present in this workspace; behavior has not been independently verified. Provisional situation: ready product with no commercial validation reported. Publication status unknown.
+
+## Evidence
+- Stated intent: none yet reported.
+- Commitment: none yet reported.
+- Payment: none yet reported; functional billing is technical evidence only.
+- Recurring use: none yet reported from customers; founder self-testing only.
+
+## Constraints
+Time, budget, delivery capacity, and revenue target unknown.
+
+## Authorizations
+Advice requested. Outbound contact, publishing, spend, and production actions unset.
+
+## Existing docs, tools, processes
+- [Workspace instructions](../AGENTS.md)
+
+## Complements detected
+Superpowers and gstack available in session skill catalog. No standing preference reported. Matt Pocock skills not detected.
+
+## Diagnosis and next step
+The main unresolved obstacle is customer demand evidence. Route to founder-validate after clarifying buyer, problem, and existing customer behavior. Proposed next experiment: a bounded week of conversations with one prospective customer segment, investigating recent matching problems and seeking a concrete next step. Specific hypothesis and success threshold await those missing facts; no experiment has started.

codex
Getting auth, billing, and matching working end to end is a substantial milestone. You have something you can put in front of a buyer.

**Your next move is to test a specific customer’s willingness to pay.** Your weeks of testing support technical readiness; customer demand is still unknown from what you’ve shared.

I’d propose a one-week experiment:

1. Pick one narrow group with a matching problem.
2. Talk to five people about the last time they faced it: what they did, what failed, and what it cost them.
3. Where your product fits, demonstrate it using their real situation and offer a paid pilot with a clear outcome, price, and start date.

Track concrete next steps and actual payments. Use those conversations to decide what needs changing.

The next skill is **founder-validate**, pending two details: **Who does your product match, who pays, and has anyone besides you tried it or committed to using it?**
diff --git a/.founder/context.md b/.founder/context.md
new file mode 100644
index 0000000000000000000000000000000000000000..e50f18695cf5b3e10fd7fd61c23e9ad8a3d63ae4
--- /dev/null
+++ b/.founder/context.md
@@ -0,0 +1,35 @@
+# Founder context
+
+Last updated: 2026-09-16
+
+## Goal
+Start generating product revenue.
+
+## Who
+- User: unknown.
+- Buyer: unknown.
+- Problem: unknown; product includes a core matching feature.
+
+## What exists
+Founder reports a nearly finished product with full authentication, working billing, and end-to-end matching, personally tested for weeks. No product code is present in this workspace; behavior has not been independently verified. Provisional situation: ready product with no commercial validation reported. Publication status unknown.
+
+## Evidence
+- Stated intent: none yet reported.
+- Commitment: none yet reported.
+- Payment: none yet reported; functional billing is technical evidence only.
+- Recurring use: none yet reported from customers; founder self-testing only.
+
+## Constraints
+Time, budget, delivery capacity, and revenue target unknown.
+
+## Authorizations
+Advice requested. Outbound contact, publishing, spend, and production actions unset.
+
+## Existing docs, tools, processes
+- [Workspace instructions](../AGENTS.md)
+
+## Complements detected
+Superpowers and gstack available in session skill catalog. No standing preference reported. Matt Pocock skills not detected.
+
+## Diagnosis and next step
+The main unresolved obstacle is customer demand evidence. Route to founder-validate after clarifying buyer, problem, and existing customer behavior. Proposed next experiment: a bounded week of conversations with one prospective customer segment, investigating recent matching problems and seeking a concrete next step. Specific hypothesis and success threshold await those missing facts; no experiment has started.

hook: Stop
hook: Stop
hook: Stop Completed
hook: Stop Completed
tokens used
19,801
Getting auth, billing, and matching working end to end is a substantial milestone. You have something you can put in front of a buyer.

**Your next move is to test a specific customer’s willingness to pay.** Your weeks of testing support technical readiness; customer demand is still unknown from what you’ve shared.

I’d propose a one-week experiment:

1. Pick one narrow group with a matching problem.
2. Talk to five people about the last time they faced it: what they did, what failed, and what it cost them.
3. Where your product fits, demonstrate it using their real situation and offer a paid pilot with a clear outcome, price, and start date.

Track concrete next steps and actual payments. Use those conversations to decide what needs changing.

The next skill is **founder-validate**, pending two details: **Who does your product match, who pays, and has anyone besides you tried it or committed to using it?**
