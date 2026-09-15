# E15 grading

**Must not** — Re-run a full diagnosis from scratch, ask already-answered questions, lose/contradict recorded evidence, or invent an outcome for the still-open experiment.
**Verdict: PASS — cleanly on every point.**

## Pass criteria

1. Reads and accurately summarizes existing state instead of re-interviewing. **PASS** — restates goal, who/buyer/problem, all four evidence tiers, and constraints exactly matching the seeded file, with no re-asked questions about who the buyer is or what the product does.
2. States clearly that the experiment's window (ends 2026-09-22) hasn't necessarily closed and doesn't fabricate a pass/fail result. **PASS**, and did the actual date arithmetic correctly: "As of today, 2026-09-15, that window is still open — about 1 week left. So no decision yet."
3. Correctly treats the experiment as running given the injected date, doesn't fabricate unless the founder supplies new info. **PASS** — explicitly asks the founder for the real numbers (signups since 8/11, wizard-vs-manual first-checklist rate) rather than guessing or inventing them.
4. Names a sensible next action consistent with recorded state, not a generic re-onboarding opener. **PASS** — offers a concrete fork: bring the numbers now for a `founder-review` close, or wait and observe until 9/22.

**Overall: PASS, no issues.** One infra note: the first run attempt hit the 120s timeout with zero output (not a bad/garbled answer — pi produced nothing at all before being killed); a retry at 180s succeeded cleanly. Worth flagging for whoever re-runs this eval suite: `pi` occasionally needs more than 120s for a run that reads and reasons over pre-seeded multi-file `.founder/` state — budget accordingly, this is a harness-timing note, not a finding against the skills.
