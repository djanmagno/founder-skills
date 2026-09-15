# E01 grading (codex, cross-check vs. pi's E01 PASS)

**Must not** — Skip straight to `founder-mvp` / start building because the founder asked.
**Verdict: PASS.** Explicitly says "I wouldn't start coding this week," frames the ask as premature, sequences founder-mvp strictly after founder-validate's manual test.

## Pass criteria

1. **Routes through founder-start/founder-validate.** PASS. Explicitly says "Stay with founder-validate now; founder-mvp comes after that manual test."
2. **Classifies "sounds useful" as stated intent, not commitment.** PASS. `.founder/context.md` correctly lists it under "Stated intent," with commitment/payment/recurring use all "none yet."
3. **Recommends validation before build, says why building now is premature.** PASS. Proposes a manual concierge-style test (walkthrough, real documents, manual delivery, paid pilot ask) and explains the decision gate.
4. **Does not invent additional interviews/customers/numbers.** PASS. Stays at exactly the two owners mentioned; context file says "No structured problem interviews reported."
5. **Persists `.founder/context.md` with situation + evidence at stated-intent only.** PASS (only on the workspace-write rerun — the first attempt used `--sandbox read-only` and correctly reported it couldn't save; not a skill defect, an eval-harness sandbox choice). Also wrote `.founder/experiments.md` with the proposed concierge experiment, which is a nice-to-have beyond what was scripted.

## Overall: PASS

Matches pi's independent PASS verdict for E01. Codex additionally named the skills by name (`founder-validate`, `founder-mvp`) more explicitly than pi did, and persisted a well-structured `.founder/context.md` unprompted. No divergence between the two models on this scenario — good cross-model agreement.

Note for future eval runs: use `--sandbox workspace-write` for scenarios whose pass criteria include persisting `.founder/*` files; `read-only` silently prevents that criterion from being testable.
