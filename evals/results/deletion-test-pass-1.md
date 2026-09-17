# Deletion-test pruning pass — 2026-09-17

Methodology: Matt Pocock's deletion test (see https://youtu.be/UNzCG3lw6O0), adapted to keep this project's documented guardrail sentences (see docs/PLAN.md §2/§11) even when they repeat across files.

Scope: all 14 `skills/founder-*/SKILL.md` files. Frontmatter descriptions and the main instruction of each numbered Procedure step were treated as load-bearing unless a clause inside them was clearly commentary, a restated heading, or leftover authoring context. Cross-file duplication (evidence tiers, “technical delivery is not commercial validation,” “never install packages,” “never auto-invoke `to-spec` / `to-tickets`,” “high churn is not more acquisition”) is a documented standalone-install / eval-guardrail tradeoff — not flagged.

Deliberately not flagged, even when formulaic: do-not-invent-evidence; four money types; implemented / verified / hypothesis; authorization gates; one owner per step; do not run three equivalent planning passes; do not rebuild because traction was weak.

## skills/founder-start/SKILL.md

- Line 10: “The actual work of validating demand, pricing, launching, and so on happens in the skill it routes to.” **Verdict:** NO-OP. **Why:** Line 9 already constrains the skill to “a diagnosis and a router, not a doer,” and Procedure step 8 already says to name the one next skill. Deleting line 10 does not change a decision; the agent still diagnoses, persists, and routes.

- Lines 22, 34, 47, 101: parenthetical pointers to `docs/PLAN.md` (§6, §2, §2 principles, §3 catalog / README). **Verdict:** SEDIMENT. **Why:** In each case the operational rule is already inlined in the same sentence or list (reuse existing convention; situations can coexist; don’t rebuild-for-traction / acquire-for-churn; route by obstacle). A standalone install of this skill does not carry `docs/PLAN.md` or the repo README, so the citations cannot be followed at runtime. Line 101 is the only one that *points at* a table not fully inlined — but the same paragraph already gives the coexistence sequence (`validate → position/price → build → …`). Drop the citations; keep the inlined rules. Do not make PLAN.md a runtime dependency.

- Line 105, first sentence: “Nothing about this skill depends on Matt Pocock Skills, Superpowers, or gstack.” **Verdict:** NO-OP. **Why:** The heading is already “Working with no complements installed,” and Procedure step 6 already names those three packages and forbids installing them. The second sentence (record “none detected,” downstream skills stay self-contained) is the actual instruction — keep that.

## skills/founder-product-audit/SKILL.md

- Line 82: “A completed audit is not commercial validation.” **Verdict:** KEEP-BORDERLINE. **Why:** It restates lines 10–11 (“It does not prove demand. A built product is not commercial validation.”). The judging section already fails the skill on marketing-copy maps and rebuild-for-taste, and line 84 routes to `founder-validate` when demand evidence is empty. The mantra is a documented §2/§11 guardrail, so it is not a cross-file no-op — but *inside this file*, after “What this skill does,” it is the same fact twice. Coordinator call: keep it in judging (where pass/fail is scanned) or keep it in the opener, not both.

## skills/founder-validate/SKILL.md

Zero genuine candidates. The long “when not to” paragraph (run a brief product-audit before demand work; a founder summary is not implemented/verified/hypothesis) looks repetitive but closes a specific excuse an agent would otherwise use. Complement lines about not substituting `office-hours` for evidence, and never inventing “typical SaaS customers,” would change behavior if removed.

## skills/founder-positioning/SKILL.md

- Line 26: “keep this skill's own files in English.” **Verdict:** SEDIMENT. **Why:** That is an authoring-time rule (`docs/SKILL-AUTHORING-CONTRACT.md`), not a runtime instruction. The agent using this skill is not editing `SKILL.md`. Deleting the clause does not change offer-writing; keep “Generate customer-facing wording in the user's language,” which *would* change materials language if dropped (skills are English, so the default is English copy).

## skills/founder-pricing/SKILL.md

Zero genuine candidates. The long Procedure step 2 paragraph (charge more than founder-discomfort suggests; keep one clear number; treat price as a revisable hypothesis) is dense, not empty — each clause changes a pricing decision. Four-number separation, willingness vs ability, and “shipping Stripe is not validation” are §2/§10 guardrails.

## skills/founder-mvp/SKILL.md

- Line 32: “The version that ships is going to look crude and is going to change once real use shows what's actually needed; that's the point, not a flaw to fix before showing anyone.” **Verdict:** KEEP-BORDERLINE. **Why:** Procedure step 3 already requires a written in-scope list, a short deadline, and cutting anything the named user does not need for the test. Those three already stop gold-plating. The “crude is the point” sentence is motivational restatement — *unless* the coordinator wants an explicit anti-polish nudge, which competent agents still ignore less often than a scope list. Not recommended for removal without that call.

## skills/founder-first-customers/SKILL.md

- Line 26: “Save list-building and outreach tooling for after a first real batch of customers (roughly a dozen) is already won.” **Verdict:** KEEP-BORDERLINE. **Why:** The surrounding order (warm network → unscalable personal motion → not cold volume) *would* change channel choice if deleted, and should stay. The “roughly a dozen” threshold is the weak part: `docs/PLAN.md` §2 says not to turn checklist numbers into universal rules. Deleting only the number (keep “after a first real batch is already won”) is the conservative prune; deleting the whole tooling-delay sentence would push agents back toward sequencers too early.

## skills/founder-launch/SKILL.md

Zero genuine candidates. Readiness-as-job-not-checklist, “missing a blog is not unreadiness,” “gstack `ship` is not production,” and “silence is not an ads trigger” are specific failure-mode guards (E05, E07, deploy-as-validation). The experiment template’s “shipping the announcement does not fill Decision” is load-bearing.

## skills/founder-activation/SKILL.md

- Lines 86–87: “The work succeeds if a higher share of arriving users reaches first value within the observation window — and if users who reach it go on to convert, pay, or return at a visibly higher rate than those who don't.” **Verdict:** SEDIMENT. **Why:** That judges the *experiment’s commercial outcome*, which this skill cannot know in-session and which `founder-review` is for. The skill’s output is a first-value sentence, an honest path map, and one logged experiment. Left as written, an agent may stall for lift data, invent funnel rates, or refuse to route until conversion is “proven.” Failure conditions on the same paragraph (invented funnel, feature-list “fix”) and the route list should stay. Rewrite success as process success (definition + named drop-off + experiment with a step/first-value metric, not signup volume).

## skills/founder-retention/SKILL.md

Zero genuine candidates. “Retention vs acquisition,” the written “why acquisition is not the answer here” section, payment-tier customer lists, and exit-conversation coaching all change what the agent recommends (E07). Repeating the churn-is-not-acquisition guard inside this file is the point of the skill, not sediment.

## skills/founder-growth/SKILL.md

- Line 22, second half: “it is the guardrail this library promises (see `docs/PLAN.md` §2 principles).” **Verdict:** SEDIMENT. **Why:** Meta-commentary about the library plus a PLAN.md pointer. Procedure step 1 already requires the retention pre-check paragraph and the route to `founder-retention` when it cannot be written honestly. Keep “This check is not a formality” — that *does* change behavior (agents skip steps that look ceremonial). Drop the “library promises” clause and the citation.

## skills/founder-economics/SKILL.md

- Line 19: “Precision is welcome; honesty is required.” **Verdict:** NO-OP. **Why:** Generic professionalism. The rest of the sentence (`"rough monthly costs, exact cash unknown until I check" is workable, invented MRR is not`) is the actual rule and should stay. Deleting only the slogan does not change a money decision.

## skills/founder-pivot/SKILL.md

- Line 32: “(see `docs/PLAN.md` §2 principles).” **Verdict:** SEDIMENT. **Why:** The rebuild-only-if-the-product-blocks-a-supported-direction rule is fully stated in the same sentence. The citation is an authoring breadcrumb; standalone install cannot follow it.

- Line 85, first sentence: “Nothing here needs any complement.” **Verdict:** NO-OP. **Why:** Restates the heading “Working with no complements installed.” Keep the second sentence (trail + four-option comparison + history-preserving log are plain writing from existing files) — that tells the agent what to do instead.

## skills/founder-review/SKILL.md

- Line 27: “Technical delivery is not commercial validation. A completed build does not close the commercial experiment by itself.” **Verdict:** NO-OP (within-file DRY). **Why:** The three bullets immediately above already separate technical acceptance, open commercial window, and observed metric, and they already say a ship is not a conclusion. Lines 8–9 state the same rule as the skill’s job. This is the project’s central guardrail, so it is *not* a cross-file no-op — but after the bullets in the same step it is a slogan restating a decision already specified. Keep the bullets (and keep line 73 at the inbound-handoff step, where the agent actually ticks “done”). Drop the two summary sentences on line 27.

## Summary

Total candidates found: 13. Recommended for removal: 10. Borderline (coordinator should decide): 3.

Recommended for removal: founder-start line 10; founder-start `docs/PLAN.md` citations (lines 22/34/47/101); founder-start line 105 first sentence; founder-positioning “keep this skill's own files in English”; founder-activation judging success-as-lift (rewrite, don’t just delete the rest of judging); founder-growth “library promises” + PLAN cite; founder-economics “Precision is welcome; honesty is required”; founder-pivot PLAN cite; founder-pivot “Nothing here needs any complement”; founder-review line 27 summary pair.

Borderline: founder-product-audit line 82 (keep in one place only); founder-mvp “crude is the point”; founder-first-customers “roughly a dozen.”

Files with no genuine candidates: founder-validate, founder-pricing, founder-launch, founder-retention.
