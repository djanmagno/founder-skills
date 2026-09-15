# Proposed fix found applied to the working tree, reverted (not authored by the E01-E08 fork)

Found live (uncommitted) in `skills/founder-start/SKILL.md`, `skills/founder-validate/SKILL.md`, and `skills/founder-product-audit/SKILL.md` while running E02, mid-batch. Not made by this fork (E01-E08 via codex) — this fork only ran Bash/Read/Write inside `/tmp/eval-runs-codex/`, never touched `skills/`. Reverted per the coordinator's instruction to never edit skills/templates/docs during eval runs; preserved here verbatim for the coordinator's own review/decision.

## skills/founder-start/SKILL.md

Step 6 changed from:

> 6. **Detect installed complements without installing anything.** Check whether Matt Pocock Skills, Superpowers, or gstack are present in this environment. Record what's detected and, if the founder has already been using one of them for technical work, note that as their standing preference — re-check only on a material change or conflict, not every session.

to:

> 6. **Detect installed complements without installing anything — and without over-claiming.** Check whether Matt Pocock Skills, Superpowers, or gstack are available to use *for this founder's project* — the project's own available-skills listing, an installed-skills directory inside the project or its host tool's project-scoped config, or the founder telling you directly. Do not treat a package installed somewhere on the operator's machine generally (a global plugin cache, a user-level config unrelated to this project) as "present" for this business — a complement genuinely available in one project is not automatically available in another, and reporting it as present when you only found it by scanning outside the project's own scope is exactly the kind of invented evidence this library exists to prevent. If you can't positively confirm a complement is available *for this project*, record it as "not detected" or "unknown," never as present. Record what's actually detected and, if the founder has already been using one of them for technical work, note that as their standing preference — re-check only on a material change or conflict, not every session.

**Rationale (inferred):** directly targets the E03 finding — `founder-start` fabricated "gstack: present in environment" in a workspace with zero gstack fixtures. This rewrite makes "present" require positive, project-scoped confirmation, closing that fabrication path.

## skills/founder-validate/SKILL.md

"When to use it / when not to" section, appended sentence:

> Use it for idea with no product, ready product with no commercial validation, or when existing "validation" is only stated intent. Use it when the founder is about to build because they are excited, not because a named customer has a named problem. Do not use it to audit the codebase (`founder-product-audit`), to pick alternatives and an offer (`founder-positioning`), to package and price (`founder-pricing`), or to specify engineering (`founder-mvp`). Do not use it as a substitute for `founder-first-customers` once the hypothesis is specific enough to sell — interviews are not a pipeline. **If real code or a real prototype already exists and hasn't gone through `founder-product-audit` yet, run that first, even briefly — even when the founder's message already summarizes what's built, a summary is not the same as classifying each capability as implemented, verified, or still a hypothesis. Don't skip straight to a demand-validation motion just because the founder's own account of their code sounds complete.**

**Rationale (inferred):** directly targets the other E03 finding — `founder-validate`'s own scope was broad enough to swallow the "partial prototype with existing code" case, so the agent refused to route to `founder-product-audit` ("we know what's built") and went straight to a generic demand-validation motion instead.

## skills/founder-product-audit/SKILL.md

Frontmatter `description` changed from:

> Map what a founder's product actually does — implemented flows, verified behavior, and commercial hypotheses — by inspecting the code, live product, or manual delivery when any of those exist, and name technical blockers only when they obstruct a business experiment. Use this when the founder has a prototype or shipped product and asks "what's actually built," "audit the product," "should we rebuild," or needs a product map before the next commercial step. Do not use it to validate demand or talk to customers (founder-validate), to design the smallest next experiment (founder-mvp), or to diagnose why users drop off after signup (founder-activation).

to:

> Map what a founder's product actually does — implemented flows, verified behavior, and commercial hypotheses — by inspecting the code, live product, or manual delivery when any of those exist, and name technical blockers only when they obstruct a business experiment. Use this whenever a founder describes an existing prototype or shipped product and asks what to focus on next, even if they've already summarized what's built in their own words — a founder's summary is not a classification into implemented/verified/hypothesis, and this skill is what produces that classification before any other skill acts on it. Also use it for direct asks like "what's actually built," "audit the product," or "should we rebuild." Do not use it to validate demand or talk to customers (founder-validate), to design the smallest next experiment (founder-mvp), or to diagnose why users drop off after signup (founder-activation).

**Rationale (inferred):** the triggering half of the same E03 fix — makes the description itself claim the "founder describes existing code in their own words" case, which is exactly the phrasing pattern E03's opening message used ("I've got about 60% of a product built...").

## Disposition

Reverted via `git checkout -- skills/founder-start/SKILL.md skills/founder-validate/SKILL.md skills/founder-product-audit/SKILL.md`. The coordinator decides separately whether to apply this fix (or a refinement) after reviewing all eval results, not mid-run.
