Reading additional input from stdin...
OpenAI Codex v0.154.0
--------
workdir: /private/tmp/eval-runs-codex/E03
model: gpt-6-astra
provider: openai
approval: never
sandbox: workspace-write [workdir, /tmp, $TMPDIR]
reasoning effort: low
reasoning summaries: none
session id: 01a0a742-9c25-7510-a182-15a118f7ffd0
--------
user
I've got about 60% of a product built (Next.js + Postgres) — invoice upload works, the matching algorithm has unit tests and I'm fairly confident in it, but there's no real auth (just a shared password) and no billing. I haven't shown this to any actual customer yet. What should I focus on next?
warning: Skill descriptions were shortened to fit the skills context budget. Codex can still see every skill, but some descriptions are shorter. Disable unused skills or plugins to leave more room for the rest.
hook: SessionStart
hook: SessionStart Completed
hook: UserPromptSubmit
hook: UserPromptSubmit Completed
codex
I’ll check the local skill guidance, then prioritize the next steps around what you most need to learn from customers.

hook: PreToolUse
hook: PreToolUse Completed
exec
/bin/zsh -lc 'rg --files skills -g SKILL.md' in /private/tmp/eval-runs-codex/E03
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
/bin/zsh -lc "awk 'FNR==1 {print \"\\n\" FILENAME} FNR<=18 {print}' skills/founder-{start,mvp,validate,product-audit,first-customers}/SKILL.md" in /private/tmp/eval-runs-codex/E03
 succeeded in 0ms:

skills/founder-start/SKILL.md
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

skills/founder-mvp/SKILL.md
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

skills/founder-validate/SKILL.md
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

skills/founder-product-audit/SKILL.md
---
name: founder-product-audit
description: Map what a founder's product actually does — implemented flows, verified behavior, and commercial hypotheses — by inspecting the code, live product, or manual delivery when any of those exist, and name technical blockers only when they obstruct a business experiment. Use this when the founder has a prototype or shipped product and asks "what's actually built," "audit the product," "should we rebuild," or needs a product map before the next commercial step. Do not use it to validate demand or talk to customers (founder-validate), to design the smallest next experiment (founder-mvp), or to diagnose why users drop off after signup (founder-activation).
---

## What this skill does

Produces a product map of what exists today: the user/buyer flows, the capabilities behind them, and — for each — whether it is implemented, verified to work, or still a commercial hypothesis wearing a feature's clothes. If code is present, it inspects the code. Technical blockers are listed only when they stop a named business experiment, not because the stack is unfashionable.

It does not prove demand. A built product is not commercial validation.

## When to use it / when not to

Use it when something already exists (partial prototype, shipped product, or a real concierge process that *is* the product) and the next decision depends on knowing what is real. Do not use it on an idea with no product — that is `founder-validate`. Do not use it to choose the smallest experiment or to write the engineering change; map the product, then hand the experiment to `founder-mvp`. Do not treat "the code is messy" as a reason to run this skill, or as a reason to rebuild.

## Minimum required context

Enough to find the product: a repo, a URL, screenshots, docs, or a description of the manual delivery. If `.founder/context.md` exists, read it first — especially **What exists**, **Who**, and **Evidence**. If those sections are empty, ask; do not invent a user, a flow, or a usage number to fill the map.

skills/founder-first-customers/SKILL.md
---
name: founder-first-customers
description: Run founder-led prospecting, discovery, demo, proposal, and follow-up to get the first buyers for a bootstrapped B2B SaaS, while honoring the outbound-contact authorization in `.founder/context.md`. Use this when the founder asks "how do I get my first customers," "who do I talk to," "help me demo / propose / follow up," or has a validated problem and no pipeline. Do not use it for repeatable channel experiments or paid acquisition (founder-growth), for launch-day materials and channels (founder-launch), or to invent a customer/problem hypothesis (founder-validate). Do not contact anyone unless authorization is recorded.
---

## What this skill does

Moves a specific offer toward the first customers through prospecting, discovery, demo, proposal, and follow-up. Every outbound step checks **Authorizations** in `.founder/context.md`. Conversations are logged at the real evidence tier. This is founder-led selling, not a growth engine.

## When to use it / when not to

Use it when the buyer and offer are specific enough to name a person, and the obstacle is getting those people into a real conversation or a yes/no. Do not use it when the problem is still unknown (`founder-validate`) or the offer is still mush (`founder-positioning`). Do not use it to scale channels, ads, or content loops — that is `founder-growth` (happy customers with no repeatable acquisition may eventually go there; the first ten do not). Do not use it as a launch checklist (`founder-launch`). Do not use it to answer high churn with more pipeline (`founder-retention`).

## Minimum required context

`.founder/context.md`: **Who**, **Evidence**, **Authorizations**, and the offer if `.founder/positioning.md` / `.founder/pricing.md` exist. If outbound contact is unset or denied, **stop**. Do not assume it is fine to email, LinkedIn, or call. Get an explicit authorization (who, which channel, any spend) and write it into context before the first outreach.

## Procedure

hook: PostToolUse
hook: PostToolUse
hook: PostToolUse Completed
hook: PostToolUse Completed
hook: PreToolUse
hook: PreToolUse Completed
exec
/bin/zsh -lc 'cat skills/founder-start/SKILL.md; if [ -f .founder/context.md ]; then cat .founder/context.md; fi' in /private/tmp/eval-runs-codex/E03
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

hook: PostToolUse
hook: PostToolUse
hook: PostToolUse Completed
hook: PostToolUse Completed
codex
I’m using the **founder-start** skill. Your main uncertainty is whether customers need the matching workflow enough to adopt it; the missing auth and billing matter when they block a concrete customer trial.

hook: PreToolUse
hook: PreToolUse Completed
exec
/bin/zsh -lc "rg --files -g '"'!skills/**'"' -g '"'!node_modules/**'"' -g '"'!package-lock.json'"' -g '"'!yarn.lock'"' -g '"'!pnpm-lock.yaml'"' -g '"'!.git/**'"' -g '"'!*.svg'"' -g '"'!*.png'"' -g '"'!*.jpg'"' -g '"'!*.pdf'"' -g '"'!*.mp4'"' -g '"'!*.woff*'"' -g '"'!*.ico'"' -g '"'!*.jpeg'"' -g '"'!*.webp'"' -g '"'!*.gif'"' -g '"'!*.ttf'"' -g '"'!*.otf'"' -g '"'!*.lock'"' -g '"'!*.csv'"' -g '"'!*.jsonl'"' -g '"'!*.map'"' -g '"'!*.snap'"' -g '"'!*.sum'"' -g '"'!*.mod'"' -g '"'!*.ipynb'"' -g '"'!*.zip'"' -g '"'!*.gz'"' -g '"'!*.tar'"' -g '"'!*.sqlite'"' -g '"'!*.db'"' -g '"'!*.log'"' -g '"'!*.xml'"' -g '"'!*.txt'"' -g '"'!*.yaml'"' -g '"'!*.yml'"' -g '"'!*.toml'"' -g '"'!*.json'"' -g '"'!LICENSE'"' -g '"'!LICENSE.*'"' -g '"'!NOTICE'"' -g '"'!Makefile'"' -g '"'!Dockerfile'"' -g '"'!*.sh'"' -g '"'!*.py'"' -g '"'!*.go'"' -g '"'!*.rs'"' -g '"'!*.java'"' -g '"'!*.c'"' -g '"'!*.h'"' -g '"'!*.cpp'"' -g '"'!*.rb'"' -g '"'!*.php'"' -g '"'!*.sql'"' -g '"'!*.css'"' -g '"'!*.scss'"' -g '"'!*.html'"'" in /private/tmp/eval-runs-codex/E03
 succeeded in 0ms:
AGENTS.md

hook: PostToolUse
hook: PostToolUse
hook: PostToolUse Completed
hook: PostToolUse Completed
hook: PreToolUse
hook: PreToolUse Completed
apply patch
patch: completed
/private/tmp/eval-runs-codex/E03/.founder/context.md
diff --git a/.founder/context.md b/.founder/context.md
new file mode 100644
index 0000000000000000000000000000000000000000..655f5a23cca355f8e5efa71975d12aaaeb2bccdf
--- /dev/null
+++ b/.founder/context.md
@@ -0,0 +1,35 @@
+# Founder context
+
+Last updated: 2026-09-16
+
+## Goal
+Choose the next priority for an approximately 60%-built product. Business and revenue goals unspecified.
+
+## Who
+- User: unknown.
+- Buyer: unknown.
+- Problem: invoice matching appears to be the intended workflow; exact problem and matching targets unconfirmed.
+
+## What exists
+Partial prototype with no commercial validation. Next.js + Postgres. Founder reports working invoice upload, unit tests for matching, confidence in the algorithm, a shared password, and no billing. No product source available in this workspace; implementation and test results have not been independently verified.
+
+## Evidence
+- Stated intent: none yet reported; product has not been shown to actual customers.
+- Commitment: none yet reported.
+- Payment: none yet reported.
+- Recurring use: none yet reported.
+
+## Constraints
+Time, budget, and delivery capacity unspecified. Shared-password access limits readiness for customer self-service with private invoices.
+
+## Authorizations
+Advice requested. Outbound contact, publishing, spend, and production changes unset.
+
+## Existing docs, tools, processes
+- [Workspace instructions](../AGENTS.md)
+
+## Complements detected
+Superpowers and gstack listed in the session skill catalog. Matt Pocock Skills not detected in that catalog. No standing technical workflow preference stated.
+
+## Diagnosis and next experiment
+Main obstacle: missing customer/problem evidence. Next skill: founder-validate. Proposed experiment: within one week, observe five people in one prospective customer segment describe and demonstrate their recent invoice-matching workflow; seek two concrete commitments to a supervised pilot with a scheduled date and suitable sample data. These thresholds are proposed decision rules, not established benchmarks. Confirm user, buyer, and exact matching task first. Defer billing automation; scope authentication to the access required by the pilot.

hook: PostToolUse
hook: PostToolUse Completed
diff --git a/.founder/context.md b/.founder/context.md
new file mode 100644
index 0000000000000000000000000000000000000000..655f5a23cca355f8e5efa71975d12aaaeb2bccdf
--- /dev/null
+++ b/.founder/context.md
@@ -0,0 +1,35 @@
+# Founder context
+
+Last updated: 2026-09-16
+
+## Goal
+Choose the next priority for an approximately 60%-built product. Business and revenue goals unspecified.
+
+## Who
+- User: unknown.
+- Buyer: unknown.
+- Problem: invoice matching appears to be the intended workflow; exact problem and matching targets unconfirmed.
+
+## What exists
+Partial prototype with no commercial validation. Next.js + Postgres. Founder reports working invoice upload, unit tests for matching, confidence in the algorithm, a shared password, and no billing. No product source available in this workspace; implementation and test results have not been independently verified.
+
+## Evidence
+- Stated intent: none yet reported; product has not been shown to actual customers.
+- Commitment: none yet reported.
+- Payment: none yet reported.
+- Recurring use: none yet reported.
+
+## Constraints
+Time, budget, and delivery capacity unspecified. Shared-password access limits readiness for customer self-service with private invoices.
+
+## Authorizations
+Advice requested. Outbound contact, publishing, spend, and production changes unset.
+
+## Existing docs, tools, processes
+- [Workspace instructions](../AGENTS.md)
+
+## Complements detected
+Superpowers and gstack listed in the session skill catalog. Matt Pocock Skills not detected in that catalog. No standing technical workflow preference stated.
+
+## Diagnosis and next experiment
+Main obstacle: missing customer/problem evidence. Next skill: founder-validate. Proposed experiment: within one week, observe five people in one prospective customer segment describe and demonstrate their recent invoice-matching workflow; seek two concrete commitments to a supervised pilot with a scheduled date and suitable sample data. These thresholds are proposed decision rules, not established benchmarks. Confirm user, buyer, and exact matching task first. Defer billing automation; scope authentication to the access required by the pilot.

codex
**Focus next on customer validation.** You have a partial prototype with technical progress, but no evidence yet that customers will adopt it. Unit tests support confidence in the algorithm; customer trials will test whether it solves a valuable problem.

**Your next experiment: spend a week with five potential customers from one specific customer segment.**

- Ask them to walk through the last time they handled this task: what they matched, what went wrong, how long it took, and who owned it.
- Show your existing workflow after understanding theirs.
- Ask for a concrete next step: a scheduled, supervised pilot using suitable sample invoices. Aim for two commitments—not just positive feedback. That’s a proposed decision threshold, not an industry benchmark.

For the unfinished engineering:

| Item | Priority |
|---|---|
| **Auth** | A supervised demo with synthetic data can happen now. Before customers independently access private invoices, add individual authentication and enforce data isolation. |
| **Billing** | Defer automation. Agree on a pilot price and invoice manually if someone commits to paying. |
| **Matching improvements** | Let observed customer examples identify the next gaps. |

The next skill is **founder-validate**; I saved the diagnosis in [.founder/context.md](/private/tmp/eval-runs-codex/E03/.founder/context.md).

**Who do you expect to use this, and what exactly are they matching invoices against?**
diff --git a/.founder/context.md b/.founder/context.md
new file mode 100644
index 0000000000000000000000000000000000000000..655f5a23cca355f8e5efa71975d12aaaeb2bccdf
--- /dev/null
+++ b/.founder/context.md
@@ -0,0 +1,35 @@
+# Founder context
+
+Last updated: 2026-09-16
+
+## Goal
+Choose the next priority for an approximately 60%-built product. Business and revenue goals unspecified.
+
+## Who
+- User: unknown.
+- Buyer: unknown.
+- Problem: invoice matching appears to be the intended workflow; exact problem and matching targets unconfirmed.
+
+## What exists
+Partial prototype with no commercial validation. Next.js + Postgres. Founder reports working invoice upload, unit tests for matching, confidence in the algorithm, a shared password, and no billing. No product source available in this workspace; implementation and test results have not been independently verified.
+
+## Evidence
+- Stated intent: none yet reported; product has not been shown to actual customers.
+- Commitment: none yet reported.
+- Payment: none yet reported.
+- Recurring use: none yet reported.
+
+## Constraints
+Time, budget, and delivery capacity unspecified. Shared-password access limits readiness for customer self-service with private invoices.
+
+## Authorizations
+Advice requested. Outbound contact, publishing, spend, and production changes unset.
+
+## Existing docs, tools, processes
+- [Workspace instructions](../AGENTS.md)
+
+## Complements detected
+Superpowers and gstack listed in the session skill catalog. Matt Pocock Skills not detected in that catalog. No standing technical workflow preference stated.
+
+## Diagnosis and next experiment
+Main obstacle: missing customer/problem evidence. Next skill: founder-validate. Proposed experiment: within one week, observe five people in one prospective customer segment describe and demonstrate their recent invoice-matching workflow; seek two concrete commitments to a supervised pilot with a scheduled date and suitable sample data. These thresholds are proposed decision rules, not established benchmarks. Confirm user, buyer, and exact matching task first. Defer billing automation; scope authentication to the access required by the pilot.

hook: Stop
hook: Stop
hook: Stop Completed
hook: Stop Completed
tokens used
17,177
**Focus next on customer validation.** You have a partial prototype with technical progress, but no evidence yet that customers will adopt it. Unit tests support confidence in the algorithm; customer trials will test whether it solves a valuable problem.

**Your next experiment: spend a week with five potential customers from one specific customer segment.**

- Ask them to walk through the last time they handled this task: what they matched, what went wrong, how long it took, and who owned it.
- Show your existing workflow after understanding theirs.
- Ask for a concrete next step: a scheduled, supervised pilot using suitable sample invoices. Aim for two commitments—not just positive feedback. That’s a proposed decision threshold, not an industry benchmark.

For the unfinished engineering:

| Item | Priority |
|---|---|
| **Auth** | A supervised demo with synthetic data can happen now. Before customers independently access private invoices, add individual authentication and enforce data isolation. |
| **Billing** | Defer automation. Agree on a pilot price and invoice manually if someone commits to paying. |
| **Matching improvements** | Let observed customer examples identify the next gaps. |

The next skill is **founder-validate**; I saved the diagnosis in [.founder/context.md](/private/tmp/eval-runs-codex/E03/.founder/context.md).

**Who do you expect to use this, and what exactly are they matching invoices against?**
