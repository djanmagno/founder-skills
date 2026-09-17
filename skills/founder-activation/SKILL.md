---
name: founder-activation
description: Define a new user's first value moment for a bootstrapped B2B SaaS, diagnose where early users drop off, and fix onboarding so more of them reach that value. Use this when signups or trials don't turn into active users, when the founder asks "why do people sign up and disappear," "how do we improve onboarding," or "what is our aha moment." Do not use it for pricing and packaging (founder-pricing), for keeping paying customers over months and expanding accounts (founder-retention), or for getting more visitors in the door (founder-growth) — activation is about users who already arrived reaching first value, not about acquiring more of them.
---

## What this skill does

Names the single first value a new user must experience, finds the step where most of them abandon before reaching it, and runs a small experiment to remove or shrink that drop-off. It works on users who already signed up — free, trial, or newly paying — and it stops once first value is consistently reached. Everything after that (renewal, expansion, long-term habit) belongs to `founder-retention`.

## When to use it / when not to

Use it for: free users with no conversion, trial users who go quiet, new paying customers who never really start using the product, or any "published product with interest but no active use" pattern.

Do not use it when nobody is arriving at all — with no signups there is no funnel to fix, and the work belongs in `founder-first-customers`, `founder-launch`, or `founder-growth`. Do not use it to re-price, re-package, or add features so the product "feels worth it" — price objections after value is reached are `founder-pricing`; missing capabilities are a `founder-mvp` question. Do not use it as a substitute for retention work: a user who activated and then cancelled months later is a retention problem, not an onboarding problem.

## Minimum required context

`.founder/context.md` (who the user is, what exists, evidence tiers), plus whatever is known about the current path from signup to first use: the steps a new user takes, and any counts at each step — even rough ones from memory, a database query, or support conversations. If no counts exist at all, say so ("unknown") rather than inventing a funnel; the first experiment may simply be instrumenting one step. If the founder cannot describe what "first value" means for their user, that definition is step 1, not a reason to skip this skill.

## Procedure

1. **Define first value in one sentence.** What is the smallest outcome after which a new user can truthfully say "this did something for me"? Prefer an outcome the user recognizes (a report they can send, a task they no longer do by hand, an answer they trust) over a product action (clicked three buttons, invited a teammate). If the founder lists five candidates, force a choice: one primary first value, the rest deferred. Mark it as a hypothesis until users who reach it actually convert, return, or pay at a higher rate than users who don't.

2. **Map the current path, honestly.** List every step between arrival (signup, invite, trial start) and first value as it exists today — including steps the founder wishes weren't there (email verification loops, blank-slate setup, mandatory integrations, waiting on an admin). For each step, record what is known about completion: a count, a rate, or "unknown." An honest map with three "unknown" steps beats a fabricated funnel with precise percentages. Do not invent drop-off numbers to make the map look complete.

3. **Name the main drop-off, not all of them.** Pick the single step where the most users are lost or stuck, based on whatever evidence exists (counts, support messages, watching one session, asking one user). One obstacle, one experiment. Common patterns to check, without assuming any of them: the user doesn't understand what to do first; setup demands work before any payoff; the payoff requires someone else (an admin, a teammate, an integration owner) who never shows up; the trial clock runs out before value lands.

4. **Design the smallest onboarding change that moves that step.** Prefer subtraction over addition: remove a step, defer it until after first value, pre-fill it, or replace it with a manual concierge action the founder does by hand. Adding tours, tooltips, videos, or emails is allowed only if the diagnosis says the user is lost rather than blocked — a blocked user doesn't need more explanation, they need less work. If the fix requires a product change, keep it small enough to be one experiment; anything larger goes through `founder-mvp` with this skill's diagnosis attached, and the commercial read still happens here, not in the build.

5. **Respect authorization and capacity.** Onboarding changes that contact users (emails, calls, manual setup help) need the same explicit authorization as any outbound contact in `.founder/context.md`. Concierge onboarding the founder does personally is often the right first experiment for a solo founder — but record the time cost honestly, because it does not scale and must not silently become the permanent process.

6. **Log the experiment** in `.founder/experiments.md` (or `.founder/experiments/<name>.md` — pick the layout already in use and stay consistent):

   ```markdown
   ## <short experiment name> — <date started>

   **Status:** running / concluded / superseded (if superseded, by which entry and why)

   **Hypothesis:** users who <reach first value as defined> <convert / return / pay> at a higher rate than users who don't — and <this specific change> moves more of them past <the named drop-off step>.

   **Action:** the specific onboarding change made (or manual concierge step performed).

   **Owner:** ...

   **Cost:** time and any tooling cost.

   **Metric:** completion rate at the named step and first-value-reached rate. Not total signups.

   **Observation window:** when the metric gets read.

   **Evidence:** observed — or "window still open" / "unknown."

   **Decision:** fill after the window.
   ```

7. **Persist the definition.** Create or update `.founder/activation.md`:

   ```markdown
   # Activation

   Last updated: <date>

   ## First value
   <one sentence — marked hypothesis until users who reach it convert/return/pay at a higher rate>

   ## Path to first value
   <each step, with completion evidence or "unknown" — never invented rates>

   ## Main drop-off
   <the one step being worked on, and why it was chosen over the others>

   ## Experiments
   <links to the relevant `.founder/experiments.md` entries — no copied content>
   ```

   Update `.founder/context.md` **Evidence** only with what was actually observed.

## Deliverables

- A one-sentence first-value definition, marked hypothesis or evidenced.
- An honest step map with the one main drop-off named.
- One onboarding experiment logged with a metric on step completion and first value reached — not on signup volume.
- `.founder/activation.md`, created or updated.

## Judging results / routing the next action

The work succeeds if the first-value definition is specific enough to be checked, the drop-off step is named from real behavior rather than guessed, and the logged experiment has a step-completion metric an observation window can actually read — whether that window ends up showing a lift is for `founder-review` to read, not something this skill can know in-session. It fails if signups grew but activation didn't (that's acquisition, not activation), if the funnel numbers were invented, or if the "fix" was a feature list.

Route from what the window actually showed:
- Users reach value but don't pay → `founder-pricing`.
- Users reach value, pay, then cancel or fade → `founder-retention`.
- Nobody arrives to activate → `founder-first-customers`, `founder-launch`, or `founder-growth` — do not keep polishing onboarding for traffic that doesn't exist.
- Value requires a product change bigger than one experiment → `founder-mvp`, carrying this diagnosis.
- Window ended, read the result → `founder-review`.

## Working with no complements installed

Everything here is doable with counts from the database, the founder's inbox, and talking to users. No analytics suite, onboarding tool, or email platform is required — a founder manually walking one new user through setup and writing down where they got stuck is a valid first experiment.

## Complement integration

- If gstack is present and the drop-off is in the live product experience, `browse` or `qa-only` can investigate what a new user actually sees — a report to feed this diagnosis, not a fix on its own. `qa` (which may fix and commit) only when fixes are explicitly in scope and authorized.
- If the fix needs spec or tickets, that preparation happens in `founder-mvp`, honoring explicit-invocation rules — never invoked automatically from here.
- Load `docs/integration/` guides only when the matching package is actually present. Never install, update, or modify complements.
