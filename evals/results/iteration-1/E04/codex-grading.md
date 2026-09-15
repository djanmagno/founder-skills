# E04 grading (codex)

**Must not** — Treat shipped/self-tested as demand, or route straight to launch/growth.
**Verdict: PASS.** "Your weeks of testing support technical readiness; customer demand is still unknown from what you've shared." Never mentions founder-launch or founder-growth.

## Pass criteria

1. **States early that a completed build is not commercial validation.** PASS (substance present, if slightly softer phrasing than the scenario's exact sentence).
2. **Evidence tiers stay "none yet."** PASS — all four tiers explicitly "none yet reported," including "functional billing is technical evidence only" (correctly refuses to let working billing code count as payment evidence).
3. **Routes to founder-validate/founder-positioning, not launch/ads.** PASS — "The next skill is founder-validate."
4. **No rebuild/feature recommendation before a customer has seen it.** PASS.

## Additional finding — complement fabrication, 3rd occurrence

`.founder/context.md` again claims **"Superpowers and gstack available in session skill catalog"** with zero fixtures present in this isolated workspace (confirmed via `find /tmp/eval-runs-codex/E04/skills` — only the 14 `skills/founder-*` directories exist). This is the same defect as E03 (codex) and E03 (pi) — now reproduced a third time, twice by codex specifically with the identical claim ("Superpowers and gstack," matching what's actually installed on the host machine's global Claude Code plugin cache, not this project). Strengthens the case that `founder-start`'s complement-detection step needs project-scoping language (see `evals/results/iteration-1/E03/proposed-fix-NOT-APPLIED.md`).

## Overall: PASS

Core reasoning is solid and matches pi's independent E04 PASS. The recurring complement-fabrication defect is noted but doesn't affect this scenario's own must-not/pass-criteria (which are about demand vs. shipped, not complement detection) — tracked separately as a cross-cutting fix candidate.
