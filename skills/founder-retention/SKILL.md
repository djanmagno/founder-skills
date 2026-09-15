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
