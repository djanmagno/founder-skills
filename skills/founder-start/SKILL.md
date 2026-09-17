---
name: founder-start
description: Diagnose a solo founder or small bootstrapped SaaS team's current business stage, name the main obstacle in the way, persist that context so future sessions can resume it, and route to the right next founder-skills skill. Use this whenever a founder describes their business, asks "what should I focus on," "am I doing this right," "what's next," or opens a new session about their product/company without a specific narrower ask already in mind. Do not use it for a request that's already scoped to one obstacle (e.g. "help me price this" goes straight to founder-pricing; "why are customers cancelling" goes straight to founder-retention) — founder-start is for when the right next step isn't yet known.
---

## What this skill does

Understands where a specific business actually is — not a generic startup stage label, but the real mix of evidence, product state, and constraints — and names one main obstacle and one next experiment. It persists that understanding so the founder doesn't have to re-explain their business every session, and it hands off to whichever of the other 13 founder-skills skills fits that obstacle.

It is a diagnosis and a router, not a doer.

## When to use it / when not to

Use it at the start of a session about the business, or whenever the founder is unsure what to work on next. Do not use it when the founder already knows what they need — send them straight to the specific skill instead of making them sit through a diagnosis they don't need. Do not use it to re-run a full diagnosis every session once `.founder/context.md` already exists and nothing material has changed; read the existing context and confirm briefly instead.

## Minimum required context

None required to start — this skill's job is to build the context. If `.founder/context.md` (or the founder's existing equivalent) already exists, read it first; don't ask questions it already answers.

## Procedure

1. **Check for existing context.** Look for `.founder/context.md` or a workspace convention the founder has already established — reuse what exists rather than imposing `.founder/`. If found, summarize it back briefly and ask only what's changed, rather than re-running the full interview.

2. **Discover the business, without assuming a stack.** Ask about, or infer from available material:
   - What the founder is trying to achieve.
   - Who uses it, who buys it (if different), what problem it solves.
   - What exists today: idea only, manual/concierge delivery, partial prototype, shipped product, shipped product with paying customers.
   - Evidence at each of the four tiers: stated intent, commitment, payment, recurring use. Don't let a founder's optimism upgrade a lower tier to a higher one — a expressed interest is not a commitment, a free trial is not a payment.
   - Constraints: time, money, skills, delivery capacity.
   - Whatever documentation, tools, or process already exists — don't assume GitHub, a specific stack, or formal engineering practice.

3. **If code exists, inspect it — but hand the deep dive to `founder-product-audit` if the codebase is nontrivial.** For a quick look, distinguish three things explicitly: what's implemented, what's actually been verified to work, and what's still a commercial hypothesis dressed up as a feature. A built product proves none of demand, retention, or growth by itself.

4. **Name the situation** (situations can coexist — pick the ones that actually apply, don't force a single label):
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

5. **Name the main obstacle and the next experiment** — singular, not a laundry list. If several situations coexist, pick the one that's actually blocking progress right now, and say why the others aren't the priority yet. Resist recommending a rebuild just because the product lacked traction, or more acquisition just because churn is high — those are default wrong answers the diagnosis exists to prevent.

6. **Detect installed complements without installing anything — and without over-claiming.** Check whether Matt Pocock Skills, Superpowers, or gstack are available to use *for this founder's project* — the project's own available-skills listing, an installed-skills directory inside the project or its host tool's project-scoped config, or the founder telling you directly. Do not treat a package installed somewhere on the operator's machine generally (a global plugin cache, a user-level config unrelated to this project) as "present" for this business — a complement genuinely available in one project is not automatically available in another, and reporting it as present when you only found it by scanning outside the project's own scope is exactly the kind of invented evidence this library exists to prevent. If you can't positively confirm a complement is available *for this project*, record it as "not detected" or "unknown," never as present. Record what's actually detected and, if the founder has already been using one of them for technical work, note that as their standing preference — re-check only on a material change or conflict, not every session.

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

Route to the skill whose primary deliverable matches the named obstacle. When situations coexist, route to the earliest unresolved one in the natural sequence (validate → position/price → build → launch → activate → retain → grow → economics/pivot) unless the founder has a specific reason to work out of order.

## Working with no complements installed

Complement detection in step 6 simply records "none detected" and every downstream skill proceeds on its self-contained path.

## Complement integration

If Matt Pocock Skills, Superpowers, or gstack are detected, load the relevant guide from `docs/integration/` only when a downstream skill actually needs to hand off technical work — `founder-start` itself records what's present but doesn't invoke any of them. Never install, update, or modify those packages. Never call an explicit-invocation skill (like Matt's `to-spec` / `to-tickets`) automatically — that's for the downstream skill preparing a real handoff to decide, with the founder in the loop.
