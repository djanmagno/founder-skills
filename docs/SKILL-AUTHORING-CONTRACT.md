# Skill authoring contract

Internal document for whoever writes a `skills/<name>/SKILL.md` in this repo — human or delegated agent. It exists because 14 skills written independently will otherwise diverge on things a reader shouldn't notice diverge. Read `skills/founder-start/SKILL.md` alongside this as the worked example; where the two disagree, the exemplar wins and this file should be corrected.

## The templates/ vs. §3 contradiction — resolved

`docs/PLAN.md` §3 requires every skill to carry its required resources **inside its own directory**, so an individually installed skill never depends on files that exist only at the repo root. §8 puts `templates/founder-context.md`, `experiment-log.md`, and `handoff.md` at the repo root.

Resolution: **root `templates/` files are human-facing reference copies, never a runtime dependency.** No `SKILL.md` may reference them by relative path (e.g. `../../templates/founder-context.md`) as something the agent needs to read to do its job. Instead:

- Each skill that writes to `.founder/context.md`, `.founder/experiments.md`, or a handoff note **inlines the exact section headers it needs** directly in its own procedure — copy the relevant structure from the root template into the skill's own Markdown, in the skill's own words where it helps clarity.
- The root `templates/` files stay as the single canonical source a human contributor edits when the shape of `.founder/` changes. If you change a section in a root template, propagate that change to every skill that inlines it — grep for the section header first.
- This means some duplication between `templates/` and individual `SKILL.md` files. That's intentional: it's the cost of "installs standalone," not an oversight to clean up.

## Frontmatter shape

```yaml
---
name: founder-<name>
description: <what it does> + <specific triggers, pushy enough that the skill fires even when the user doesn't name it explicitly> + <one line distinguishing it from the sibling skill it's most likely to be confused with>
---
```

The description is the entire triggering mechanism — a host agent decides whether to consult a skill from name + description alone, before reading the body. Since this library has 14 siblings with overlapping vocabulary (e.g. `founder-validate` vs. `founder-product-audit`, `founder-growth` vs. `founder-first-customers`), every description must name what it does NOT cover, not just what it does. See `docs/PLAN.md` §3 "avoids overlap."

## Section order (match `founder-start`)

1. **What this skill does** — one paragraph, plain language.
2. **When to use it / when not to** — the disambiguation from sibling skills, expanded from the frontmatter description.
3. **Minimum required context** — what has to be known before this skill can do useful work; where to get it if it's missing (usually: ask, or read `.founder/context.md` if present).
4. **Procedure** — decision-oriented steps. Not a rigid script; explain the *why* behind each step per the writing-style guidance in the skill-creator instructions this project was bootstrapped under (theory of mind over rigid MUSTs).
5. **Deliverables** — what gets produced, and where it's saved (usually somewhere under `.founder/`, using the section headers inlined per the resolution above).
6. **Judging results / routing the next action** — how to tell if this skill's output actually succeeded, and which sibling skill is the likely next step.
7. **Working with no complements installed** — the fully self-contained path. This is the default; complement integration is an enhancement on top of it, never a requirement.
8. **Optional: complement integration** — only if this skill has a natural connection point per `docs/PLAN.md` §4. Load the relevant `docs/integration/<package>.md` guide's content by reference, and only mention it conditional on that complement being detected. Do not invoke `to-spec` / `to-tickets` or any other explicit-invocation skill automatically — prepare the context and name the call for the user instead.

## Vocabulary that must stay consistent across all 14 skills

- The 11 business situations from `docs/PLAN.md` §2 — use the same short names everywhere (e.g. "idea with no product," "customers with churn"), don't invent synonyms per-skill.
- Evidence tiers: **stated intent → commitment → payment → recurring use**. Never call a signup a "commitment" or a trial a "payment."
- `.founder/context.md`, `.founder/experiments.md` (or `.founder/experiments/<name>.md`) as the default file names — pick one experiments layout across all skills, don't let each skill invent its own.
- "Technical delivery is not commercial validation" — this principle recurs across `founder-mvp`, `founder-launch`, `founder-review`, and any skill that hands off to a complement. State it the same way each time.

## Hard rules for anyone (human or delegated agent) writing skills here

- **English only**, in every `SKILL.md` and every `docs/` file. The founder's own language is only for live conversation and generated business materials — never for the skill files themselves.
- **Do not invent interviews, customers, metrics, or evidence** anywhere in a skill's example text or procedure — model the discipline the skill is supposed to enforce.
- **Do not import conventions, architecture, or tracking files from any sibling repo on this machine** (there are several `swe-factory-*` projects nearby — none of their patterns apply here; this project is explicitly independent, `docs/PLAN.md` §1).
- **Do not `git add` or commit.** Leave changes in the working tree; the coordinator reviews and commits with the exact message specified in `docs/PLAN.md` §13 for that task.
- High churn is never answered by default with "get more customers" — retention and acquisition are different problems; see `docs/PLAN.md` §2 principles.
