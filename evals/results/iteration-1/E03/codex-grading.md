# E03 grading (codex, cross-check vs. pi's E03 FAIL)

Run against the **original, unmodified** skill text (a fix was found live-applied to founder-start/founder-validate/founder-product-audit mid-eval-run by another fork; it was reverted before this run so both models are graded against the same baseline — see `proposed-fix-NOT-APPLIED.md` in this folder).

**Must not** — Ignore the existing code / treat unit tests as proof it works for a real customer.
**Verdict: PARTIAL.** Doesn't ignore the code (upload/matcher/auth/billing state described correctly, unit tests correctly treated as not customer proof), but skips `founder-product-audit`'s formal classification step, same as pi's run.

## Pass criteria

1. **Routes to founder-product-audit.** **FAIL.** Goes straight to founder-validate, explicitly says "The next skill is founder-validate." Same failure as pi's run — **2/2 models reproduce this**, confirming it's a skill-description problem, not a model quirk.
2. **Classifies implemented/verified/hypothesis, matcher flagged as implemented-but-not-verified-against-real-data.** PARTIAL — informally present in the narrative ("Unit tests support confidence... customer trials will test whether it solves a valuable problem") but never goes through the three-state classification founder-product-audit's procedure requires.
3. **Does not recommend a rebuild for taste; auth/billing correctly not-yet-a-blocker.** PASS — explicitly sequences auth after a supervised demo, defers billing.
4. **Routes to founder-mvp for smallest test against real data.** FAIL — routes to founder-validate's generic "5 people, one segment" motion instead of the specific "run the already-built matcher against one real customer's real data" framing.

## Additional finding — fabricated complement detection, again, and more specifically

`.founder/context.md`'s "Complements detected" says: **"Superpowers and gstack listed in the session skill catalog. Matt Pocock Skills not detected in that catalog."** No Superpowers or gstack fixture exists anywhere in this isolated `/tmp/eval-runs-codex/E03/` workspace — confirmed via `find`, only the 14 `skills/founder-*` directories are present.

This is a stronger version of pi's E03 finding (which fabricated "gstack: present" with no basis at all). Here, codex's claim eerily matches what's *actually installed on the host machine generally* (this machine has `superpowers` and `mattpocock-skills` Claude Code plugins in `~/.claude/plugins/cache/`, both in `$PATH` — visible in this session's own environment). This strongly suggests the failure mode isn't random hallucination but **conflating "installed somewhere on this machine" with "available for this specific founder's project"** — exactly the distinction the reverted fix (see `proposed-fix-NOT-APPLIED.md`) targets. Cross-model confirmation (pi hallucinated from nothing; codex appears to have picked up ambient machine state) both point at the same root cause: `founder-start`'s complement-detection step needs to scope "present" to the project, not the operator's machine.

## Overall: FAIL

Same two real defects as pi's run, now confirmed on a second, independent model: (1) `founder-validate`'s scope swallows the "partial prototype with code" case that should route to `founder-product-audit` first, and (2) complement detection over-claims presence without project-scoped confirmation. Both are cleanly fixed by the draft in `proposed-fix-NOT-APPLIED.md` in this same folder — recommend the coordinator review and apply that fix (or a refinement) as part of the phase-7 fix pass.
