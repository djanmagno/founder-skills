---
name: founder-economics
description: Model unit economics and cash constraints for a bootstrapped B2B SaaS — recurring revenue, one-off revenue, pipeline, and cash as four distinct numbers, plus margin and customer concentration risk. Use this when the founder asks "are we sustainable," "can we afford this," "what does our revenue actually look like," or when growth is limited by margin, support load, or dependence on one or two customers. Do not use it to set packaging or test willingness to pay (founder-pricing), to choose acquisition channels (founder-growth), or to record shipped code as commercial progress (founder-review) — a completed build is never itself commercial validation, and revenue is never recognized here until money and renewal reality say so.
---

## What this skill does

Produces an honest money picture a solo founder can decide from: what recurs, what was one-off, what is merely pipeline, and what cash is actually available — plus what each customer really costs to serve and what happens if the biggest one leaves. It stops founders from spending pipeline, from calling project fees ARR, and from discovering concentration risk the month the big account pauses.

## When to use it / when not to

Use it for: growth limited by margin or operational capacity, a founder mixing bookings with bank balance, renewal-based planning, hiring or spend decisions, or "we're growing but the account never grows" confusion.

Do not use it to discover willingness to pay — that's `founder-pricing` (this skill consumes real prices, it doesn't set them). Do not use it to pick channels — that's `founder-growth`. Do not use it to decide persist vs. pivot vs. shut down — that's `founder-pivot`, which reads this skill's output as input. And do not use it to re-label engineering progress as revenue: a shipped feature, a merged PR, or a completed build changes cost and capability, never revenue recognition.

## Minimum required context

`.founder/context.md` (customers, prices, constraints), `.founder/pricing.md` if it exists, and the raw money facts: who has paid what, on what cadence, plus current cash and current costs. Precision is welcome; honesty is required — "rough monthly costs, exact cash unknown until I check" is workable, invented MRR is not. If the founder cannot separate one-off project money from subscription money yet, that separation is step 1.

## Procedure

1. **Separate the four numbers — never collapse them.** Write each from actuals, with "none yet" or "unknown" where true:
   - **Recurring revenue** — subscription or contract revenue expected to renew. State the cadence and the renewal evidence (contracts signed, renewals already observed, or hypothesis clearly marked as such). One payment is not recurring revenue; two payments are barely the start of it.
   - **One-off revenue** — setup fees, implementation, concierge, single projects. Real money, but it does not renew and must never be annualized into ARR.
   - **Pipeline** — verbal interest, proposals outstanding, trials in flight. Not revenue of any kind. Listed here so it stops being spent mentally.
   - **Cash** — what is in the account (and firm near-term receivables, labeled as such). Independent of bookings, ARR math, or optimism.

   Do not add these together. Do not present their sum as "revenue." Any sentence that mixes them gets rewritten until each number stands alone.

2. **Recognize revenue conservatively.** A price on a page is not revenue. A signed pilot that hasn't paid is pipeline. A first payment is one-off until renewal behavior exists. A shipped billing page, a completed feature, or a deployed build is technical delivery — it is recorded as cost and capability, never as commercial validation or recognized revenue. When in doubt, the lower tier wins, and the evidence tier (stated intent → commitment → payment → recurring use) is named next to every claim.

3. **Compute margin per customer, roughly.** Revenue per account (recurring, labeled) minus what serving them actually costs: founder time honestly hourly-costed, infrastructure, tools, support load. Solo-founder time given away "free" is the most common hidden cost — price it even roughly or the margin is fiction. If one account consumes half the founder's week for standard-fee revenue, that is the finding, stated plainly.

4. **Name concentration risk explicitly.** What share of recurring revenue comes from the largest one or two accounts, and what happens to cash and runway if each leaves? A business with three customers where one pays 70% does not have a retention rate — it has a key-person risk wearing a SaaS costume. State the scenario in one line each ("if account X pauses, recurring revenue falls by ... and cash covers ... months"). No mitigation theater; the point is seeing it, not solving it in this step.

5. **Sketch scenarios, not forecasts.** Two or three short cash paths from the numbers above (e.g. no new sales / current pace / lose-largest-account), each with runway implications in plain language. These are decision aids, not predictions — no growth curves, no invented close rates, no spreadsheet precision the evidence can't carry. Each scenario says which `.founder/experiments.md` entries would confirm or break it.

6. **Log the read as a decision-aid entry** (economics itself is rarely the "experiment" — it frames the others). If a decision or test follows (a price change, a cost cut, a concentration reduction), that gets its own experiment entry:

   ```markdown
   ## <short experiment name> — <date started>

   **Status:** running / concluded / superseded (if superseded, by which entry and why)

   **Hypothesis:** the specific money claim being tested (e.g. "dropping the lowest-margin account frees N hours without reducing recurring revenue below X").

   **Action:** what was actually done.

   **Owner:** ...

   **Cost:** ...

   **Metric:** one of the four numbers, named — never a blend.

   **Observation window:** ...

   **Evidence:** observed — or "window still open" / "unknown."

   **Decision:** fill after the window.
   ```

7. **Persist the picture.** Create or update `.founder/economics.md`:

   ```markdown
   # Economics

   Last updated: <date>

   ## Four numbers (never collapsed)
   - Recurring revenue: <actual / hypothesis-marked / none yet, with cadence and renewal evidence>
   - One-off revenue: <...>
   - Pipeline: <... — explicitly not revenue>
   - Cash: <...>

   ## Claims we will not make
   <no ARR from one-off work; no revenue from shipped features; no pipeline spent as cash>

   ## Margin per account
   <per-account recurring revenue minus honest serving cost, however rough>

   ## Concentration
   <share of top accounts; one-line fallout scenario each>

   ## Scenarios
   <two or three cash paths with runway implications and the experiments that would confirm or break them>

   ## Experiments
   <links to the relevant `.founder/experiments.md` entries — no copied content>
   ```

   Update `.founder/context.md` **Evidence** and **Constraints** only with observed money facts.

## Deliverables

- Four separated money numbers with renewal and recognition honesty enforced.
- Margin-per-account read with founder time costed.
- Concentration risk stated as fallout scenarios.
- Two or three cash scenarios tied to experiments.
- `.founder/economics.md`, created or updated.

## Judging results / routing the next action

The work succeeds if the founder can say what recurs, what's one-off, what's pipeline, what's cash — and what happens if the biggest account leaves — without blurring any two. It fails if one-off work was annualized, pipeline was treated as revenue, shipped code was recorded as validation, founder time was costed at zero, or concentration went unnamed.

Route from what the picture shows:
- Prices or packaging are the actual lever → `founder-pricing`.
- Acquisition cost breaks the margin → `founder-growth` (with the margin constraint attached).
- Churn threatens the recurring base → `founder-retention` — never more acquisition as the patch.
- Numbers force persist / reposition / change segment-product / shut down → `founder-pivot`, with this file as input.
- A decision was taken, watch its window → `founder-review`.

## Working with no complements installed

A bank balance, invoices, and an honest hour count are the whole input. No accounting software, dashboard, or model template is required — a founder who writes the four numbers on one page and costs their own week has done the core of this skill.

## Complement integration

- gstack `office-hours` or `plan-ceo-review` only if the economics force a genuinely strategic fork (e.g. the model can't sustain the current segment) — after this picture is written, as input, not as the analysis itself.
- Engineering cost questions (build vs buy, infrastructure) may draw on complement estimates via `founder-mvp` handoffs; delivery estimates feed cost, never revenue.
- Load `docs/integration/` guides only when the matching package is actually present. Never install, update, or modify complements.
