---
name: founder-launch
description: Size a launch to the actual product and audience — readiness, materials, channels, and follow-through — for a solo founder or small bootstrapped B2B SaaS, not a Series B go-to-market. Use this when the founder asks "are we ready to launch," "write a launch checklist," "where should we announce," or has a published product with no acquisition or interest and wants a first telling. Do not use it for founder-led selling of the first named accounts (founder-first-customers), for ongoing acquisition experiments (founder-growth), or to treat shipping/launch day as commercial validation (founder-review).
---

## What this skill does

Produces a launch that is proportional to who will actually hear it and what the product can actually do: a readiness call, the materials to tell those people, the channels that reach them, and a follow-through experiment. Technical delivery is not commercial validation — launching, or shipping to production, does not conclude the experiment. Demand is still read at stated intent / commitment / payment / recurring use after the window.

## When to use it / when not to

Use it when there is something to show a bounded audience (manual service, prototype, or shipped product) and the founder needs to tell that audience once, on purpose. Do not use it as an excuse to skip `founder-validate` on an idea with no product. Do not use it in place of `founder-first-customers` when the work is one-to-one outreach. Do not use it in place of `founder-growth` when the work is repeatable channel tests with budget. Do not apply a company-wide GTM checklist sized for a funded multi-team launch to a founder's first ten users.

## Minimum required context

`.founder/context.md` (who, what exists, evidence, constraints, **Authorizations** for publishing, spend, production). Offer and price if they exist. Product map if it exists — do not launch unverified capabilities as if they were proven. If publishing/production is not authorized, plan the launch but do not execute those steps.

## Procedure

1. **Size the launch to the audience that is real.** First ten users, a community the founder already belongs to, existing waiters, a partner's list — those are different launches from "Product Hunt plus PR plus ads." Write the intended audience as a number and a source the founder can actually reach. If that source is "everyone on the internet," shrink it.

2. **Readiness is whether the named customer can get the promised value, not whether the checklist is long.** Ask only:
   - Can a user in **Who** complete the job the offer promises (implemented + verified, or an honest concierge)?
   - Can we observe the commercial metric we will care about after launch?
   - Are publishing, contact, spend, and production authorized for the steps we intend?
   Missing analytics, a blog, a status page, or a sales deck is not unreadiness for a ten-person launch. A product that cannot deliver first value is unreadiness — route to `founder-mvp` or `founder-activation` design, don't paper over it with copy.

3. **Materials in the user's language, claims inside the evidence.** What the audience will see: a short announcement, a page, an email, a demo path. Generate those in the founder's/customer's language. Do not claim customers, metrics, or logos that are not in `.founder/context.md`. Do not describe hypothesis capabilities as shipped-and-verified.

4. **Channels: only those that reach the sized audience, with cost.** One or few. A channel with spend needs spend authorization. "Post everywhere" is not a plan. If there is no way to reach the audience, the gap is `founder-first-customers` or `founder-validate`, not more assets.

5. **Follow-through is the experiment, not the announcement.** Log in `.founder/experiments.md` before publishing:

   ```markdown
   ## <short experiment name> — <date started>

   **Status:** running

   **Hypothesis:** this audience, told this offer, produces a named next step (reply, call, commitment, payment) within the window.

   **Action:** materials + channels + what we do with responses.

   **Owner:** ...

   **Cost:** time and authorized spend.

   **Metric:** commitments/payments (recurring vs one-off labeled), not impressions, not "we launched."

   **Observation window:** starts at publish; has an end date.

   **Evidence:** window still open until founder-review.

   **Decision:** (empty — shipping the announcement does not fill this)
   ```

6. **Persist a proportional readiness note** in `.founder/launch.md`:

   ```markdown
   # Launch

   Last updated: <date>
   Audience size and source: <...>
   Authorizations used: publishing / contact / spend / production — <each: yes, no, or unset>

   ## Readiness
   - Job the customer must complete:
   - Implemented / verified / still hypothesis:
   - What we are not waiting on (intentionally omitted):

   ## Materials
   - Artifact:
   - Claim it is allowed to make:

   ## Channels
   - Channel:
   - Why it reaches this audience:
   - Cost / authorization:

   ## Follow-through
   - Experiment name:
   - What we do when someone replies:
   - What we do if nobody does (not "buy ads by default"):
   ```

7. **Execute only the authorized steps.** Production deploy, public post, paid placement — each needs its line in **Authorizations**. gstack `ship` is not production; production is separate. After publish, observe. Do not mark the experiment concluded because the post went live.

8. **If nothing happens, diagnose; don't spend.** Published product with no acquisition or interest is a situation, not an ads trigger. Next might be `founder-first-customers`, a tighter offer, or `founder-validate` — decided in `founder-review` from evidence, including "zero replies."

## Deliverables

- `.founder/launch.md` sized to the real audience.
- Materials that do not outrun evidence.
- A running experiment whose metric is not "launched."
- Execution only inside authorization — or an explicit blocked list of steps.
- A named next skill (`founder-review` when the window ends).

## Judging results / routing the next action

Success: a launch a solo founder can finish this week, with a metric that can fail. Failure: a Series-B checklist, invented traction in the copy, deploy-as-validation, or "we need more customers" as the answer to silence or to churn.

Route:
- Not ready to deliver the job → `founder-product-audit` / `founder-mvp`.
- Nobody specific to tell → `founder-validate` / `founder-first-customers`.
- One-to-one selling is the real work → `founder-first-customers`.
- Published, window ended → `founder-review`.
- Users arrive but don't get value → `founder-activation`.
- Repeatable acquisition after a real launch read → `founder-growth`.
- They paid and left → `founder-retention`, not another launch.

## Working with no complements installed

Write the note, the email, the page, in whatever tools the founder already uses. No website, no Product Hunt, no CI. A message to a bounded list the founder is authorized to contact is a valid launch.

## Complement integration

- gstack `ship` / `land-and-deploy` / `canary` only for technical publication, and only with production authorization. They close technical delivery, not the commercial experiment.
- gstack `browse` / `qa-only` to walk the live path before telling people; `qa` only if fixes are in scope.
- Do not invoke `to-spec` / `to-tickets` from a launch; product gaps go to `founder-mvp`.
- Never install packages. Load `docs/integration/` guides only when the matching package is present.
