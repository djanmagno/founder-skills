# founder-skills

A public library of [Agent Skills](https://agentskills.io/specification) that takes solo founders and small bootstrapped SaaS teams (B2B-first, initially) from an idea or an existing product toward sustainable recurring revenue. US$1M ARR is used as a guiding target throughout the library — **it is a reference point, not a promise.**

## Who this is for

- Solo founders and small bootstrapped SaaS teams.
- B2B-first, at any stage: idea, manual/concierge delivery, prototype, shipped product with no traction, paying customers with churn, or a business ready to scale.
- Founders who want an agent that understands their specific business stage before recommending anything, rather than a generic startup checklist.

This library does not assume you use GitHub, a specific stack, analytics, or any formal process. It inspects what you have — including existing code, when present — and adapts.

## Install

Full library:

```bash
npx skills add djanmagno/founder-skills
```

Or clone manually and point your agent's skills directory at it:

```bash
git clone https://github.com/djanmagno/founder-skills.git
```

Each skill in `skills/<name>/SKILL.md` is also installable on its own — no skill in this library depends on files that live only at the repo root.

## The 14 skills

A single guided entry point, `founder-start`, diagnoses your business and routes you to the right next skill. Every skill below also works standalone, even if you never run `founder-start`.

| Skill | What it produces |
|---|---|
| `founder-start` | Diagnosis, persistent context, and the next action |
| `founder-product-audit` | Product map, code evidence, technical blockers tied to the business |
| `founder-validate` | Customer/problem hypothesis, interviews, demand experiments |
| `founder-positioning` | Alternatives, differentiation, positioning, and offer |
| `founder-pricing` | Price hypotheses, packaging, commercial tests |
| `founder-mvp` | Smallest useful experiment and the product changes it requires |
| `founder-first-customers` | Prospects, outreach, discovery, demo, proposal |
| `founder-launch` | Launch readiness, materials, channels, follow-through |
| `founder-activation` | First value, drop-off diagnosis, onboarding |
| `founder-retention` | Cohorts, cancellations, renewal, expansion |
| `founder-growth` | Acquisition experiments with budget and evaluation criteria |
| `founder-economics` | Recurring revenue, margin, acquisition cost, cash, scenarios |
| `founder-pivot` | Persist / reposition / pivot / shut down, decided from evidence |
| `founder-review` | Results review and the next experiment cycle |

See [`docs/PLAN.md`](docs/PLAN.md) for the full design and rationale.

## Independence

founder-skills carries the commercial reasoning and experiment continuity. It does not require, install, or modify anything else. Three other skill packages are **optional complements** you may already have installed:

- **[Matt Pocock Skills](https://github.com/mattpocock/skills)** — domain/code understanding, spec/tickets, implementation and review.
- **[Superpowers](https://github.com/obra/superpowers)** — open technical design, planning, debugging, verification.
- **[gstack](https://github.com/garrytan/gstack)** — strategic review, design/QA review, delivery.

If none of the three are installed, founder-skills works fully on its own. If one or more are present, `founder-start` detects them and hands off technical work through a simple Markdown contract (see [`docs/examples/handoff.md`](docs/examples/handoff.md)) rather than duplicating their process. See `docs/integration/` for per-package guides, each loaded only when that package is actually present.

## Language

- The skills themselves, and any package documentation, are written in English.
- The agent talks with you, and generates your business materials, **in your language** — whatever language you use to talk to it.

## Where your business data lives

This repository holds skills, not your business. Commercial context, evidence, decisions, and experiment history are kept in your business workspace — by default a local `.founder/` directory that stays out of git commits unless you choose otherwise. See [`templates/founder-context.md`](templates/founder-context.md).

## Status

This library is in active development. See [`docs/STATUS.md`](docs/STATUS.md) for implementation progress and [`docs/LEFTOVERS.md`](docs/LEFTOVERS.md) for what is intentionally out of v1.

## License

MIT for original content in this repository. Third-party sources are referenced, not copied — see [`CONTRIBUTING.md`](CONTRIBUTING.md) and [`docs/SOURCES.md`](docs/SOURCES.md).
