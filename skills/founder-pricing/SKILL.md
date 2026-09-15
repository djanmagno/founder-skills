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
