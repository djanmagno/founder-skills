Reading additional input from stdin...
OpenAI Codex v0.154.0
--------
workdir: /private/tmp/eval-runs-codex/E07
model: gpt-6-astra
provider: openai
approval: never
sandbox: workspace-write [workdir, /tmp, $TMPDIR]
reasoning effort: low
reasoning summaries: none
session id: 01a0a747-2dcd-7223-8b33-baf56921a646
--------
user
We've got 15 paying customers for CrewSync but lost 6 of them last quarter — most just said something like "we weren't really using it" when they cancelled. I'm thinking now's the time to really push outbound sales to backfill those losses and keep growing. Should I start hiring for that or doing it myself?
warning: Skill descriptions were shortened to fit the skills context budget. Codex can still see every skill, but some descriptions are shorter. Disable unused skills or plugins to leave more room for the rest.
hook: SessionStart
hook: SessionStart Completed
hook: UserPromptSubmit
hook: UserPromptSubmit Completed
codex
I’ll check the relevant strategy skill, then assess whether outbound is the right next move given those cancellations.

hook: PreToolUse
hook: PreToolUse Completed
exec
/bin/zsh -lc 'rg --files skills -g SKILL.md' in /private/tmp/eval-runs-codex/E07
 succeeded in 0ms:
skills/founder-validate/SKILL.md
skills/founder-pricing/SKILL.md
skills/founder-growth/SKILL.md
skills/founder-economics/SKILL.md
skills/founder-review/SKILL.md
skills/founder-first-customers/SKILL.md
skills/founder-mvp/SKILL.md
skills/founder-retention/SKILL.md
skills/founder-pivot/SKILL.md
skills/founder-positioning/SKILL.md
skills/founder-activation/SKILL.md
skills/founder-launch/SKILL.md
skills/founder-start/SKILL.md
skills/founder-product-audit/SKILL.md

hook: PostToolUse
hook: PostToolUse
hook: PostToolUse Completed
hook: PostToolUse Completed
hook: PreToolUse
hook: PreToolUse Completed
exec
/bin/zsh -lc "cat '/Users/user01/.codex/plugins/cache/superpowers-dev/superpowers/6.3.0/skills/using-superpowers/SKILL.md'" in /private/tmp/eval-runs-codex/E07
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
/bin/zsh -lc "awk 'FNR==1 {print \"\\n\" FILENAME} FNR<=12 {print}' skills/*/SKILL.md" in /private/tmp/eval-runs-codex/E07
 succeeded in 0ms:

skills/founder-activation/SKILL.md
---
name: founder-activation
description: Define a new user's first value moment for a bootstrapped B2B SaaS, diagnose where early users drop off, and fix onboarding so more of them reach that value. Use this when signups or trials don't turn into active users, when the founder asks "why do people sign up and disappear," "how do we improve onboarding," or "what is our aha moment." Do not use it for pricing and packaging (founder-pricing), for keeping paying customers over months and expanding accounts (founder-retention), or for getting more visitors in the door (founder-growth) — activation is about users who already arrived reaching first value, not about acquiring more of them.
---

## What this skill does

Names the single first value a new user must experience, finds the step where most of them abandon before reaching it, and runs a small experiment to remove or shrink that drop-off. It works on users who already signed up — free, trial, or newly paying — and it stops once first value is consistently reached. Everything after that (renewal, expansion, long-term habit) belongs to `founder-retention`.

## When to use it / when not to

Use it for: free users with no conversion, trial users who go quiet, new paying customers who never really start using the product, or any "published product with interest but no active use" pattern.

skills/founder-economics/SKILL.md
---
name: founder-economics
description: Model unit economics and cash constraints for a bootstrapped B2B SaaS — recurring revenue, one-off revenue, pipeline, and cash as four distinct numbers, plus margin and customer concentration risk. Use this when the founder asks "are we sustainable," "can we afford this," "what does our revenue actually look like," or when growth is limited by margin, support load, or dependence on one or two customers. Do not use it to set packaging or test willingness to pay (founder-pricing), to choose acquisition channels (founder-growth), or to record shipped code as commercial progress (founder-review) — a completed build is never itself commercial validation, and revenue is never recognized here until money and renewal reality say so.
---

## What this skill does

Produces an honest money picture a solo founder can decide from: what recurs, what was one-off, what is merely pipeline, and what cash is actually available — plus what each customer really costs to serve and what happens if the biggest one leaves. It stops founders from spending pipeline, from calling project fees ARR, and from discovering concentration risk the month the big account pauses.

## When to use it / when not to

Use it for: growth limited by margin or operational capacity, a founder mixing bookings with bank balance, renewal-based planning, hiring or spend decisions, or "we're growing but the account never grows" confusion.

skills/founder-first-customers/SKILL.md
---
name: founder-first-customers
description: Run founder-led prospecting, discovery, demo, proposal, and follow-up to get the first buyers for a bootstrapped B2B SaaS, while honoring the outbound-contact authorization in `.founder/context.md`. Use this when the founder asks "how do I get my first customers," "who do I talk to," "help me demo / propose / follow up," or has a validated problem and no pipeline. Do not use it for repeatable channel experiments or paid acquisition (founder-growth), for launch-day materials and channels (founder-launch), or to invent a customer/problem hypothesis (founder-validate). Do not contact anyone unless authorization is recorded.
---

## What this skill does

Moves a specific offer toward the first customers through prospecting, discovery, demo, proposal, and follow-up. Every outbound step checks **Authorizations** in `.founder/context.md`. Conversations are logged at the real evidence tier. This is founder-led selling, not a growth engine.

## When to use it / when not to

Use it when the buyer and offer are specific enough to name a person, and the obstacle is getting those people into a real conversation or a yes/no. Do not use it when the problem is still unknown (`founder-validate`) or the offer is still mush (`founder-positioning`). Do not use it to scale channels, ads, or content loops — that is `founder-growth` (happy customers with no repeatable acquisition may eventually go there; the first ten do not). Do not use it as a launch checklist (`founder-launch`). Do not use it to answer high churn with more pipeline (`founder-retention`).

skills/founder-growth/SKILL.md
---
name: founder-growth
description: Choose and evaluate acquisition and distribution channels for a bootstrapped B2B SaaS through budgeted experiments with explicit pass/fail criteria. Use this when retention is acceptable but there is no repeatable way to add customers, or when the founder asks "how do we get more customers," "which channel should we try," or "should we run ads / do content / do outbound." Do not use it to stop churn (founder-retention — high churn is never solved by more acquisition), to get existing signups to first value (founder-activation), or to prospect named buyers one by one (founder-first-customers) — growth builds a repeatable channel, not a prospect list and not a leak patch.
---

## What this skill does

Turns "we need more customers" into one budgeted channel experiment at a time: which channel, what it costs, what success looks like before the money is spent, and what the founder will do with either outcome. Every experiment carries an explicit budget and explicit evaluation criteria — there is no open-ended "try marketing" advice here.

## When to use it / when not to

Use it for: happy customers with no repeatable acquisition, consistent retention that needs a second channel, or a founder choosing between channels (outbound, content, partnerships, paid, community platforms like Reddit, organic social / building in public, AI-answer-engine visibility, marketplace) with limited money and time.

skills/founder-launch/SKILL.md
---
name: founder-launch
description: Size a launch to the actual product and audience — readiness, materials, channels, and follow-through — for a solo founder or small bootstrapped B2B SaaS, not a Series B go-to-market. Use this when the founder asks "are we ready to launch," "write a launch checklist," "where should we announce," or has a published product with no acquisition or interest and wants a first telling. Do not use it for founder-led selling of the first named accounts (founder-first-customers), for ongoing acquisition experiments (founder-growth), or to treat shipping/launch day as commercial validation (founder-review).
---

## What this skill does

Produces a launch that is proportional to who will actually hear it and what the product can actually do: a readiness call, the materials to tell those people, the channels that reach them, and a follow-through experiment. Technical delivery is not commercial validation — launching, or shipping to production, does not conclude the experiment. Demand is still read at stated intent / commitment / payment / recurring use after the window.

## When to use it / when not to

Use it when there is something to show a bounded audience (manual service, prototype, or shipped product) and the founder needs to tell that audience once, on purpose. Do not use it as an excuse to skip `founder-validate` on an idea with no product. Do not use it in place of `founder-first-customers` when the work is one-to-one outreach. Do not use it in place of `founder-growth` when the work is repeatable channel tests with budget. Do not apply a company-wide GTM checklist sized for a funded multi-team launch to a founder's first ten users.

skills/founder-mvp/SKILL.md
---
name: founder-mvp
description: Define the smallest useful experiment for a bootstrapped B2B SaaS and specify only the product changes that hypothesis actually requires — engineering last, not first. Use this when the founder asks "what should we build," "is this the MVP," "can we concierge this," or is about to write tickets for a full product. Do not use it to discover the customer/problem (founder-validate), to map what already exists (founder-product-audit), or to treat a shipped feature as commercial validation (founder-review). Never auto-invoke Matt's to-spec or to-tickets; those are explicit-invocation skills — prepare the call for the founder.
---

## What this skill does

Names the smallest useful experiment that can move an evidence tier, and the smallest product (or non-product) change that experiment needs. Interviews, a landing ask, a concierge delivery, or a manual workaround beat a build when they can test the same hypothesis. If engineering is required, this skill writes a handoff with technical acceptance criteria **and** a commercial metric — then stops. Technical delivery is not commercial validation.

## When to use it / when not to

Use it when a hypothesis exists and the founder is choosing what to build, shrink, or skip. Use it for partial prototype needing adjustments when the adjustment is in service of a commercial test. Do not use it as a product-roadmap workshop. Do not use it to skip `founder-validate` on an idea with no customer/problem hypothesis. Do not use it to close an experiment after merge — that is `founder-review`. Do not use it to launch (`founder-launch`) or to prospect (`founder-first-customers`).

skills/founder-pivot/SKILL.md
---
name: founder-pivot
description: Compare persist vs. reposition vs. change segment-or-product vs. shut down from recorded evidence, and preserve the full decision history when the founder changes direction. Use this when the founder asks "should we pivot," "is this working," "should we shut this down," or when repeated experiments keep failing and the hypothesis itself looks wrong. Do not use it to close a single experiment cycle (founder-review), to model cash and margin (founder-economics), or to validate a brand-new idea from scratch (founder-validate) — a pivot decides from the evidence already recorded, and it adds history rather than rewriting it.
---

## What this skill does

Forces the hardest decision through evidence instead of exhaustion: given what has actually been tried and observed, should the founder persist with the current hypothesis, reposition the same product for the same problem, change segment or product, or shut down — and it records that decision so a future session can see what was believed, what disproved it, and what replaced it.

## When to use it / when not to

Use it for: the "need to reposition, pivot, or kill a hypothesis" situation — repeated failed experiments, a segment that won't pay, economics that can't work, or a founder who suspects the problem is the thesis, not the execution.

skills/founder-positioning/SKILL.md
---
name: founder-positioning
description: Compare the alternatives a buyer already uses, name the differentiation that matters to that buyer, and write a clear offer for a bootstrapped B2B SaaS. Use this when the founder asks "how do we describe this," "what's our positioning," "what's the offer," or when validation showed a real problem but prospects cannot tell this apart from the status quo. Do not use it to set price or packaging (founder-pricing), to pick acquisition channels (founder-growth), to write a launch checklist (founder-launch), or to invent demand that founder-validate has not evidenced.
---

## What this skill does

Produces alternatives, differentiation, and an offer: who it is for, the problem, the promised outcome, and who it is not for. The offer is written from evidence already in `.founder/context.md`, in the founder's language for conversation and in the customer's language for materials. It does not invent competitors, quotes, or wins.

## When to use it / when not to

Use it when the customer/problem is specific enough to compare against real alternatives, including "do nothing" and the current workaround (spreadsheet, intern, incumbent tool, agency). Do not use it as a substitute for `founder-validate` — positioning cannot create demand. Do not use it to choose a number or a packaging ladder — that is `founder-pricing` (the offer names what is sold; pricing names what it costs and how it recurs). Do not use it to plan ads or content engines (`founder-growth`) or a go-to-market event (`founder-launch`).

skills/founder-pricing/SKILL.md
---
name: founder-pricing
description: Set packaging and price hypotheses for a bootstrapped B2B SaaS and test willingness and ability to pay, keeping recurring revenue, one-off services, pipeline, and cash as separate numbers. Use this when the founder asks "what should we charge," "how do we package this," "are they willing to pay," or when free users are not converting. Do not use it to write the offer or differentiation (founder-positioning), to model full unit economics and runway (founder-economics), or to treat a listed price as proof of demand (founder-validate).
---

## What this skill does

Produces a packaging structure and a price hypothesis, then a test that can observe willingness to pay and ability to pay. It labels money as **recurring**, **one-off**, **pipeline**, or **cash** — those are not interchangeable. A price on a page is not payment. Payment is not recurring use.

## When to use it / when not to

Use it when the offer is clear enough to put a number on, when conversion from free to paid is the obstacle, or when the founder is mixing project fees with subscription in their head. Do not use it to invent the buyer or the problem (`founder-validate`) or the offer sentence (`founder-positioning` first if "what we sell" is still mushy). Do not use it as a full economics model (margin, concentration, runway) — that is `founder-economics`. Do not use it to add features so the price "feels justified."

skills/founder-product-audit/SKILL.md
---
name: founder-product-audit
description: Map what a founder's product actually does — implemented flows, verified behavior, and commercial hypotheses — by inspecting the code, live product, or manual delivery when any of those exist, and name technical blockers only when they obstruct a business experiment. Use this whenever a founder describes an existing prototype or shipped product and asks what to focus on next, even if they've already summarized what's built in their own words — a founder's summary is not a classification into implemented/verified/hypothesis, and this skill is what produces that classification before any other skill acts on it. Also use it for direct asks like "what's actually built," "audit the product," or "should we rebuild." Do not use it to validate demand or talk to customers (founder-validate), to design the smallest next experiment (founder-mvp), or to diagnose why users drop off after signup (founder-activation).
---

## What this skill does

Produces a product map of what exists today: the user/buyer flows, the capabilities behind them, and — for each — whether it is implemented, verified to work, or still a commercial hypothesis wearing a feature's clothes. If code is present, it inspects the code. Technical blockers are listed only when they stop a named business experiment, not because the stack is unfashionable.

It does not prove demand. A built product is not commercial validation.

## When to use it / when not to

skills/founder-retention/SKILL.md
---
name: founder-retention
description: Analyze cohorts, cancellations, renewals, and expansion for a bootstrapped B2B SaaS so paying customers stay and grow. Use this when customers cancel, don't renew, go quiet after buying, or when the founder asks "why are we churning," "is our retention healthy," or "how do we expand accounts." Do not use it to get new users to first value (founder-activation), to change packaging or price (founder-pricing), or to find new customers (founder-growth) — retention and acquisition are separate problems with separate causes, and this skill never answers churn with "get more customers."
---

## What this skill does

Turns cancellation and renewal reality into a cohort read the founder can act on: who leaves, when, why, and what — if anything — keeps comparable customers staying and spending more. It treats retention (customers staying) and expansion (customers spending more) as distinct outcomes with distinct evidence, and it treats acquisition as a different problem entirely.

## When to use it / when not to

Use it for: paying customers with weak retention or high churn, renewals that need work, accounts that stay but never expand, or "consistent revenue that suddenly wobbles."

skills/founder-review/SKILL.md
---
name: founder-review
description: Close an experiment cycle for a bootstrapped B2B SaaS — read what was actually observed, update `.founder/experiments.md`, and choose the next step without treating a technical ship as commercial validation. Use this when an observation window has ended, a complement hands work back, the founder asks "did that work," "what should we do next," or a session resumes mid-experiment. Do not use it for a first diagnosis (founder-start), to decide persist vs. pivot vs. shut down as a strategy exercise (founder-pivot), or to start a new acquisition push (founder-growth) — especially not because churn is high.
---

## What this skill does

Reads the running experiment against the evidence that actually showed up, records the decision, and names the next action. Technical delivery from a complement (a merged PR, a deployed feature, a passing test suite) closes only the **technical acceptance criteria** in the handoff. It does not conclude the commercial experiment. That experiment stays **running** until the commercial metric has been observed over its window.

## When to use it / when not to

Use it at the end of an observation window, when inbound handoff notes arrive, or when the founder wants a cycle close rather than a new initiative. Do not use it to replace `founder-start` when there is no experiment history. Do not use it to run a persist / reposition / pivot / shut-down comparison — that is `founder-pivot`, which this skill may *route to* after the evidence is written. Do not use it to launch ads or "get more customers" as the default next step.

skills/founder-start/SKILL.md
---
name: founder-start
description: Diagnose a solo founder or small bootstrapped SaaS team's current business stage, name the main obstacle in the way, persist that context so future sessions can resume it, and route to the right next founder-skills skill. Use this whenever a founder describes their business, asks "what should I focus on," "am I doing this right," "what's next," or opens a new session about their product/company without a specific narrower ask already in mind. Do not use it for a request that's already scoped to one obstacle (e.g. "help me price this" goes straight to founder-pricing; "why are customers cancelling" goes straight to founder-retention) — founder-start is for when the right next step isn't yet known.
---

## What this skill does

Understands where a specific business actually is — not a generic startup stage label, but the real mix of evidence, product state, and constraints — and names one main obstacle and one next experiment. It persists that understanding so the founder doesn't have to re-explain their business every session, and it hands off to whichever of the other 13 founder-skills skills fits that obstacle.

It is a diagnosis and a router, not a doer. The actual work of validating demand, pricing, launching, and so on happens in the skill it routes to.

## When to use it / when not to

skills/founder-validate/SKILL.md
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
/bin/zsh -lc 'cat skills/founder-retention/SKILL.md' in /private/tmp/eval-runs-codex/E07
 succeeded in 0ms:
---
name: founder-retention
description: Analyze cohorts, cancellations, renewals, and expansion for a bootstrapped B2B SaaS so paying customers stay and grow. Use this when customers cancel, don't renew, go quiet after buying, or when the founder asks "why are we churning," "is our retention healthy," or "how do we expand accounts." Do not use it to get new users to first value (founder-activation), to change packaging or price (founder-pricing), or to find new customers (founder-growth) — retention and acquisition are separate problems with separate causes, and this skill never answers churn with "get more customers."
---

## What this skill does

Turns cancellation and renewal reality into a cohort read the founder can act on: who leaves, when, why, and what — if anything — keeps comparable customers staying and spending more. It treats retention (customers staying) and expansion (customers spending more) as distinct outcomes with distinct evidence, and it treats acquisition as a different problem entirely.

## When to use it / when not to

Use it for: paying customers with weak retention or high churn, renewals that need work, accounts that stay but never expand, or "consistent revenue that suddenly wobbles."

Do not use it when the problem is users who never reached first value — that's `founder-activation`. Do not use it when nobody is arriving at all — that's acquisition (`founder-growth`, `founder-first-customers`), and reaching for it here is exactly the failure mode this skill guards against (see step 4). Do not use it to decide persist vs. pivot vs. shut down as a strategy — that's `founder-pivot`, which this skill may route to once the retention evidence is written.

## Minimum required context

`.founder/context.md` (buyer, what exists, evidence tiers), plus the customer list as it actually stands: who pays, since when, who cancelled and when, and any stated cancellation reasons. Rough is fine; invented is not — "we have about a dozen paying accounts, four cancelled this quarter, reasons mostly unknown" is a valid starting point. If renewal or cancellation data genuinely doesn't exist, the first experiment may be reconstructing it, not analyzing it.

## Procedure

1. **List customers before computing anything.** Write down paying accounts (count, rough tenure, rough value each — or "unknown" where unknown). No cohort math can precede this list, and no list may be padded with trials, free users, or "warm leads" counted as customers. Evidence tiers apply here: payment and recurring use only.

2. **Build the simplest cohort read the data supports.** Group customers by when they started (month or quarter) and note, per group, how many still pay. With tiny numbers this is a table of names and dates, not a curve — that is fine. With no start dates, say so and reconstruct what can be reconstructed from invoices or memory. Never smooth, annualize, or project a retention rate the underlying list doesn't support. A cohort table with gaps beats a confident-sounding churn percentage built on guesses.

3. **Collect cancellation reasons as evidence, not as anecdotes.** For each lost account, record what was actually said or observed (their words where possible), and mark "reason unknown" where nothing was said. Do not upgrade a polite "we're pausing for now" into a confirmed product diagnosis, and do not let one loud cancellation outweigh five silent ones without saying so. If reasons are mostly unknown, the next experiment is asking — an exit conversation the founder conducts personally, within existing contact authorization — not assuming.

   When the founder runs that exit conversation, coach them toward what actually happened over what the customer thinks in general: walk the specific week or moment the decision to cancel was made, what they were trying to do right before it, what else they tried or considered, and what would have had to be true for them to stay — instead of an abstract "why did you cancel?" that invites a polite, generic answer. A behavioral account of one real cancellation moment is stronger evidence than an opinion about the product.

4. **Guard against the default wrong answer.** State this explicitly in the working notes: **high churn is a retention problem, and retention and acquisition are separate problems with separate causes. Adding more customers on top of a leak does not fix the leak — it hides it while burning acquisition effort and reputation.** Do not recommend `founder-growth`, more outreach, or more top-of-funnel as the response to churn. If the founder asks for that anyway, write down why the retention evidence says otherwise and what would have to change first (which cancellations would need to stop, and why) before acquisition becomes the priority again.

5. **Separate retention from expansion.** Staying (renewal, continued payment, continued use) and growing (more seats, higher tier, additional use cases) are different outcomes with different causes. A customer who renews but never expands is a retention success and an expansion unknown — not an expansion failure. Expansion experiments (a wider rollout, a second team, a higher package) get their own hypothesis, metric, and window; they are never smuggled into a retention read as "proof" retention is fine.

6. **Pick one retention experiment.** From the cohort read and the cancellation evidence, name the single most plausible preventable cause (a missing check-in before renewal, a value gap for a specific segment, support load the founder can't cover — whatever the evidence actually points to), and design one change with one metric: renewals kept, cancellations avoided, or quiet accounts re-engaged over a stated window. One cause, one change, one read. If the evidence points nowhere — reasons unknown, numbers too small to split — the experiment is gathering reasons first, and its metric is "cancellation reasons collected," honestly labeled as groundwork rather than a fix.

7. **Log the experiment** in `.founder/experiments.md` (or `.founder/experiments/<name>.md` — pick the layout already in use and stay consistent):

   ```markdown
   ## <short experiment name> — <date started>

   **Status:** running / concluded / superseded (if superseded, by which entry and why)

   **Hypothesis:** <the specific preventable cause> drives <these cancellations / non-renewals>, and <this specific change> keeps more of <this cohort> paying through <the window>.

   **Action:** the specific change made (or the exit conversations conducted, if reasons are the gap).

   **Owner:** ...

   **Cost:** time and any concession cost (discounts, extra support).

   **Metric:** renewals kept / cancellations in the cohort / reasons collected — labeled as which. Not new signups, not pipeline.

   **Observation window:** when the metric gets read (must cover at least one renewal or cancellation decision point).

   **Evidence:** observed — or "window still open" / "unknown."

   **Decision:** fill after the window.
   ```

8. **Persist the read.** Create or update `.founder/retention.md`:

   ```markdown
   # Retention

   Last updated: <date>

   ## Customer list basis
   <who pays, since when, who left and when — or what is unknown about it>

   ## Cohort read
   <per-start-period table, however rough — never a smoothed rate the list doesn't support>

   ## Cancellation reasons
   <per-account reasons in their words where possible; "unknown" where unknown>

   ## Retention vs expansion
   <what staying vs growing each look like for these accounts, kept as separate questions>

   ## Why acquisition is not the answer here
   <one paragraph: what the retention evidence shows and what would have to change before acquisition becomes the priority>

   ## Experiments
   <links to the relevant `.founder/experiments.md` entries — no copied content>
   ```

   Update `.founder/context.md` **Evidence** only with what was actually observed.

## Deliverables

- A customer list and cohort read with gaps marked, not smoothed over.
- Cancellation reasons recorded as evidence, unknowns labeled.
- An explicit written guard against answering churn with acquisition.
- One retention (or expansion, or reason-gathering) experiment logged with a renewal-window metric.
- `.founder/retention.md`, created or updated.

## Judging results / routing the next action

The work succeeds if the founder can say which customers leave, when, and why — and if the next experiment targets a preventable cause with a metric read at a real renewal point. It fails if churn produced an acquisition plan, if free users or pipeline were counted as retained customers, if one anecdote became the whole diagnosis, or if expansion was claimed without a separate experiment.

Route from what the window actually showed:
- New users never reach value before they can even churn → `founder-activation`.
- Cancellations cite price or packaging → `founder-pricing`.
- The product genuinely lacks what a whole segment needs → `founder-mvp`, carrying this diagnosis.
- Retention is stable and a repeatable way to add customers is the gap → `founder-growth` — only now, with the leak characterized first.
- Margin, cash, or concentration surfaced by the customer list → `founder-economics`.
- Evidence suggests the segment or product itself is wrong → `founder-pivot`.
- Window ended, read the result → `founder-review`.

## Working with no complements installed

Invoices, memory, and a handful of honest exit conversations are the entire toolkit. No analytics platform, CRM, or survey tool is required — a founder who personally asks three cancelled accounts why they left and writes down what they said has done the core of this skill.

## Complement integration

- gstack `office-hours` only if the retention evidence forces a genuinely strategic fork (e.g. a segment must be dropped) — and only after the cohort read is written, so the session reacts to evidence rather than replacing it.
- gstack `browse` / `qa-only` may investigate what a long-lived account actually experiences, as input to the diagnosis — never as the diagnosis itself.
- Load `docs/integration/` guides only when the matching package is actually present. Never install, update, or modify complements.

hook: PostToolUse
hook: PostToolUse
hook: PostToolUse Completed
hook: PostToolUse Completed
hook: PreToolUse
hook: PreToolUse Completed
exec
/bin/zsh -lc "rg --files --hidden -g '"'!'"\\.git/**' -g '"'!skills/**'"'" in /private/tmp/eval-runs-codex/E07
 succeeded in 0ms:
output.txt
AGENTS.md

hook: PostToolUse
hook: PostToolUse
hook: PostToolUse Completed
hook: PostToolUse Completed
codex
I’m using the founder-retention skill. “We weren’t really using it” signals a problem worth investigating, but it doesn’t tell us whether customers never got value or stopped needing CrewSync. I’d resolve that before adding a sales hire.

hook: PreToolUse
hook: PreToolUse Completed
web search: 
web search: site.ycombinator.com library founder sales retention churn product market fit
hook: PostToolUse
hook: PostToolUse Completed
hook: PreToolUse
hook: PreToolUse Completed
exec
/bin/zsh -lc 'mkdir -p .founder' in /private/tmp/eval-runs-codex/E07
 succeeded in 0ms:
hook: PostToolUse
hook: PostToolUse
hook: PostToolUse Completed
hook: PostToolUse Completed
hook: PreToolUse
hook: PreToolUse Completed
apply patch
patch: completed
/private/tmp/eval-runs-codex/E07/.founder/context.md
/private/tmp/eval-runs-codex/E07/.founder/experiments.md
/private/tmp/eval-runs-codex/E07/.founder/retention.md
diff --git a/.founder/context.md b/.founder/context.md
new file mode 100644
index 0000000000000000000000000000000000000000..e7cd38369a38501f4f2b87baf5e5e81d220dd3fe
--- /dev/null
+++ b/.founder/context.md
@@ -0,0 +1,15 @@
+# CrewSync
+
+Updated: 2026-09-16
+
+## Business
+Paying SaaS customers; buyer, product workflows, pricing and cash constraints unknown.
+
+## Evidence
+Founder reports 15 paying customers and six cancellations last quarter. Whether 15 is the current count or the count before losses is unconfirmed. Most cancellations were described approximately as "we weren't really using it"; exact count and account-level quotes unknown. Payment is reported; recurring use and renewal history are unverified.
+
+## Current priority
+Diagnose cancellations before scaling acquisition or hiring sales.
+
+## Authorizations
+Advice and local working notes only. No customer outreach authorized or performed.
diff --git a/.founder/experiments.md b/.founder/experiments.md
new file mode 100644
index 0000000000000000000000000000000000000000..406d8cf0f02c5ac9dbf2a6a1b5b6bd738dc8b052
--- /dev/null
+++ b/.founder/experiments.md
@@ -0,0 +1,21 @@
+# Experiments
+
+## Cancellation reconstruction — 2026-09-16
+
+**Status:** proposed; interviews not started.
+
+**Hypothesis:** Unknown. Low reported use is a symptom; reconstructing actual cancellation decisions may reveal a preventable cause. This is groundwork, not a demonstrated retention fix.
+
+**Action:** Founder reconstructs the paying-account list and personally seeks conversations with all six cancelled customers. Walk through the week of cancellation, the last task attempted, any earlier successful use, what replaced CrewSync and what would have needed to change to stay. Record exact statements separately from inferred causes. Compare with a few retained customers' actual usage and outcomes.
+
+**Owner:** Founder; recommendation awaiting adoption.
+
+**Cost:** Suggested cap of four founder hours; no discounts or additional spend.
+
+**Metric:** Cancellation reasons collected as concrete accounts of behavior; proposed target at least four of six. Nonresponses stay unknown.
+
+**Observation window:** Proposed seven days after adoption, reconstructing each interviewed customer's actual cancellation decision point from last quarter. Any subsequent retention intervention must run through at least one affected account's renewal/cancellation decision.
+
+**Evidence:** Only founder's aggregate report so far; no conversations conducted.
+
+**Decision:** Pending. If customers never reached first value, investigate activation. If they reached value then stopped, select one cause-specific retention intervention with a renewal metric. No acquisition scaling based on interview completion alone.
diff --git a/.founder/retention.md b/.founder/retention.md
new file mode 100644
index 0000000000000000000000000000000000000000..2a5a502f6b1e78dd3915db3f44be0d329c0c8d15
--- /dev/null
+++ b/.founder/retention.md
@@ -0,0 +1,26 @@
+# Retention
+
+Last updated: 2026-09-16
+
+## Customer list basis
+Account-level list unavailable. Founder reports 15 paying customers and six cancellations last quarter. Relationship between those counts is unknown. Names, start dates, tenure, recurring value and renewal dates are unknown. No free users or pipeline included.
+
+## Cohort read
+| Reported group | Count | Start period | Current status |
+| --- | --- | --- | --- |
+| Paying customers | 15 | Unknown | Whether count precedes or follows losses unknown |
+| Cancelled last quarter | 6 | Unknown | Cancelled; individual dates unknown |
+
+No churn rate calculated. Reconstruct one row per real account from invoices: start date, subscription value, last meaningful use, renewal/cancellation date and status.
+
+## Cancellation reasons
+Most reportedly said something like "we weren't really using it." This is the founder's approximate summary, not verified individual quotes. Per-account reasons unknown. Failure to reach initial value, loss of an ongoing need, workflow friction and poor customer fit remain hypotheses.
+
+## Retention vs expansion
+Retention means continued meaningful use and payment through renewal. Neither is verified at the individual-account level. Expansion means additional seats or spend and is unknown; it does not establish retention.
+
+## Why acquisition is not the answer here
+High churn is a retention problem, and retention and acquisition are separate problems with separate causes. Adding more customers on top of a leak does not fix the leak — it hides it while burning acquisition effort and reputation. Six cancellations warrant investigation, even though a rate is not yet supported. Before acquisition becomes the priority, identify the affected customer group and preventable cause, then observe comparable accounts using the product and renewing through a real decision point. A sales hire also needs a founder-proven repeatable sales process and affordable economics, currently unknown.
+
+## Experiments
+See [cancellation reconstruction](experiments.md#cancellation-reconstruction--2026-09-16).

hook: PostToolUse
hook: PostToolUse Completed
diff --git a/.founder/context.md b/.founder/context.md
new file mode 100644
index 0000000000000000000000000000000000000000..e7cd38369a38501f4f2b87baf5e5e81d220dd3fe
--- /dev/null
+++ b/.founder/context.md
@@ -0,0 +1,15 @@
+# CrewSync
+
+Updated: 2026-09-16
+
+## Business
+Paying SaaS customers; buyer, product workflows, pricing and cash constraints unknown.
+
+## Evidence
+Founder reports 15 paying customers and six cancellations last quarter. Whether 15 is the current count or the count before losses is unconfirmed. Most cancellations were described approximately as "we weren't really using it"; exact count and account-level quotes unknown. Payment is reported; recurring use and renewal history are unverified.
+
+## Current priority
+Diagnose cancellations before scaling acquisition or hiring sales.
+
+## Authorizations
+Advice and local working notes only. No customer outreach authorized or performed.
diff --git a/.founder/experiments.md b/.founder/experiments.md
new file mode 100644
index 0000000000000000000000000000000000000000..406d8cf0f02c5ac9dbf2a6a1b5b6bd738dc8b052
--- /dev/null
+++ b/.founder/experiments.md
@@ -0,0 +1,21 @@
+# Experiments
+
+## Cancellation reconstruction — 2026-09-16
+
+**Status:** proposed; interviews not started.
+
+**Hypothesis:** Unknown. Low reported use is a symptom; reconstructing actual cancellation decisions may reveal a preventable cause. This is groundwork, not a demonstrated retention fix.
+
+**Action:** Founder reconstructs the paying-account list and personally seeks conversations with all six cancelled customers. Walk through the week of cancellation, the last task attempted, any earlier successful use, what replaced CrewSync and what would have needed to change to stay. Record exact statements separately from inferred causes. Compare with a few retained customers' actual usage and outcomes.
+
+**Owner:** Founder; recommendation awaiting adoption.
+
+**Cost:** Suggested cap of four founder hours; no discounts or additional spend.
+
+**Metric:** Cancellation reasons collected as concrete accounts of behavior; proposed target at least four of six. Nonresponses stay unknown.
+
+**Observation window:** Proposed seven days after adoption, reconstructing each interviewed customer's actual cancellation decision point from last quarter. Any subsequent retention intervention must run through at least one affected account's renewal/cancellation decision.
+
+**Evidence:** Only founder's aggregate report so far; no conversations conducted.
+
+**Decision:** Pending. If customers never reached first value, investigate activation. If they reached value then stopped, select one cause-specific retention intervention with a renewal metric. No acquisition scaling based on interview completion alone.
diff --git a/.founder/retention.md b/.founder/retention.md
new file mode 100644
index 0000000000000000000000000000000000000000..2a5a502f6b1e78dd3915db3f44be0d329c0c8d15
--- /dev/null
+++ b/.founder/retention.md
@@ -0,0 +1,26 @@
+# Retention
+
+Last updated: 2026-09-16
+
+## Customer list basis
+Account-level list unavailable. Founder reports 15 paying customers and six cancellations last quarter. Relationship between those counts is unknown. Names, start dates, tenure, recurring value and renewal dates are unknown. No free users or pipeline included.
+
+## Cohort read
+| Reported group | Count | Start period | Current status |
+| --- | --- | --- | --- |
+| Paying customers | 15 | Unknown | Whether count precedes or follows losses unknown |
+| Cancelled last quarter | 6 | Unknown | Cancelled; individual dates unknown |
+
+No churn rate calculated. Reconstruct one row per real account from invoices: start date, subscription value, last meaningful use, renewal/cancellation date and status.
+
+## Cancellation reasons
+Most reportedly said something like "we weren't really using it." This is the founder's approximate summary, not verified individual quotes. Per-account reasons unknown. Failure to reach initial value, loss of an ongoing need, workflow friction and poor customer fit remain hypotheses.
+
+## Retention vs expansion
+Retention means continued meaningful use and payment through renewal. Neither is verified at the individual-account level. Expansion means additional seats or spend and is unknown; it does not establish retention.
+
+## Why acquisition is not the answer here
+High churn is a retention problem, and retention and acquisition are separate problems with separate causes. Adding more customers on top of a leak does not fix the leak — it hides it while burning acquisition effort and reputation. Six cancellations warrant investigation, even though a rate is not yet supported. Before acquisition becomes the priority, identify the affected customer group and preventable cause, then observe comparable accounts using the product and renewing through a real decision point. A sales hire also needs a founder-proven repeatable sales process and affordable economics, currently unknown.
+
+## Experiments
+See [cancellation reconstruction](experiments.md#cancellation-reconstruction--2026-09-16).

codex
**I wouldn’t hire for outbound yet. Your next founder-led job is understanding those six cancellations.** More sales could replace the lost revenue temporarily while leaving the reason customers leave unresolved.

“We weren’t really using it” is a symptom. It could mean they never got started, the workflow was too difficult, or the need wasn’t recurring. Each requires a different response. This is consistent with [YC’s advice to establish product-market fit before scaling hiring](https://www.ycombinator.com/blog/the-real-product-market-fit/).

**This week:**

1. **Personally seek conversations with all six cancelled customers.** Aim for four substantive conversations. Ask: “Walk me through the week you decided to cancel. When did CrewSync last help you accomplish something? What do you use now?”
2. **Compare with a few customers who stayed.** What do they repeatedly accomplish with CrewSync, and how are their needs different?
3. **Test one fix based on what you learn.** If customers never reached value, address onboarding. If value faded, investigate why. Judge success by meaningful use and renewal through the next billing decision—not interview completion.

When you can identify who stays and why, and you’ve personally demonstrated a repeatable sales process, revisit hiring. Until then, keep sales founder-led.

I saved the diagnosis and a proposed experiment in [the retention notes](/private/tmp/eval-runs-codex/E07/.founder/retention.md).

**Are the 15 paying customers the ones remaining today, or the count before those six left?** That changes the scale of the losses.
diff --git a/.founder/context.md b/.founder/context.md
new file mode 100644
index 0000000000000000000000000000000000000000..e7cd38369a38501f4f2b87baf5e5e81d220dd3fe
--- /dev/null
+++ b/.founder/context.md
@@ -0,0 +1,15 @@
+# CrewSync
+
+Updated: 2026-09-16
+
+## Business
+Paying SaaS customers; buyer, product workflows, pricing and cash constraints unknown.
+
+## Evidence
+Founder reports 15 paying customers and six cancellations last quarter. Whether 15 is the current count or the count before losses is unconfirmed. Most cancellations were described approximately as "we weren't really using it"; exact count and account-level quotes unknown. Payment is reported; recurring use and renewal history are unverified.
+
+## Current priority
+Diagnose cancellations before scaling acquisition or hiring sales.
+
+## Authorizations
+Advice and local working notes only. No customer outreach authorized or performed.
diff --git a/.founder/experiments.md b/.founder/experiments.md
new file mode 100644
index 0000000000000000000000000000000000000000..406d8cf0f02c5ac9dbf2a6a1b5b6bd738dc8b052
--- /dev/null
+++ b/.founder/experiments.md
@@ -0,0 +1,21 @@
+# Experiments
+
+## Cancellation reconstruction — 2026-09-16
+
+**Status:** proposed; interviews not started.
+
+**Hypothesis:** Unknown. Low reported use is a symptom; reconstructing actual cancellation decisions may reveal a preventable cause. This is groundwork, not a demonstrated retention fix.
+
+**Action:** Founder reconstructs the paying-account list and personally seeks conversations with all six cancelled customers. Walk through the week of cancellation, the last task attempted, any earlier successful use, what replaced CrewSync and what would have needed to change to stay. Record exact statements separately from inferred causes. Compare with a few retained customers' actual usage and outcomes.
+
+**Owner:** Founder; recommendation awaiting adoption.
+
+**Cost:** Suggested cap of four founder hours; no discounts or additional spend.
+
+**Metric:** Cancellation reasons collected as concrete accounts of behavior; proposed target at least four of six. Nonresponses stay unknown.
+
+**Observation window:** Proposed seven days after adoption, reconstructing each interviewed customer's actual cancellation decision point from last quarter. Any subsequent retention intervention must run through at least one affected account's renewal/cancellation decision.
+
+**Evidence:** Only founder's aggregate report so far; no conversations conducted.
+
+**Decision:** Pending. If customers never reached first value, investigate activation. If they reached value then stopped, select one cause-specific retention intervention with a renewal metric. No acquisition scaling based on interview completion alone.
diff --git a/.founder/retention.md b/.founder/retention.md
new file mode 100644
index 0000000000000000000000000000000000000000..2a5a502f6b1e78dd3915db3f44be0d329c0c8d15
--- /dev/null
+++ b/.founder/retention.md
@@ -0,0 +1,26 @@
+# Retention
+
+Last updated: 2026-09-16
+
+## Customer list basis
+Account-level list unavailable. Founder reports 15 paying customers and six cancellations last quarter. Relationship between those counts is unknown. Names, start dates, tenure, recurring value and renewal dates are unknown. No free users or pipeline included.
+
+## Cohort read
+| Reported group | Count | Start period | Current status |
+| --- | --- | --- | --- |
+| Paying customers | 15 | Unknown | Whether count precedes or follows losses unknown |
+| Cancelled last quarter | 6 | Unknown | Cancelled; individual dates unknown |
+
+No churn rate calculated. Reconstruct one row per real account from invoices: start date, subscription value, last meaningful use, renewal/cancellation date and status.
+
+## Cancellation reasons
+Most reportedly said something like "we weren't really using it." This is the founder's approximate summary, not verified individual quotes. Per-account reasons unknown. Failure to reach initial value, loss of an ongoing need, workflow friction and poor customer fit remain hypotheses.
+
+## Retention vs expansion
+Retention means continued meaningful use and payment through renewal. Neither is verified at the individual-account level. Expansion means additional seats or spend and is unknown; it does not establish retention.
+
+## Why acquisition is not the answer here
+High churn is a retention problem, and retention and acquisition are separate problems with separate causes. Adding more customers on top of a leak does not fix the leak — it hides it while burning acquisition effort and reputation. Six cancellations warrant investigation, even though a rate is not yet supported. Before acquisition becomes the priority, identify the affected customer group and preventable cause, then observe comparable accounts using the product and renewing through a real decision point. A sales hire also needs a founder-proven repeatable sales process and affordable economics, currently unknown.
+
+## Experiments
+See [cancellation reconstruction](experiments.md#cancellation-reconstruction--2026-09-16).

hook: Stop
hook: Stop
hook: Stop Completed
hook: Stop Completed
tokens used
25,077
**I wouldn’t hire for outbound yet. Your next founder-led job is understanding those six cancellations.** More sales could replace the lost revenue temporarily while leaving the reason customers leave unresolved.

“We weren’t really using it” is a symptom. It could mean they never got started, the workflow was too difficult, or the need wasn’t recurring. Each requires a different response. This is consistent with [YC’s advice to establish product-market fit before scaling hiring](https://www.ycombinator.com/blog/the-real-product-market-fit/).

**This week:**

1. **Personally seek conversations with all six cancelled customers.** Aim for four substantive conversations. Ask: “Walk me through the week you decided to cancel. When did CrewSync last help you accomplish something? What do you use now?”
2. **Compare with a few customers who stayed.** What do they repeatedly accomplish with CrewSync, and how are their needs different?
3. **Test one fix based on what you learn.** If customers never reached value, address onboarding. If value faded, investigate why. Judge success by meaningful use and renewal through the next billing decision—not interview completion.

When you can identify who stays and why, and you’ve personally demonstrated a repeatable sales process, revisit hiring. Until then, keep sales founder-led.

I saved the diagnosis and a proposed experiment in [the retention notes](/private/tmp/eval-runs-codex/E07/.founder/retention.md).

**Are the 15 paying customers the ones remaining today, or the count before those six left?** That changes the scale of the losses.
