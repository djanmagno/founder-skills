---
name: founder-positioning
description: Compare the alternatives a buyer already uses, name the differentiation that matters to that buyer, and write a clear offer for a bootstrapped B2B SaaS. Use this when the founder asks "how do we describe this," "what's our positioning," "what's the offer," or when validation showed a real problem but prospects cannot tell this apart from the status quo. Do not use it to set price or packaging (founder-pricing), to pick acquisition channels (founder-growth), to write a launch checklist (founder-launch), or to invent demand that founder-validate has not evidenced.
---

## What this skill does

Produces alternatives, differentiation, and an offer: who it is for, the problem, the promised outcome, and who it is not for. The offer is written from evidence already in `.founder/context.md`, in the founder's language for conversation and in the customer's language for materials. It does not invent competitors, quotes, or wins.

## When to use it / when not to

Use it when the customer/problem is specific enough to compare against real alternatives, including "do nothing" and the current workaround (spreadsheet, intern, incumbent tool, agency). Do not use it as a substitute for `founder-validate` — positioning cannot create demand. Do not use it to choose a number or a packaging ladder — that is `founder-pricing` (the offer names what is sold; pricing names what it costs and how it recurs). Do not use it to plan ads or content engines (`founder-growth`) or a go-to-market event (`founder-launch`).

## Minimum required context

User, buyer, and problem from `.founder/context.md`, plus whatever **Evidence** exists. If those are empty, gather them or route to `founder-validate` / `founder-start`. If `.founder/product-map.md` exists, use it so the offer does not promise unverified capabilities.

## Procedure

1. **Start from evidence, not from a tagline.** Read context (and the product map if present). List the evidence tier the offer is allowed to lean on. An offer that assumes recurring use when the file says "none yet" is fiction — rewrite it down to what is known.

2. **Name the alternatives the buyer already has.** Status quo, do nothing, hire someone, cobble tools, a named incumbent if the founder can point to one they actually lose to. Do not compile a fantasy competitive matrix. If the founder does not know what buyers do today, that is a `founder-validate` gap, not a positioning deliverable.

3. **Differentiate only on what the buyer cares about.** Difference that does not change the job, the risk, or the cost of switching is not positioning. Prefer a difference you can show in a conversation or a concierge delivery over a difference that requires a rebuild. Do not recommend a rewrite so the product can "position upmarket."

4. **Write the offer as a sentence a buyer could reject.** Who it is for, the problem, the outcome, the form (manual service, product, hybrid), and who it is not for. Keep claims inside verified capabilities plus honest hypotheses — mark hypotheses as such. Generate customer-facing wording in the user's language; keep this skill's own files in English.

5. **Check the offer against the situation.** Ready product with no commercial validation still needs demand evidence — a sharper sentence does not replace `founder-validate`. Free users with no conversion may be an offer/pricing problem, not a feature problem. Happy customers with no repeatable acquisition may need this offer made repeatable in `founder-first-customers` / `founder-growth`, not a new product story.

6. **Persist.** Create or update `.founder/positioning.md`:

   ```markdown
   # Positioning and offer

   Last updated: <date>

   ## Buyer and user
   <from context — mark hypothesis vs evidenced>

   ## Problem
   <as evidenced; otherwise labeled hypothesis>

   ## Alternatives the buyer already uses
   - Alternative:
   - Why they stay / switch — only if someone has said or done this; otherwise "unknown"

   ## Differentiation
   - Difference:
   - Why it matters to the buyer:
   - Evidence: <tier or "none yet">

   ## Offer
   For <buyer> who <problem>, we <outcome> by <form>.
   Not for: <...>
   Hypotheses inside this offer: <explicit list>

   ## Claims we will not make yet
   <anything the product map still marks as hypothesis>
   ```

   Update `.founder/context.md` **Who** / **Problem** if the offer tightened them. If the founder will test the offer in conversations, log an experiment in `.founder/experiments.md` with a metric at commitment or payment, not "liked the messaging."

## Deliverables

- `.founder/positioning.md` with alternatives, differentiation, and offer.
- Hypotheses inside the offer listed explicitly.
- Optional experiment log entry if the offer will be tested.
- A named next skill.

## Judging results / routing the next action

The work succeeded if a founder could say the offer out loud and a buyer could decline it for a concrete reason, and if no claim outruns the evidence file. It failed if the document is slogan-only, invents competitors, or treats positioning as proof of demand.

Route:
- Price, packaging, recurring vs one-off still open → `founder-pricing`.
- Offer testable without a build → `founder-first-customers` (if contact is authorized) or `founder-validate`.
- Offer depends on a product change → `founder-mvp`.
- Ready to tell a specific audience, proportionally → `founder-launch`.
- Need to change segment or kill the story → `founder-pivot` after `founder-review`.

## Working with no complements installed

Write the positioning note from context, interviews already recorded, and the product map. No category research subscription required. If alternatives are unknown, go talk (authorized) rather than inventing a landscape.

## Complement integration

gstack `office-hours` or `plan-ceo-review` only for a material strategic fight (wrong segment, category confusion) after the offer is written down. Do not run three equivalent strategy reviews. Do not invoke engineering skills to "build the differentiator" from here — that goes through `founder-mvp`. Never install packages. Load `docs/integration/` guides only when the matching package is present.
