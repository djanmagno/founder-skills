---
name: founder-first-customers
description: Run founder-led prospecting, discovery, demo, proposal, and follow-up to get the first buyers for a bootstrapped B2B SaaS, while honoring the outbound-contact authorization in `.founder/context.md`. Use this when the founder asks "how do I get my first customers," "who do I talk to," "help me demo / propose / follow up," or has a validated problem and no pipeline. Do not use it for repeatable channel experiments or paid acquisition (founder-growth), for launch-day materials and channels (founder-launch), or to invent a customer/problem hypothesis (founder-validate). Do not contact anyone unless authorization is recorded.
---

## What this skill does

Moves a specific offer toward the first customers through prospecting, discovery, demo, proposal, and follow-up. Every outbound step checks **Authorizations** in `.founder/context.md`. Conversations are logged at the real evidence tier. This is founder-led selling, not a growth engine.

## When to use it / when not to

Use it when the buyer and offer are specific enough to name a person, and the obstacle is getting those people into a real conversation or a yes/no. Do not use it when the problem is still unknown (`founder-validate`) or the offer is still mush (`founder-positioning`). Do not use it to scale channels, ads, or content loops — that is `founder-growth` (happy customers with no repeatable acquisition may eventually go there; the first ten do not). Do not use it as a launch checklist (`founder-launch`). Do not use it to answer high churn with more pipeline (`founder-retention`).

## Minimum required context

`.founder/context.md`: **Who**, **Evidence**, **Authorizations**, and the offer if `.founder/positioning.md` / `.founder/pricing.md` exist. If outbound contact is unset or denied, **stop**. Do not assume it is fine to email, LinkedIn, or call. Get an explicit authorization (who, which channel, any spend) and write it into context before the first outreach.

## Procedure

1. **Authorization gate — every time, not once per project.** Read **Authorizations**. If outbound contact is not recorded, ask and wait. If authorization is limited (named list, no cold email, no production tenants), stay inside it. Publishing, spend, and production are separate gates; a "yes" to talking is not a yes to deploying or charging a card without the matching line.

2. **Name who is allowed to be sought.** User vs buyer from context. Prospecting criteria come from evidenced who/problem, not from an invented ICP. If the founder cannot point to a way those people are findable, that is a research gap for `founder-validate`, not a reason to scrape strangers.

3. **Prospect in small batches, starting from who actually trusts the founder.** A list the founder can actually work. For each prospect: why they might have the problem (a public fact or a founder relationship — not a fabricated pain story), the channel authorized, the next action. Do not send volume to cover a weak offer.

   Work outward in the order that actually converts at this stage: personal network and one-degree-removed introductions first (they're taking a bet on the founder, not yet on the product, so trust matters more than polish); then whatever "doesn't scale" — a direct message where the buyer already hangs out, showing up in person, a small session offered to a handful of prospects — once the warm list runs out. Save list-building and outreach tooling for after a first real batch of customers is already won; reaching for volume tools before that usually means avoiding the harder, slower conversations that actually convert this early. Before picking any channel at all, get concrete about where this specific buyer already spends their attention — the default of cold email/LinkedIn fits some buyers and badly fits others (a channel mismatch reads as "outreach doesn't work" when it's really "wrong venue").

4. **Discovery before demo.** First conversations are about their last occurrence of the problem, current workaround, and who pays — same discipline as `founder-validate`. Do not pitch through the discovery. Record what they said; do not write what they "would say." Compliments stay **stated intent**. A booked next step is **commitment**.

5. **Demo only what is implemented and honest about the rest.** If `.founder/product-map.md` exists, do not demo hypothesis as verified. Concierge is a valid demo of the job. A polished walkthrough of unverified UI is not evidence.

6. **Propose with a number and a cadence.** Recurring vs one-off must be explicit (see `founder-pricing`). The proposal is a commercial artifact in the user's language. No authorization to send commercial terms → don't send them.

7. **Follow up on a clock, then log the outcome.** Every contact either advances a next step, gets a no, or is still inside a stated window. Silence is not a commitment. Do not keep prospects in pipeline forever to look busy.

8. **Persist without inventing a funnel.** Create or update `.founder/pipeline.md` (or the founder's existing CRM/notes — reuse that convention):

   ```markdown
   # First-customer pipeline

   Last updated: <date>
   Authorization for outbound: <quote the context.md line; if missing, this file is not a license to contact>

   ## Prospects
   For each:
   - Who / org:
   - Why they are on this list (source fact):
   - Stage: prospect / discovery / demo / proposal / follow-up / won / lost / paused
   - Evidence tier reached: stated intent / commitment / payment / recurring use / none yet
   - Last action / next action / date:
   - Notes: observed only
   ```

   Log the overall push in `.founder/experiments.md`:

   ```markdown
   ## <short experiment name> — <date started>

   **Status:** running / concluded / superseded (if superseded, by which entry and why)

   **Hypothesis:** this offer, to this buyer, produces commitment or payment in the window.

   **Action:** the outreach and sales steps actually taken (counts of real contacts, not planned ones).

   **Owner:** ...

   **Cost:** time and any spend authorized.

   **Metric:** commitments and payments (recurring vs one-off labeled). Not emails sent.

   **Observation window:** ...

   **Evidence:** ...

   **Decision:** fill in founder-review.
   ```

   Update `.founder/context.md` **Evidence** when a tier actually moves. A single payment is not recurring use and not a repeatable acquisition motion.

## Deliverables

- Authorization check, written.
- `.founder/pipeline.md` (or equivalent) with real prospects only.
- Experiment-log entry whose metric is commitment/payment, not activity.
- Updated evidence tiers in context when something happened.
- A named next skill.

## Judging results / routing the next action

Success: outreach that was allowed, conversations that could have failed, and a pipeline that does not contain invented people. Failure: contacting without authorization, demoing fiction, counting emails as demand, or jumping to ads because a handful of conversations were slow.

Route:
- Problem/offer still collapsing in discovery → `founder-validate` / `founder-positioning`.
- Price is the sticking point → `founder-pricing`.
- Product cannot deliver the promised job → `founder-product-audit` then `founder-mvp`.
- They pay or start, then stall → `founder-activation`.
- They pay and leave → `founder-retention` (do not "just get more").
- First customers exist and the gap is a repeatable channel → `founder-growth`.
- Window ended → `founder-review`.

## Working with no complements installed

Inbox, calendar, a markdown pipeline. No CRM, sequencer, or enrichment tool required. Lack of tooling is not a reason to skip authorization or to automate spam.

## Complement integration

This skill does not hand off to engineering by default. If a demo blocker is technical, route through `founder-mvp` rather than invoking `to-spec` here. gstack `browse` may walk a demo environment if already authorized; it is not outreach. Never install packages. Never send messages from a complement that bypasses the authorization gate. Load `docs/integration/` guides only when the matching package is present.
