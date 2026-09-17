---
name: founder-growth
description: Choose and evaluate acquisition and distribution channels for a bootstrapped B2B SaaS through budgeted experiments with explicit pass/fail criteria. Use this when retention is acceptable but there is no repeatable way to add customers, or when the founder asks "how do we get more customers," "which channel should we try," or "should we run ads / do content / do outbound." Do not use it to stop churn (founder-retention — high churn is never solved by more acquisition), to get existing signups to first value (founder-activation), or to prospect named buyers one by one (founder-first-customers) — growth builds a repeatable channel, not a prospect list and not a leak patch.
---

## What this skill does

Turns "we need more customers" into one budgeted channel experiment at a time: which channel, what it costs, what success looks like before the money is spent, and what the founder will do with either outcome. Every experiment carries an explicit budget and explicit evaluation criteria — there is no open-ended "try marketing" advice here.

## When to use it / when not to

Use it for: happy customers with no repeatable acquisition, consistent retention that needs a second channel, or a founder choosing between channels (outbound, content, partnerships, paid, community platforms like Reddit, organic social / building in public, AI-answer-engine visibility, marketplace) with limited money and time.

Do not use it when paying customers are churning — retention and acquisition are separate problems with separate causes, and pouring acquisition on top of churn hides the leak while burning effort and reputation. Route that to `founder-retention` first and say why. Do not use it when signups arrive but never activate — that's `founder-activation`. Do not use it for one-by-one prospecting of named buyers with personal outreach — that's `founder-first-customers`. Growth starts where those leave off: a channel that could repeatably bring the next hundred, not the next three.

## Minimum required context

`.founder/context.md` (buyer, problem, offer, constraints, authorizations — especially spend limits and publishing authorization), plus the retention reality: is churn characterized and acceptable? If retention is unknown or leaking, say so and fix the order first — this skill refuses to be the answer to churn. Also needed: what channels, if any, have ever produced a customer, and what each cost in time and money. "None yet, unknown" is valid; invented channel performance is not.

## Procedure

1. **Confirm retention is not the real problem.** Before any channel work, write one paragraph: what is known about churn and renewal, and why acquisition (not retention) is the current constraint. If that paragraph can't be written honestly — cancellations unexplained, renewals wobbling — route to `founder-retention` instead and say so. This check is not a formality.

2. **Narrow to one channel and one audience slice.** From the buyer definition, pick a single channel to test (one outbound motion, one content bet, one partnership, one paid experiment — never three at once) and the specific slice of buyer it should reach. Justify the choice in two lines: why this channel could plausibly reach this buyer, and what has to be true for it to work. A solo founder's time is the scarcest budget — a channel that needs full-time operation to show signal is the wrong first test regardless of its theoretical ceiling.

3. **Set the budget before spending anything.** Every experiment states, up front:
   - **Money budget:** the maximum spend, authorized explicitly by the founder (respect `.founder/context.md` authorizations — never assume spend consent).
   - **Time budget:** founder hours allocated, honestly costed (a "free" channel that eats twenty hours a week is not free).
   - **Stop rule:** what ends the experiment early (budget exhausted, a hard interim read, an authorization boundary hit).

   No budget, no experiment. "Spend a little and see" is not a budget.

4. **Set evaluation criteria before running anything.** For the chosen channel, write down in advance: the metric that decides pass/fail (qualified conversations, trials started, commitments — labeled by evidence tier, never "impressions" or "traffic" alone), the target number, and the observation window. Also write what happens on pass (scale how, with what budget) and on fail (drop the channel or change one variable, named now — not improvised later). Criteria written after the results are in are not criteria.

5. **Run small, observe honestly.** Execute within the budget and the authorization. Record what was actually done and what actually happened — replies, meetings, trials, payments — tiered as stated intent, commitment, payment, recurring use. Do not upgrade attention ("great engagement") into demand. If the window hasn't closed, the evidence section says "window still open" — results are never read early to justify more spend.

6. **Log the experiment** in `.founder/experiments.md` (or `.founder/experiments/<name>.md` — pick the layout already in use and stay consistent):

   ```markdown
   ## <short experiment name> — <date started>

   **Status:** running / concluded / superseded (if superseded, by which entry and why)

   **Hypothesis:** <this channel> repeatably reaches <this buyer slice> because <reason>, producing <metric target> within <window>.

   **Action:** what was actually done (messages sent, posts published, ads run — specific counts).

   **Owner:** ...

   **Cost:** money spent vs budget; time spent vs budget.

   **Metric:** the pre-written pass/fail metric and target. Not impressions, not "learnings" alone.

   **Observation window:** ...

   **Evidence:** observed, tiered — or "window still open" / "none yet."

   **Decision:** fill after the window: scale (with what budget), drop, or change one named variable.
   ```

7. **Persist the channel read.** Create or update `.founder/growth.md`:

   ```markdown
   # Growth

   Last updated: <date>

   ## Retention pre-check
   <the paragraph from step 1 — why acquisition (not retention) is the constraint>

   ## Channels tested
   <per channel: budget set, criteria set, what happened — or "not yet tested">

   ## Current channel
   <the one active bet, its budget, its pass/fail criteria, its window>

   ## Ruled out
   <channels dropped with the evidence that dropped them — history, not shame>

   ## Experiments
   <links to the relevant `.founder/experiments.md` entries — no copied content>
   ```

   Update `.founder/context.md` authorizations if spend or publishing consent changed.

## Deliverables

- A retention pre-check paragraph justifying acquisition as the current work.
- One channel experiment with an explicit money budget, time budget, stop rule, pass/fail metric, and observation window — all written before spend.
- `.founder/growth.md`, created or updated, including ruled-out channels with their evidence.

## Judging results / routing the next action

The work succeeds if the founder spent a bounded amount to learn a crisp pass/fail about one channel — including a clean fail that rules the channel out. It fails if spend was open-ended, if criteria were written after the fact, if vanity metrics stood in for demand, or if the experiment was really a churn patch wearing a growth costume.

Route from what the window actually showed:
- Channel produced signups that never activate → `founder-activation`.
- Prospects arrive but won't pay the price → `founder-pricing`.
- Response says the offer or positioning misses → `founder-positioning`.
- Named-buyer outreach is still the right motion → `founder-first-customers`.
- Channel economics (cost per acquired customer vs margin) look broken → `founder-economics`.
- Churn surfaced mid-experiment → stop and go to `founder-retention`; do not out-spend the leak.
- Window ended, read the result → `founder-review`.

## Working with no complements installed

Channel experiments need no special tooling: personal outreach within authorization, a few posts, a small paid test inside an explicit budget, a partnership conversation. "We have no marketing stack" is normal for this audience, not a blocker.

## Complement integration

- gstack `office-hours` only if the channel choice is a genuinely strategic fork (e.g. paid vs partnership as the company's bet for the year) after the options and budgets are written — input to the decision, not a replacement for it.
- Publishing, contacts, and spend always respect current authorization and project flow. Load `docs/integration/` guides only when the matching package is actually present. Never install, update, or modify complements.
