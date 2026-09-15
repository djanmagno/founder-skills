---
name: founder-pivot
description: Compare persist vs. reposition vs. change segment-or-product vs. shut down from recorded evidence, and preserve the full decision history when the founder changes direction. Use this when the founder asks "should we pivot," "is this working," "should we shut this down," or when repeated experiments keep failing and the hypothesis itself looks wrong. Do not use it to close a single experiment cycle (founder-review), to model cash and margin (founder-economics), or to validate a brand-new idea from scratch (founder-validate) — a pivot decides from the evidence already recorded, and it adds history rather than rewriting it.
---

## What this skill does

Forces the hardest decision through evidence instead of exhaustion: given what has actually been tried and observed, should the founder persist with the current hypothesis, reposition the same product for the same problem, change segment or product, or shut down — and it records that decision so a future session can see what was believed, what disproved it, and what replaced it.

## When to use it / when not to

Use it for: the "need to reposition, pivot, or kill a hypothesis" situation — repeated failed experiments, a segment that won't pay, economics that can't work, or a founder who suspects the problem is the thesis, not the execution.

Do not use it to review one experiment's window — that's `founder-review`, which may *escalate here* once the evidence is written. Do not use it as a first diagnosis for a new idea with no history — that's `founder-start` then `founder-validate`. Do not use it to avoid one more honest experiment: if the current hypothesis has never actually been tested (no real ask, no real price, no real trial), the answer is usually "test it first," not "pivot."

## Minimum required context

`.founder/context.md` and `.founder/experiments.md` (or `.founder/experiments/<name>.md`) — the actual history of hypotheses, actions, and observed evidence. Plus `.founder/economics.md` where money constrains the choice. If there is no experiment history, say so: a pivot with no record of what was tried is just a rebrand of guessing, and the first step is reconstructing what can be reconstructed or running the missing test — not choosing from the four options on vibes. Never invent past experiments to justify the decision.

## Procedure

1. **Assemble the evidence trail first.** Before any option is discussed, summarize: which hypotheses were tested, what was actually done, what was observed (tiered: stated intent → commitment → payment → recurring use), and what remains unknown. Mark unknowns as unknowns. If the trail shows the thesis was never really tested — no price put in front of a buyer, no concierge delivery attempted, no channel run inside a budget — name that plainly: the decision may be "run the missing test," not any of the four options below.

2. **Compare exactly four options — no fifth, no blur.** Write each one down with what it keeps and what it discards:
   - **Persist** — same segment, same product, same thesis; the evidence says execution or volume is the gap, not direction. Requires naming the specific experiment that will prove persistence right within one window.
   - **Reposition** — same product and segment, new framing: different promise, different buyer within the same company, different differentiation (`founder-positioning` does the follow-through). Requires naming what evidence says the product is fine but the story misses.
   - **Change segment or product** — a real pivot: a different buyer, a different problem, or a substantially different product for the learning so far. Requires naming which evidence killed the old target and which (thin, honestly labeled) evidence points at the new one. The new direction starts as hypothesis, never as proven.
   - **Shut down** — stop spending on this hypothesis. Requires naming what the founder keeps (learnings, assets, relationships) and what stops (spend, support promises, timelines). Shutting down is a decision with dignity, not a failure to be euphemized — write it plainly.

   Do not merge reposition into pivot or soften shut-down into "pause and hope." Each option gets its own paragraph with its own required evidence.

3. **Decide from the evidence, in the open.** For each option, write which evidence supports it and which contradicts it — including the emotional and sunk-cost pressures, named as pressures rather than hidden inside "strategic" language. The founder decides; the skill makes the trade legible. A rebuild recommendation is allowed only if the evidence shows the product (not the thesis) blocks a direction the evidence otherwise supports — never "rebuild because traction was weak" (see `docs/PLAN.md` §2 principles).

4. **Preserve history — never delete or rewrite it.** The decision is recorded by **adding a new entry** to `.founder/experiments.md` and **marking the superseded entry (or entries) superseded**, with the evidence that changed the founder's mind. Prior entries stay intact: their hypotheses, actions, and evidence are not edited to flatter the new direction.

   ```markdown
   ## <new direction name> — <date started>

   **Status:** running

   **Hypothesis:** the new thesis, marked as hypothesis — even if confidence is high.

   **Action:** what changes starting now (and what explicitly stops).

   **Owner:** ...

   **Cost:** what the change costs and what spend stops.

   **Metric:** the number the new direction lives or dies by, and how it's measured.

   **Observation window:** ...

   **Evidence:** "window still open" until it isn't — never pre-filled.

   **Decision:** fill after the window.
   ```

   And on each superseded entry: change **Status** to `superseded (by <new entry name>, <date>)` and append one line naming the evidence that superseded it. Nothing else in the old entry changes.

5. **Update context without rewriting the past.** Refresh `.founder/context.md` (goal, who, what exists, evidence) to reflect the new direction — but as a new "Last updated" revision, not a rewrite that pretends the old direction never happened. If the founder keeps a changelog or decision log convention of their own, the pivot note goes there too, by link rather than by duplicate copy.

6. **Name the immediate next skill.** A pivot decision without a next experiment is just a mood. Persist names its proving experiment; reposition routes to `founder-positioning`; a new segment routes to `founder-validate`; a new product shape routes to `founder-mvp`; a shutdown names the concrete wind-down steps and stops.

## Deliverables

- A four-option comparison with supporting and contradicting evidence per option, sunk-cost pressures named.
- A founder-made decision recorded as a new experiment entry plus superseded markings on the old ones — history intact, nothing deleted or rewritten.
- Updated `.founder/context.md` as a new revision.
- One named next skill (or explicit wind-down steps).

## Judging results / routing the next action

The work succeeds if a later session can reconstruct what was believed, what disproved it, and what replaced it — without finding edited history. It fails if old entries were deleted or silently rewritten, if the new direction was recorded as proven before its window, if shut-down was euphemized into drift, or if persistence was chosen without naming its proving experiment.

Route from the decision:
- Persist with a proving experiment → run it, then `founder-review`.
- Reposition → `founder-positioning`.
- New segment or problem → `founder-validate`.
- New product shape → `founder-mvp`.
- New money picture needed → `founder-economics` as input to the next cycle.
- Window ended → `founder-review`.

## Working with no complements installed

Nothing here needs any complement. The evidence trail, the four-option comparison, and the history-preserving log entries are all plain writing from files the founder already has.

## Complement integration

- gstack `office-hours` or `plan-ceo-review` may challenge the decision once the four-option comparison is written — input to the founder's choice, never the decision itself, and never a reason to skip writing the comparison first.
- If the new direction needs technical discovery, design, or delivery, that goes through the relevant skill (`founder-mvp`, `founder-product-audit`) with proper handoffs — not from inside this decision. Technical delivery afterward is still not commercial validation.
- Load `docs/integration/` guides only when the matching package is actually present. Never install, update, or modify complements. Never invoke explicit-invocation skills automatically.
