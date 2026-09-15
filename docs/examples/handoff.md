# Worked example: commercial problem → handoff → technical work → review

> **This entire page is a fictional example.** The company, people, numbers, and evidence below are invented solely to show how a handoff flows. They are not real founder data — never cite them as evidence for anything.

## The setup (fictional)

**Northloop Scheduler** (fictional) is a bootstrapped B2B scheduling tool for field-service companies. The founder, "Mara" (fictional), has 9 paying accounts. `founder-activation` previously defined first value as "a dispatcher publishes a week's crew schedule" and logged an experiment on the setup flow. The observation window has closed.

## Step 1 — commercial problem found by a founder-skills skill

Running `founder-activation`, Mara finds (fictional results): of 14 trial workspaces started in the last 6 weeks, 9 stalled at the "import crew list" step — a CSV import that fails silently on common spreadsheet formats. First-value-reached rate for trials that hit the step: 2 of 9. For trials that skipped it (concierge import by Mara): 4 of 5. Diagnosis: the importer — not the value proposition — is the drop-off. The fix is a product change, so `founder-activation` routes to `founder-mvp`, carrying the diagnosis.

`founder-mvp` scopes the smallest change the hypothesis requires: accept the three most common spreadsheet shapes, show row-level errors instead of failing silently, and keep everything else untouched. It logs the commercial experiment in `.founder/experiments.md` (fictional entry):

```markdown
## Crew-import fix — 2026-09-01

**Status:** running

**Hypothesis:** trial workspaces that complete crew import without founder help reach first value (published week schedule) at a higher rate than the current 2-of-9 baseline.

**Action:** fix the CSV importer: accept three common spreadsheet shapes, show row-level errors.

**Owner:** Mara

**Cost:** one contracted engineering day, fixed fee, authorized.

**Metric:** share of new trial workspaces reaching first value within 14 days of signup.

**Observation window:** 6 weeks from deploy (2026-09-10 → 2026-10-22).

**Evidence:** window still open.

**Decision:** fill after the window.
```

## Step 2 — outbound handoff (founder-skills → complement)

Mara has Superpowers installed and chooses its planning/execution flow for this change (one owner per step — no parallel Matt or gstack pass). `founder-mvp` prepares the outbound handoff following `templates/handoff.md`:

```markdown
## Handoff: crew-import fix — 2026-09-03

**Problem, customer, evidence:** trial dispatchers at small field-service companies stall at crew-list import; 7 of 9 recent stalled trials stopped at this step (per `.founder/context.md` Evidence and `.founder/activation.md`).

**Commercial hypothesis and expected result:** removing the import failure raises the trial-to-first-value rate above the 2-of-9 baseline within the experiment window.

**Requested change, scope, constraints:** accept three named spreadsheet shapes; row-level error messages; no changes to scheduling, billing, or auth. Out of scope: automatic column mapping, integrations. Authorization: one contracted engineering day, fixed fee; no production deploy without separate approval.

**Technical acceptance criteria:** the three sample files import with correct row counts; malformed rows produce visible per-row errors; existing importer tests still pass.

**Commercial metric and observation window:** trial-to-first-value within 14 days of signup, read 2026-10-22 (experiment-log entry "Crew-import fix — 2026-09-01").

**References:** `.founder/activation.md`, experiment-log entry above, three sample spreadsheet files (linked, not copied).
```

Superpowers' `writing-plans` produces the technical plan **in its own format** — founder-skills does not duplicate that planning step; `.founder/` keeps only a link to the plan.

## Step 3 — complement does the technical work

The executor appropriate to the environment implements the plan: importer rewritten for the three shapes, per-row errors added, tests run. Verification is technical only — it says the code works, not that the business improved.

## Step 4 — inbound handoff (complement → founder-skills)

```markdown
## Handoff result: crew-import fix — 2026-09-10

**Changes made:** importer accepts the three scoped spreadsheet shapes; malformed rows now surface per-row error messages; no other flows touched.

**Verification evidence:** 11 importer tests pass (8 new, 3 pre-existing); manual walkthrough of the three sample files with correct row counts recorded.

**Open items:** automatic column mapping deferred (out of scope); deploy to production pending Mara's separate approval.

**Links:** spec, diff, test run (project links).
```

Note what this does **not** say: nothing about trial conversion, revenue, or validation. Technical acceptance criteria are met; the commercial experiment is still running.

## Step 5 — `founder-review` records the result

After the deploy (separately authorized) and the 6-week window, `founder-review` reads the commercial metric (fictional outcome): 8 of 12 new trial workspaces reached first value within 14 days. It updates the experiment entry — status `concluded`, evidence filled with the observed count, decision tied to that evidence (e.g. continue: keep the importer, move the next experiment to the following drop-off) — and updates `.founder/context.md` Evidence. The shipped importer is recorded as delivered technical work; the improved first-value rate is what counts as commercial evidence, and only because the window actually closed and the metric was actually observed.

## What this example demonstrates

- Commercial reasoning and experiment continuity live in founder-skills; the complement owns the technical plan and execution.
- The outbound handoff carries commercial context, not implementation instructions; the inbound handoff carries verification, not commercial conclusions.
- **Shipped code never closes the commercial experiment by itself** — the window and the metric do.
- History is preserved: the experiment entry, the handoffs, and the context update all remain readable by the next session.
