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
