---
name: founder-review
description: Close an experiment cycle for a bootstrapped B2B SaaS — read what was actually observed, update `.founder/experiments.md`, and choose the next step without treating a technical ship as commercial validation. Use this when an observation window has ended, a complement hands work back, the founder asks "did that work," "what should we do next," or a session resumes mid-experiment. Do not use it for a first diagnosis (founder-start), to decide persist vs. pivot vs. shut down as a strategy exercise (founder-pivot), or to start a new acquisition push (founder-growth) — especially not because churn is high.
---

## What this skill does

Reads the running experiment against the evidence that actually showed up, records the decision, and names the next action. Technical delivery from a complement (a merged PR, a deployed feature, a passing test suite) closes only the **technical acceptance criteria** in the handoff. It does not conclude the commercial experiment. That experiment stays **running** until the commercial metric has been observed over its window.

## When to use it / when not to

Use it at the end of an observation window, when inbound handoff notes arrive, or when the founder wants a cycle close rather than a new initiative. Do not use it to replace `founder-start` when there is no experiment history. Do not use it to run a persist / reposition / pivot / shut-down comparison — that is `founder-pivot`, which this skill may *route to* after the evidence is written. Do not use it to launch ads or "get more customers" as the default next step.

## Minimum required context

The experiment being reviewed: `.founder/experiments.md` (or `.founder/experiments/<name>.md`) and `.founder/context.md`. If an inbound handoff exists, read it. If there is no experiment log, do not invent one from memory — reconstruct from what the founder can point to, mark unknowns, or send them to `founder-start`.

## Procedure

1. **Load the thread; do not relitigate from scratch.** Read context, the experiment entry, and any inbound handoff. Preserve history: never delete or silently rewrite a prior entry.

2. **Separate three kinds of "done."** For the experiment under review, say which of these is true — they are not interchangeable:
   - **Technical acceptance met** — the handoff's technical criteria were verified (tests, walkthrough, deploy). Record this under the inbound handoff, not as commercial success.
   - **Commercial window still open** — the metric has not been read yet. Status stays **running**. A ship during an open window is not a conclusion.
   - **Commercial metric observed** — the window ended and the evidence section can be filled with what actually happened (including "nothing happened" and "unknown").

3. **Fill Evidence only with observations.** Counts, quotes, payments, cancellations, usage — only if they occurred. If the metric is unknown, write "unknown." Do not estimate to make the entry look complete. Do not upgrade stated intent to commitment, a trial to payment, or one payment to recurring use.

4. **Read churn and traction with the right next skill in mind.** If the evidence is paying customers with weak activation or high churn, the problem is retention/activation, not acquisition. Do **not** default to "get more customers," `founder-growth`, or more top-of-funnel. If the evidence is happy customers with no repeatable acquisition, do not pivot the product without cause. If the evidence is published product with no acquisition or interest, do not increase ads without a hypothesis.

5. **Write the Decision, tied to the evidence.** Continue, stop, change approach, or escalate to `founder-pivot`. Status becomes **concluded** only when the commercial metric was read (or the founder explicitly kills the experiment). If a new hypothesis replaces this one, add a new entry and mark this one **superseded**, with the evidence that changed the founder's mind — history stays intact.

   Update the experiment:

   ```markdown
   ## <short experiment name> — <date started>

   **Status:** running / concluded / superseded (if superseded, by which entry and why)

   **Hypothesis:** (unchanged unless you are recording that it was the wrong hypothesis — then supersede, don't silently edit)

   **Action:** what was actually done, including technical work if any.

   **Owner:** ...

   **Cost:** actuals if known, else the original estimate plus "unknown actuals."

   **Metric:** ...

   **Observation window:** ...

   **Evidence:** what was observed — or "window still open" / "unknown."

   **Decision:** next step, named, justified by the evidence above, not by how the work felt.
   ```

6. **Record inbound technical handoffs without closing commerce.** If a complement returned work, append or keep:

   ```markdown
   ## Handoff result: <short title> — <date>

   **Changes made:** what was actually built or changed.

   **Verification evidence:** tests, checks — specific, not "it works."

   **Open items:** deferred work and why.

   **Links:** spec, tickets, diffs, tests, deploy/PR links.
   ```

   Then: technical criteria may be checked off; the experiment **Status** stays **running** until step 3's commercial read.

7. **Refresh `.founder/context.md`** for anything that actually changed (evidence tiers, constraints, authorizations). Do not fill gaps with invented metrics.

8. **Name one next skill.** Not a backlog.

## Deliverables

- Updated experiment entry (status, evidence, decision).
- Inbound handoff recorded when one exists, without auto-closing the commercial experiment.
- Updated `.founder/context.md` when evidence or situation changed.
- One named next skill, or an explicit "window still open — observe."

## Judging results / routing the next action

The review worked if a later session can see what was tried, what was observed, and why the next step follows. It failed if shipped code was recorded as commercial validation, if empty metrics were filled in, if high churn produced an acquisition recommendation, or if a pivot erased history.

Route from the decision, not from habit:
- Window open → observe; stay on this experiment.
- Demand still unproven → `founder-validate`.
- Offer/price is the gap → `founder-positioning` / `founder-pricing`.
- Product change required by the hypothesis → `founder-mvp`.
- Need named buyers and outreach (authorized) → `founder-first-customers`.
- Launch materials/channels, proportional → `founder-launch`.
- Drop-off before first value → `founder-activation`.
- Cancellations, renewal, expansion → `founder-retention` (not `founder-growth`).
- Repeatable acquisition is the gap, retention is not → `founder-growth`.
- Margin, cash, concentration → `founder-economics`.
- Persist vs. reposition vs. change segment-product vs. shut down → `founder-pivot`.

## Working with no complements installed

Review the log, the context file, and whatever the founder can show (invoices, inboxes, product usage they already have). No analytics suite required. "We don't have dashboards" is not a reason to invent a number or to declare success.

## Complement integration

- gstack `retro` may feed engineering-execution notes into this review. It is input, not a commercial conclusion.
- Inbound handoffs from Matt / Superpowers / gstack are recorded here; do not run a second equivalent planning or review pass.
- Never call `ship`, `qa`, or `to-spec` as part of closing a cycle. Never install packages. Load `docs/integration/` guides only when the matching package is present and the inbound note actually needs them.
