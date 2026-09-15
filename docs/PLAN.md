# founder-skills — Unified plan

> Canonical document. Merges the original `PLAN.md` (integration, packaging, acceptance) and `PLAN2.md` (decisions, behavior, sources, validation).
>
> **For agents:** implement task-by-task from section 13. Do not import swe-factory conventions.

**Goal:** a public English-language skill library that takes solo founders and small bootstrapped SaaS teams (initially B2B) from an idea or existing product to sustainable recurring revenue, with US$1M ARR as a guiding target — not a promise.

**Architecture:** commercial reasoning and experiment continuity live in founder-skills. Matt Pocock Skills, Superpowers, and gstack are used only when installed and authorized. Each skill works standalone. Business state lives in the business workspace (default `.founder/`), not in this library repo.

**Stack / distribution:** Agent Skills (`skills/<name>/SKILL.md`), install via `npx skills add djanmagno/founder-skills` or manual clone, MIT for original content, initial validation on Claude Code and Codex.

---

## 1. Goal and confirmed decisions

Create the public repository **djanmagno/founder-skills** at `~/dev/src/github/djanmagno/founder-skills`.

The agent talks in the user's language, understands the business stage, executes authorized actions, and tracks results across sessions.

**US$0 → US$1M ARR** describes the path from zero revenue to sustainable recurring revenue with little capital. “US$0” allows small, explicit costs; it is not a literally zero budget. It does not imply a guaranteed outcome or a deadline.

### Project

| Decision | Value |
|---|---|
| GitHub | `djanmagno/founder-skills` |
| Directory | `~/dev/src/github/djanmagno/founder-skills` |
| Audience | solo founders and small bootstrapped SaaS teams, B2B-first |
| Language of skills and package docs | English |
| Language of interaction and generated materials | the user's language |
| License for original content | MIT |
| Experience | one guided entry (`founder-start`) plus skills that work individually |
| Capability | diagnose and execute authorized actions |
| Knowledge | self-contained references; gbrain optional, never an install requirement |
| Authorization already given | create the directory and the public repo; implementation happens in that project |

### Independence

- This is a **separate** project from swe-factory. Do not import that repo's conventions, architecture, tracking files, or processes.
- Matt Pocock Skills, Superpowers, and gstack are **optional complements**. The library works without any of them.
- This package must not install, update, or modify the other packages automatically.

---

## 2. Expected behavior

### Understand each business before acting

The agent discovers, without assuming a stack:

- What the founder intends to achieve.
- Who uses, who buys, and which problem is solved.
- What exists: idea, manual service, prototype, code, shipped product.
- Evidence: interviews, commitments, payments, usage, and retention.
- Constraints on time, money, skills, and delivery capacity.
- Existing documentation, tools, and processes, when present.

Do not assume GitHub, a specific stack, particular files, analytics, engineering practices, or formal processes.

When code exists, inspect it. Distinguish:

1. implemented functionality
2. verified behavior
3. commercial hypothesis

A built product does not prove demand. Isolated revenue does not prove sustainable growth. Shipped code and a validated commercial hypothesis are separate states.

### Situations to cover (they may coexist)

Diagnosis names the **main obstacle** and the **next experiment**. It does not impose a fixed sequence.

1. Idea with no product.
2. Problem validated through manual delivery or concierge service.
3. Partial prototype that needs adjustments.
4. Ready product with no commercial validation.
5. Published product with no acquisition or interest.
6. Free users with no conversion.
7. Paying customers with weak activation or high churn.
8. Happy customers with no repeatable acquisition.
9. Growth limited by margin, support, or customer concentration.
10. Business with consistent acquisition and retention, seeking expansion.
11. Need to reposition, pivot, or kill a hypothesis.

Compact mapping (stage × obstacle):

- idea with no product
- product with no validation
- launch with no traction
- users with no conversion
- customers with churn
- retention without repeatable acquisition
- growth limited by margin or operational capacity

### Work cycle

**Understand → prioritize → execute → observe → decide.**

Each experiment records: hypothesis, action, owner, cost, metric, observation window, evidence, and decision. Missing data stays unknown. Pivots keep history and mark superseded decisions.

### Principles

- Do not invent interviews, results, customers, or metrics.
- Distinguish stated intent, commitment, payment, and recurring use.
- Do not treat feature count or signups as proven demand.
- Do not turn checklist numbers into universal rules.
- Do not recommend a rebuild only because the product lacked traction.
- Separate technical delivery from commercial validation.
- Respect current scope and authorizations for contacts, publishing, spend, and production.
- High churn does **not** automatically recommend more acquisition.
- Do not turn a commercial task into engineering when interviews, materials, or manual delivery will do.
- Distinguish recurring revenue, one-off services, pipeline, and cash.
- Technical success is not recorded as commercial validation.

---

## 3. First-version catalog (14 skills)

A guided entry identifies the main obstacle and routes onward. Each skill also works standalone — even if the user never ran `founder-start`.

| Skill | Primary deliverable | Responsibility |
|---|---|---|
| `founder-start` | Diagnosis, persistent context, and next action | Understand the business, recover context, and name the next step |
| `founder-product-audit` | Product map, code evidence, and business-linked technical blockers | Map flows, capabilities, and technical obstacles |
| `founder-validate` | Customer/problem hypothesis, interviews, and demand experiments | Define customer/problem and evaluate demand evidence |
| `founder-positioning` | Alternatives, differentiation, positioning, and offer | Compare alternatives and produce a clear offer |
| `founder-pricing` | Price hypotheses, packaging, and commercial tests | Set price/packaging and test willingness and ability to pay |
| `founder-mvp` | Smallest useful experiment and required product changes | Define the smallest experiment and execute or specify changes |
| `founder-first-customers` | Prospects, outreach, discovery, demo, and proposal | Prospecting, discovery, demo, proposal, and follow-up |
| `founder-launch` | Readiness, materials, channels, and follow-through | Launch proportional to the product and audience |
| `founder-activation` | First value, drop-off diagnosis, and onboarding | Define first value and reduce early abandonment |
| `founder-retention` | Cohorts, cancellations, renewal, and expansion | Analyze retention and expansion without confusing them with acquisition |
| `founder-growth` | Acquisition experiments with budget and evaluation criteria | Choose and evaluate acquisition and distribution channels |
| `founder-economics` | Recurring revenue, margin, acquisition, cash, and scenarios | Model unit economics and cash constraints |
| `founder-pivot` | Compare persist, reposition, pivot, or shut down | Decide from evidence while preserving history |
| `founder-review` | Results review and next cycle | Update decisions and choose the next experiment |

### Contract for every skill

Each skill will have:

- Clear triggers and a description that avoids overlap.
- Minimum required context.
- A decision-oriented procedure.
- Concrete deliverables.
- Criteria to judge results and route the next action.
- References and templates only when they add value.
- Guidance to work with no complements installed.
- Required resources **inside the skill directory** (individual install must not depend on files that exist only at the repo root).

---

## 4. Optional integration with the three packages

founder-skills keeps commercial reasoning and experiment continuity. Complements help with code discovery, design, engineering, review, and delivery.

### Flow selection

`founder-start` detects available skills and reads relevant project instructions. It records the existing preference and re-checks only when there is a material change or conflict.

1. Follow the flow defined by the project.
2. If none exists, use capabilities compatible with the task and current authorization.
3. When equivalent alternatives exist, choose **one** owner per step.
4. With no integrations installed, continue on the self-contained flow.
5. Do not install, update, or modify the other packages automatically.
6. Resolve names from the real install, including namespaces and invocation restrictions.
7. Read the installed skill before invoking it; names and effects vary by version.
8. Honor explicit-invocation skills (`disable-model-invocation: true`). In those cases, prepare the context and the call for the user.
9. Do not skip required steps of the chosen complement.
10. If a tool is missing, continue with what is available or produce a usable work handoff.

### Connection points

| Need | Integration |
|---|---|
| Understand domain and code boundaries | Matt: `domain-modeling`, `codebase-design` |
| Turn a commercial change into spec and tickets | Matt: `to-spec`, `to-tickets` (explicit invocation) |
| Execute via the Matt process already adopted | Matt: `implement`, `tdd`, `code-review` |
| Resolve still-open technical design | Superpowers: `brainstorming` |
| Plan and implement a change | Superpowers: `writing-plans` and the executor appropriate to the environment |
| Investigate failures and verify results | Superpowers: `systematic-debugging`, `test-driven-development`, review, `verification-before-completion` |
| Challenge a material strategic decision | gstack: `office-hours` or `plan-ceo-review` |
| Review engineering, experience, or design | gstack: `plan-eng-review`, `plan-design-review`; `plan-devex-review` when the product serves developers |
| Investigate the live product experience | gstack: `browse`, `qa-only`; `qa` when fixes are in scope |
| Prepare technical delivery and verify production | gstack: `ship`, `land-and-deploy`, `canary`, per authorization and project flow |
| Learn from engineering execution | gstack: `retro`, as input to `founder-review` |

Role by package (summary):

| Complement | Useful connections |
|---|---|
| Matt Pocock Skills | domain/code; spec/tickets; implementation/TDD/review when that is the chosen flow |
| Superpowers | open design; plan and execution; debug, tests, review, and verification |
| gstack | office-hours and plan reviews; browser/QA; design; PR and delivery within authorized scope |

### Verified distinctions (do not collapse)

- Matt `to-spec` and `to-tickets` require explicit invocation. Sources: [to-spec](https://github.com/mattpocock/skills/blob/main/skills/engineering/to-spec/SKILL.md), [to-tickets](https://github.com/mattpocock/skills/blob/main/skills/engineering/to-tickets/SKILL.md).
- Superpowers receives commercial context and produces the technical plan in its own format. Source: [writing-plans](https://github.com/obra/superpowers/blob/main/skills/writing-plans/SKILL.md).
- gstack `qa-only` produces a report; `qa` may fix and create commits. Source: [qa-only](https://github.com/garrytan/gstack/blob/main/qa-only/SKILL.md).
- gstack `ship` includes commits, push, and PR creation; production deploy is a distinct action. Source: [ship](https://github.com/garrytan/gstack/blob/main/ship/SKILL.md).
- Distinguish diagnosis, correction, and publication. Do not claim approvals or verifications that did not happen.

Research covers relevant catalogs and flows. It does not assume every external skill has been read in full or is compatible. Record consulted versions or commits and known limitations.

### Avoid duplicate processes

- Reuse discoveries and decisions already recorded.
- Do not run three equivalent discovery interviews or three equivalent planning passes.
- Choose one executor and one testing discipline per change.
- Add extra reviews only when they evaluate distinct questions.
- Preserve the real requirements of the selected package.

---

## 5. Context handoff contract

Each handoff (founder-skills → complement, and back) uses simple Markdown with:

**Outbound**

- Problem, customer, and evidence.
- Commercial hypothesis and expected result.
- Requested change, scope, constraints, and current authorization.
- Technical acceptance criteria.
- Commercial metric and observation window.
- References to existing documents.

**Inbound**

- Changes made.
- Verification evidence.
- Open items.
- Links to spec, tickets, diffs, tests, and artifacts.

`founder-review` records the result and resumes the experiment. Shipped code does **not** automatically close the commercial experiment.

Technical documents stay where the project and packages keep them. `.founder/` stores commercial references and conclusions, avoiding divergent copies. Do not duplicate documents only to fit this library.

---

## 6. Persistence and business state

- Reuse the documentation location the user already chose.
- With no convention, offer `.founder/` in the **business workspace** as the default for context, evidence, decisions, metrics, experiments, and materials.
- Create only the files needed.
- Sensitive commercial information stays local, **out of commits by default**.
- Decision history is preserved; pivots identify what new evidence superseded.
- Each individual skill works even without a prior `founder-start`.

---

## 7. Sources and research for implementation

Consult the real relevant files, record the commit consulted, and distinguish **research** from **tested integration**. Do not modify, export, or publish the gbrain corpus in order to research.

### Primary repositories

| Source | Use |
|---|---|
| [mattpocock/skills](https://github.com/mattpocock/skills) | Structure, composition, specs, tickets, and engineering complement |
| [obra/superpowers](https://github.com/obra/superpowers) | Design, planning, implementation, and verification |
| [garrytan/gstack](https://github.com/garrytan/gstack) | Strategy, design, QA, and delivery |
| [EdoStra/Marketing-for-Founders](https://github.com/EdoStra/Marketing-for-Founders) | Customer research, channels, launch, positioning, and first users |
| [sickn33/antigravity-awesome-skills](https://github.com/sickn33/antigravity-awesome-skills) | saas-mvp-launcher reference; confirm redirects and current location |

Especially relevant files:

- [Matt — to-spec](https://github.com/mattpocock/skills/blob/main/skills/engineering/to-spec/SKILL.md)
- [Matt — to-tickets](https://github.com/mattpocock/skills/blob/main/skills/engineering/to-tickets/SKILL.md)
- [Superpowers — writing-plans](https://github.com/obra/superpowers/blob/main/skills/writing-plans/SKILL.md)
- [gstack — office-hours](https://github.com/garrytan/gstack/blob/main/office-hours/SKILL.md)
- [gstack — qa-only](https://github.com/garrytan/gstack/blob/main/qa-only/SKILL.md)
- [gstack — ship](https://github.com/garrytan/gstack/blob/main/ship/SKILL.md)
- [SaaS MVP Launcher](https://github.com/sickn33/agentic-awesome-skills/blob/main/skills/saas-mvp-launcher/SKILL.md)

### Documents provided by the user

- [YC Startup Library](https://startup-library.ycombinator.com)
- [YC Library](https://www.ycombinator.com/library)
- [AO Network — GTM Launch Checklist](https://aonetwork.com/templates/gtm-launch-checklist-template)
- [Code & Tell — SaaS Launch Checklist](https://codeandtell.com/blog/saas-launch-checklist)
- [Sell Successfully — B2B SaaS GTM Checklist](https://sellsuccessfully.io/blog/go-to-market-checklist-saas-launch/)

The briefing mentions The Mom Test, interviews, and the Superhuman product-market fit case. **Full texts were not provided**; do not present those readings as completed.

### Gbrain YC on this machine (state of the original research)

- Executable: `/Users/user01/.bun/bin/gbrain`
- Source found: `default`
- Inventory: 420 pages — 394 transcripts and 26 notes (the user had reported ~397 transcripts)
- **16 representative transcripts** were read, not the full corpus
- Commands: `gbrain sources list`, `gbrain list`, `gbrain search`, `gbrain get` — consult installed help for filters
- gbrain is an additional source **during use**, never a requirement to install the skills

Transcripts consulted:

| Theme | Sources |
|---|---|
| Ideas and interviews | [How to Get and Test Startup Ideas](https://www.youtube.com/watch?v=vDXkpJw16os), [How To Talk To Users](https://www.youtube.com/watch?v=z1iF1c8w5Lg) |
| MVP and launch | [How To Build An MVP](https://www.youtube.com/watch?v=qRZ_l7CVzZU), [The Best Way To Launch Your Startup](https://www.youtube.com/watch?v=u36A-YTXiow) |
| First customers and sales | [First 10 Customers](https://www.youtube.com/watch?v=_FBivfgOvuE), [Enterprise Sales](https://www.youtube.com/watch?v=0fKYVl12VTA), [Sales Playbook For Founders](https://www.youtube.com/watch?v=DH7REvnQ1y4) |
| Pricing and models | [How To Price For B2B](https://www.youtube.com/watch?v=4hjiRmgmHiU), [Startup Business Models and Pricing](https://www.youtube.com/watch?v=oWZbWzAyHAE) |
| Retention and PMF | [How To Keep Your Users](https://www.youtube.com/watch?v=VNxBZ7ka5J0), [The Real Product Market Fit](https://www.youtube.com/watch?v=FBOLk9s9Ci4), [Peter Reinhardt / Segment](https://www.youtube.com/watch?v=l-vfn97QTr0) |
| Bootstrap and scale | [Bootstrap or Raise Venture Capital?](https://www.youtube.com/watch?v=D81y-kh11oI), [Building A $2 Billion SaaS Company](https://www.youtube.com/watch?v=rjyJsbUunQ4) |
| Pivots | [Favorite Pivot Stories](https://www.youtube.com/watch?v=DmehFuCMtvc), [From Pivot Hell To $1.4 Billion Unicorn](https://www.youtube.com/watch?v=5WN8bfG06Hk) |

### Format, attribution, and packaging

- [Agent Skills — specification](https://agentskills.io/specification)
- [Skills CLI — install](https://www.skills.sh/docs/cli)
- [Marketing-for-Founders — license](https://github.com/EdoStra/Marketing-for-Founders/blob/main/LICENSE.md)

Rules:

- Structure `skills/<name>/SKILL.md`, with references and templates as needed.
- Skills installable in isolation, with no hidden dependencies.
- Per-package integration guides, loaded **only when applicable**.
- Produce original syntheses and procedures, with traceable references.
- Original content under MIT; third-party attribution and licenses identified.
- Marketing-for-Founders uses CC BY-SA; that license is not the same as the licenses of external pages.
- Do not copy collections, templates, or full transcripts into the MIT content.
- Synthesize YC and marketing sources; gbrain optional, without distributing full transcripts.
- Compatibility initially validated on Codex and Claude Code.

---

## 8. Repository file structure

Map to create. Each file has one responsibility.

```
founder-skills/
  README.md                          # install, entry cases, examples
  LICENSE                            # MIT
  CONTRIBUTING.md                    # contribution and attribution limits
  docs/
    PLAN.md                          # this plan
    STATUS.md                        # implementation progress
    LEFTOVERS.md                     # what is out of v1 and why
    SOURCES.md                       # consulted commits/versions and limitations
    COMPATIBILITY.md                 # Claude Code, Codex, known constraints
    integration/
      matt-pocock.md                 # guide loaded only if Matt is present
      superpowers.md
      gstack.md
    examples/
      handoff.md                     # complete outbound/inbound example
  skills/
    founder-start/SKILL.md
    founder-product-audit/SKILL.md
    founder-validate/SKILL.md
    founder-positioning/SKILL.md
    founder-pricing/SKILL.md
    founder-mvp/SKILL.md
    founder-first-customers/SKILL.md
    founder-launch/SKILL.md
    founder-activation/SKILL.md
    founder-retention/SKILL.md
    founder-growth/SKILL.md
    founder-economics/SKILL.md
    founder-pivot/SKILL.md
    founder-review/SKILL.md
  templates/                         # only what skills reference
    founder-context.md
    experiment-log.md
    handoff.md
  evals/
    README.md
    scenarios/                       # one file per situation in section 2
```

`.founder/` does **not** live in this repository (except example templates). It lives in the business workspace.

---

## 9. Implementation sequence

1. Create the new project, minimal README, LICENSE, `docs/STATUS.md`, `docs/LEFTOVERS.md`, and record this design.
2. Consolidate sources, evidence rules, the context contract (`.founder/` + templates), and `docs/SOURCES.md`.
3. Implement `founder-start`, `founder-product-audit`, `founder-validate`, and `founder-review`.
4. Implement offer, pricing, MVP, first customers, and launch.
5. Implement activation, retention, growth, economics, and pivot.
6. Implement integration guides and complete handoff examples.
7. Run evaluations with independent agents, fix failures, publish on GitHub, and cut the first version.

v1 includes the **14 skills** and the **three optional integrations** documented, with tested capabilities and explicit limitations.

Keep `docs/STATUS.md` and `docs/LEFTOVERS.md` updated each phase.

---

## 10. Acceptance criteria

Union of both source plans. v1 closes only if all pass.

### Packaging and install

- Frontmatter, names, local references, and install are valid.
- Full install and individual install of each skill work.
- Each isolated skill carries its required resources (no dependence on root-only files).
- Compatibility verified initially on Claude Code and Codex.

### Business coverage

- All 11 situations in section 2 have evaluation scenarios with fictional data, run with independent agents.
- A project **without** defined processes works.
- A project **with** different conventions keeps its organization.
- Resumed sessions preserve context, evidence, and decisions.

### Integrations

- Absence of the three complements does not block use; it yields a usable alternative.
- With one package, and with all three, the project flow is respected, with no routing loops.
- Explicit-invocation skills are honored.
- Invocation and authorization restrictions are preserved.
- Publishing, contacts, spend, and production respect current authorization.

### Evidence and economics

- A ready product is not confused with validated demand.
- High churn does not automatically recommend more acquisition.
- Missing data is not invented; missing metrics do not produce invented conclusions.
- Calculations distinguish recurring revenue, one-off revenue, pipeline, and cash.
- Technical changes have proportional acceptance criteria and verification, tied to the experiment.
- Code delivery does not automatically close the commercial experiment.
- Technical success is not recorded as commercial validation.

---

## 11. Evaluation (evals)

One fictional scenario per situation in section 2, plus cross-cutting cases:

| ID | Situation | Expected skills | Fail if… |
|---|---|---|---|
| E01 | Idea with no product | start → validate | skip to build/MVP with no customer hypothesis |
| E02 | Concierge / manual service | validate, mvp | recommend rebuilding the product first |
| E03 | Partial prototype | product-audit, mvp | ignore existing code |
| E04 | Ready product, no validation | validate, positioning | treat “shipped” as demand |
| E05 | Published with no traction | launch, first-customers, growth | increase ads without evidence |
| E06 | Free users, no conversion | activation, pricing, first-customers | only ask for more features |
| E07 | Paying customers with churn | activation, retention | recommend more acquisition |
| E08 | Happy customers, no repeatable acquisition | growth, first-customers | pivot the product without cause |
| E09 | Limited by margin/capacity | economics, pricing | ignore unit economics |
| E10 | Consistent acquisition + retention | growth, economics | force a pivot |
| E11 | Pivot / kill a hypothesis | pivot, review | erase decision history |
| E12 | No complements installed | any skill | refuse work or require install |
| E13 | Matt + Superpowers + gstack present | start + handoff | three equivalent planning passes |
| E14 | `to-spec` / `to-tickets` | mvp / audit | invoke automatically |
| E15 | Resumed session | start, review | lose decisions or invent metrics |

Each eval uses fictional data, states what the agent **must not** invent, and records the expected complement (none / one / three).

---

## 12. Out of scope for v1 (record in LEFTOVERS.md)

- A promise of US$1M ARR or a fundraising playbook.
- A skills marketplace, web dashboard, or SaaS of this library.
- Automatic installation of the three complements.
- Distribution of YC transcripts or full CC BY-SA templates.
- B2C, marketplace, hardware, or non-SaaS as the focus.
- Conventions, CI, or scaffolding copied from swe-factory.
- Reading the full Matt / Superpowers / gstack catalogs as a v1 prerequisite; only the connection points in section 4.

---

## 13. Implementation tasks

Each task produces a testable deliverable. Global constraints from section 1 and criteria from section 10 apply to all.

### Task 1: Repository scaffold

**Files:** create `README.md`, `LICENSE`, `CONTRIBUTING.md`, `docs/STATUS.md`, `docs/LEFTOVERS.md`, `docs/SOURCES.md`, `docs/COMPATIBILITY.md`

- [ ] Initialize git in the project directory (if it is not already a repo).
- [ ] MIT `LICENSE` for original content.
- [ ] English `README.md`: what it is, who it is for, install (`npx skills add djanmagno/founder-skills` + manual clone), 14 skills, independence from the three packages, interaction language vs. skill language, warning that US$1M ARR is not a promise.
- [ ] `CONTRIBUTING.md`: original syntheses, attribution, CC BY-SA vs MIT, do not copy transcripts.
- [ ] `docs/STATUS.md` with the 7 phases from section 9, all open.
- [ ] `docs/LEFTOVERS.md` with section 12.
- [ ] `docs/SOURCES.md` with the section 7 table and a field for consulted commit SHA.
- [ ] `docs/COMPATIBILITY.md`: Claude Code and Codex; “other tools: untested”.
- [ ] Commit: `docs: scaffold founder-skills repo and tracking files`

### Task 2: Context contract and templates

**Files:** create `templates/founder-context.md`, `templates/experiment-log.md`, `templates/handoff.md`

- [ ] Context template: goal, user, buyer, problem, what exists, evidence, constraints, authorizations, links to technical docs (do not copy them).
- [ ] Experiment template: hypothesis, action, owner, cost, metric, window, evidence, decision.
- [ ] Handoff template (outbound and inbound) per section 5.
- [ ] Explicit instruction: sensitive data local, out of git by default; create only what is needed; reuse the user's convention if it exists.
- [ ] Commit: `feat: add founder context, experiment, and handoff templates`

### Task 3: Core — start, audit, validate, review

**Files:** `skills/founder-start/SKILL.md`, `skills/founder-product-audit/SKILL.md`, `skills/founder-validate/SKILL.md`, `skills/founder-review/SKILL.md` (+ local references if needed)

Each SKILL.md in English, with valid frontmatter (name, description/triggers), procedure, deliverables, routing criteria, fallback with no complements.

- [ ] `founder-start`: diagnose the 11 situations, persist context, choose the next skill, optionally detect complements without installing them.
- [ ] `founder-product-audit`: product map; inspect code if present; separate implemented / verified / hypothesis.
- [ ] `founder-validate`: customer/problem hypothesis, interviews, demand experiments; do not invent evidence.
- [ ] `founder-review`: close the cycle, update decisions, do not treat a technical ship as commercial validation.
- [ ] Commit: `feat: add start, product-audit, validate, and review skills`

### Task 4: Offer through launch

**Files:** `skills/founder-positioning/SKILL.md`, `skills/founder-pricing/SKILL.md`, `skills/founder-mvp/SKILL.md`, `skills/founder-first-customers/SKILL.md`, `skills/founder-launch/SKILL.md`

- [ ] Positioning: alternatives, differentiation, offer.
- [ ] Pricing: packaging, willingness/ability-to-pay tests; distinguish recurring vs one-off.
- [ ] MVP: smallest useful experiment; engineering only if the hypothesis requires it; hand off to spec/tickets when appropriate.
- [ ] First customers: prospecting, discovery, demo, proposal, follow-up; respect contact authorization.
- [ ] Launch: proportional readiness; materials and channels; follow-through.
- [ ] Commit: `feat: add positioning, pricing, mvp, first-customers, and launch skills`

### Task 5: Activation through pivot

**Files:** `skills/founder-activation/SKILL.md`, `skills/founder-retention/SKILL.md`, `skills/founder-growth/SKILL.md`, `skills/founder-economics/SKILL.md`, `skills/founder-pivot/SKILL.md`

- [ ] Activation: first value, drop-off, onboarding.
- [ ] Retention: cohorts, churn, renewal, expansion; do **not** answer churn with more acquisition.
- [ ] Growth: acquisition experiments with budget and criteria.
- [ ] Economics: ARR vs one-off vs pipeline vs cash; margin; customer concentration.
- [ ] Pivot: persist / reposition / change segment-product / shut down; preserve history.
- [ ] Commit: `feat: add activation, retention, growth, economics, and pivot skills`

### Task 6: Integration guides and examples

**Files:** `docs/integration/matt-pocock.md`, `docs/integration/superpowers.md`, `docs/integration/gstack.md`, `docs/examples/handoff.md`

- [ ] One guide per package: when to use, what **not** to do, explicit invocation, one owner per step.
- [ ] Section 4 table in each guide, only that package's rows.
- [ ] Complete outbound/inbound example (problem → spec/tickets or plan → diff/tests → founder-review).
- [ ] Skills load the guide **only** if the complement is present.
- [ ] Commit: `docs: add optional integration guides and handoff example`

### Task 7: Evals, fixes, and publish

**Files:** `evals/README.md`, `evals/scenarios/E01.md` … `E15.md`

- [ ] Write the 15 scenarios from section 11 with fictional data and explicit failure conditions.
- [ ] Run evaluations with independent agents in modes: isolated, one complement, three complements.
- [ ] Fix failures found; note limitations in `docs/SOURCES.md` and `docs/COMPATIBILITY.md`.
- [ ] Update `docs/STATUS.md` and `docs/LEFTOVERS.md`.
- [ ] Publish the public repo and create the first tag/version.
- [ ] Commit(s): `test: add business-situation evals` and `chore: cut v0.1.0`

---

## 14. Coverage vs. the two originals

| Theme | Original PLAN | PLAN2 | This document |
|---|---|---|---|
| Goal, audience, language, MIT, GitHub path | yes | yes | §1 |
| Independence from swe-factory | — | yes | §1 |
| Authorization to create the repo | — | yes | §1 |
| Understand the business before acting | partial | yes | §2 |
| 11 situations + coexistence | 7 stages | 11 situations | §2 (both) |
| Cycle and evidence principles | partial | yes | §2 |
| Catalog of 14 skills | deliverable | responsibility | §3 (union) |
| Internal contract per skill | — | yes | §3 |
| Connection-point table | yes | summarized | §4 |
| Flow-selection rules | yes | yes | §4 |
| Distinctions to-spec / qa-only / ship | yes | yes | §4 |
| Outbound/inbound handoff contract | yes | yes | §5 |
| `.founder/` vs user convention | `.founder/` fixed | reuse convention | §6 (convention first) |
| Sources, URLs, gbrain, transcripts | summarized | complete | §7 |
| CC BY-SA vs MIT attribution | yes | yes | §7 |
| File structure | implicit | implicit | §8 (explicit) |
| 6–7 phase sequence | yes | yes | §9 |
| STATUS.md and LEFTOVERS.md | yes | — | §9, Task 1 |
| Acceptance criteria | yes | yes + churn/evals | §10 (union) |
| Evals E01–E15 | “evaluations” | situations from §2 | §11 |
| Out of scope | implicit | implicit | §12 |
| Actionable tasks | phases | phases | §13 |

Nothing material from either original was dropped. Conflict resolved: persistence — **reuse the user's convention**; `.founder/` is the default only when none exists.
