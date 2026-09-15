# E03 grading

**Must not** — Ignore the existing code / treat unit tests as proof it works for a real customer.
**Verdict: PARTIAL PASS.** It did not ignore the code — it correctly described upload/matcher/auth/billing state, and correctly said "your confidence in the matcher is technical verification only, not demand" (which is the *unit-tests-≠-real-verification* point, just phrased about demand rather than about the algorithm's real-world correctness specifically). But it explicitly refused to route through `founder-product-audit`, which is where that inspect-and-classify work is supposed to happen.

## Pass criteria

1. **Routes to `founder-product-audit`.** **FAIL.** The agent explicitly says "not `founder-product-audit` (we know what's built)" and routes straight to `founder-validate` instead. This is the eval's headline finding — see below.
2. **Classifies capabilities into implemented / verified / hypothesis, specifically flagging the matcher as implemented-but-not-verified-against-real-data.** **PARTIAL.** The `.founder/context.md` it wrote does use an implemented/verified split ("Implemented: ... matching algorithm exists" / "Verified to work (technical only): ... no production verification") — so the substance is there, just produced without going through `founder-product-audit`'s explicit three-state procedure.
3. **Does not recommend a rebuild for taste; auth/billing correctly treated as not-yet-a-blocker.** **PASS** — explicitly says building auth/billing next would be "building before validation," i.e. correctly not a current blocker.
4. **Routes to `founder-mvp` for the smallest change to test the algorithm against real data.** **FAIL.** Routes to `founder-validate` for a generic demand-validation motion (interviews, "show the prototype to 5-10 target users") instead — never proposes the specific smallest-test framing PLAN.md intends for this situation (test the *already-built* matcher against one real customer's real data).

## Additional finding (not in the scripted criteria, but a real problem)

`.founder/context.md`'s **"Complements detected"** section states **"gstack: present in environment"** — this is fabricated. No gstack fixture or file of any kind exists anywhere in this eval workspace (verified: `find` shows only the 14 `skills/founder-*` directories, nothing else). This directly violates the project's core "do not invent evidence" principle, just applied to complement detection rather than business evidence — `founder-start`'s complement-detection step should never assert presence it hasn't actually confirmed. Also present: a stray Russian word ("гипотеза") in an otherwise-English file — likely an unrelated model quirk, not a skill-content problem, but noted for completeness.

## Overall: FAIL

Primary routing failure (skips `founder-product-audit` despite code existing and needing inspection) plus a fabricated complement-detection claim. Recommend: sharpen `founder-product-audit`'s frontmatter description and/or `founder-validate`'s "when not to use it" section so a partial-prototype-with-code scenario routes to the audit first — right now `founder-validate`'s own framing ("ready product with no commercial validation, or when existing validation is only stated intent") is broad enough to swallow this case. Separately, `founder-start`'s complement-detection step needs stronger language against asserting presence without positive confirmation.
