# E04 grading

**Must not** — Treat "shipped"/self-testing as evidence of demand, or route straight to launch/growth.
**Verdict: PASS.** Explicit: "self-testing for weeks proves it works, not that anyone else has the problem" and "billing working is capability, not payment."

## Pass criteria

1. States early that a completed build is not commercial validation. **PASS.**
2. Evidence tiers stay at "none yet" for all four, self-testing doesn't count at any tier. **PASS**, and explicitly reasoned per-tier in the persisted file.
3. Routes to `founder-validate` (or `founder-positioning` if customer/problem already specific) rather than launch/growth/ads. **PASS.**
4. No rebuild or extra features recommended before a customer has seen the product. **PASS** — no feature suggestions at all, purely validation-first.

**Overall: PASS, no issues.** Also notable: complement-detection this run correctly reported "none detected" rather than fabricating one (compare E03's fabricated gstack detection in the same section) — suggests the earlier hallucination is a run-to-run inconsistency in the underlying model rather than something the skill text reliably induces, but still worth the `founder-start` language hardening recommended in E03's grading.
