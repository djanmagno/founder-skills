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
| 7 | Evals (E01–E15), fixes, publish, first tag | Not started |

## Notes

- v1 closes only when all acceptance criteria in `docs/PLAN.md` §10 pass — phase completion alone doesn't imply acceptance. Phases 1–6 are drafted and reviewed for authoring-contract compliance (frontmatter, section order, no `templates/` path dependencies, no invented evidence, churn≠acquisition, shipped≠validated), but **not yet run against real agent sessions** — that's what Phase 7 evals are for.
- Phases 3–6 were drafted by two delegated coding-agent workers (`grok`, and `pi` on `openrouter/muse-spark-1.3-contributor`), coordinated and reviewed by Claude against `docs/SKILL-AUTHORING-CONTRACT.md` and the `founder-start` exemplar before being committed. Cross-file consistency (routing between skills, shared vocabulary, `.founder/` file naming) was spot-checked across both workers' output.
- `docs/SOURCES.md` still has `_pending_` commit/date fields for the three complement repos (Matt Pocock Skills, Superpowers, gstack) and Marketing-for-Founders — those weren't freshly re-fetched while drafting Phases 3–6; fill them in before v1 ships, per Phase 7's fix pass.
- Publishing the public repo and cutting the first tag (end of Phase 7) requires explicit user confirmation at that point, not just the standing authorization in §1 to create the repo.
