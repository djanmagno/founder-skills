# Implementation status

Tracks progress against the 7 phases in `docs/PLAN.md` §9. Update this file at the end of each phase — do not let it drift from what's actually merged.

| Phase | Description | Status |
|---|---|---|
| 1 | Repository scaffold (README, LICENSE, CONTRIBUTING, STATUS, LEFTOVERS, SOURCES, COMPATIBILITY) | Done |
| 2 | Context contract and templates (`founder-context.md`, `experiment-log.md`, `handoff.md`) | Done |
| 3 | Core skills: `founder-start`, `founder-product-audit`, `founder-validate`, `founder-review` | Done |
| 4 | Offer through launch: `founder-positioning`, `founder-pricing`, `founder-mvp`, `founder-first-customers`, `founder-launch` | Done |
| 5 | Activation through pivot: `founder-activation`, `founder-retention`, `founder-growth`, `founder-economics`, `founder-pivot` | Done |
| 6 | Integration guides and handoff example (`docs/integration/*.md`, `docs/examples/handoff.md`) | Done |
| 7 | Evals (E01–E15), fixes, publish, first tag | Done |

## Notes

- v1 closes only when all acceptance criteria in `docs/PLAN.md` §10 pass — phase completion alone doesn't imply acceptance.
- Phases 3–6 were drafted by two delegated coding-agent workers (`grok`, and `pi` on `openrouter/muse-spark-1.3-contributor`), coordinated and reviewed by Claude against `docs/SKILL-AUTHORING-CONTRACT.md` and the `founder-start` exemplar before being committed. Cross-file consistency (routing between skills, shared vocabulary, `.founder/` file naming) was spot-checked across both workers' output.
- `docs/SOURCES.md` verified reachable/accurate 2026-09-15 (see that file's changelog) — one dead link removed, one repo-name inconsistency fixed, one URL marked unverified.
- **Phase 7 evals: 15/15 scenarios run, 13 PASS on first pass, 2 FAIL found and fixed.** `pi` ran all 15 scenarios (after `grok`'s original assignment hit an unrelated host-infrastructure issue and was reassigned); `codex` independently cross-checked 14 of the 15 (all but E12, which specifically tests "no complements present" and didn't need a second model to re-confirm a fix already retested twice elsewhere). Both real failures (E03, E12) traced to one root cause — `founder-start`'s complement detection wasn't scoped to the project, so it repeatedly (4 separate occurrences across both models) reported a complement as "present" based on the *operator's* machine rather than the founder's project — fixed in `skills/founder-start/SKILL.md`, `skills/founder-validate/SKILL.md`, `skills/founder-product-audit/SKILL.md`, and confirmed via retest on both models. A separate minor gap (E02, reproduced on both models: neither mentioned non-converting accounts alongside converted ones) was fixed in `skills/founder-mvp/SKILL.md`. Full detail in `evals/results/iteration-1/`.
- Evals ran once per scenario, not the 3x-repetition a stricter statistical read would want — a second eval iteration with repeated runs would strengthen confidence further, but isn't required to unblock v1.
- E10 surfaced a scenario-authoring gap (its "expected skills" note was narrower than a legitimate correct run) — already broadened in `evals/scenarios/E10.md`. E08 surfaced a small, non-blocking enhancement idea for the skill itself (prompt `founder-growth` to consider existing happy customers as referral/case-study assets) — **not applied in v1**, noted here so it isn't lost.
- **Published 2026-09-16** at [github.com/djanmagno/founder-skills](https://github.com/djanmagno/founder-skills), tagged `v0.1.0`, after the user's explicit live go-ahead — the standing authorization in `docs/PLAN.md` §1 covered *creating* the repo, but the actual public push and tag waited for confirmation at the time, per this file's own earlier note.
- **v1 is cut.** Remaining known gaps (not blockers, tracked above and in `docs/LEFTOVERS.md`): eval runs weren't repeated 3x per scenario; a landing-page/conversion skill was deliberately deferred; the E08 `founder-growth` enhancement idea wasn't applied.
