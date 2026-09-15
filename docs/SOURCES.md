# Sources consulted

Per `docs/PLAN.md` §7. Records what was consulted, at what depth, and any known limitation — so a reader can tell "researched" apart from "tested integration." Fill in the commit SHA / access date columns as each source is actually consulted during implementation; don't backfill from memory.

## Primary repositories (integration research)

| Source | Use | Commit / version consulted | Depth | Known limitation |
|---|---|---|---|---|
| [mattpocock/skills](https://github.com/mattpocock/skills) | Structure, composition, specs, tickets, engineering complement | Verified reachable 2026-09-15 | Connection-point files only (`to-spec`, `to-tickets`) | Full catalog not read; other skills in that package unverified |
| [obra/superpowers](https://github.com/obra/superpowers) | Design, planning, implementation, verification | Verified reachable 2026-09-15 | Connection-point files only (`writing-plans`) | Full catalog not read |
| [garrytan/gstack](https://github.com/garrytan/gstack) | Strategy, design, QA, delivery | Verified reachable 2026-09-15 | Connection-point files only (`office-hours`, `qa-only`, `ship`) | Full catalog not read |
| [EdoStra/Marketing-for-Founders](https://github.com/EdoStra/Marketing-for-Founders) | Customer research, channels, launch, positioning, first users | Verified reachable 2026-09-15 | Read for synthesis, not copied | Licensed CC BY-SA (LICENSE.md content confirmed 2026-09-15) — do not mix verbatim into MIT content, see CONTRIBUTING.md |
| [sickn33/agentic-awesome-skills](https://github.com/sickn33/agentic-awesome-skills) | `saas-mvp-launcher` reference | Verified reachable 2026-09-15 | Reference only | This is the canonical repo name. `sickn33/antigravity-awesome-skills`, used in earlier drafts of this project, is a stale name — GitHub confirms the repo was renamed; that URL now redirects here. Use `agentic-awesome-skills` everywhere in this repo. |

### Especially relevant files

- Matt — [to-spec](https://github.com/mattpocock/skills/blob/main/skills/engineering/to-spec/SKILL.md), [to-tickets](https://github.com/mattpocock/skills/blob/main/skills/engineering/to-tickets/SKILL.md) — both require explicit invocation; do not call automatically. Exact paths confirmed 2026-09-15.
- Superpowers — [writing-plans](https://github.com/obra/superpowers/blob/main/skills/writing-plans/SKILL.md) — receives commercial context, produces the technical plan in its own format. Exact path confirmed 2026-09-15.
- gstack — [office-hours](https://github.com/garrytan/gstack/blob/main/office-hours/SKILL.md), [qa-only](https://github.com/garrytan/gstack/blob/main/qa-only/SKILL.md) (report only, no fixes), [ship](https://github.com/garrytan/gstack/blob/main/ship/SKILL.md) (commits + push + PR; production deploy is separate). Exact paths confirmed 2026-09-15.
- [SaaS MVP Launcher](https://github.com/sickn33/agentic-awesome-skills/blob/main/skills/saas-mvp-launcher/SKILL.md) — exact path confirmed 2026-09-15 under the canonical repo name.

## Documents provided by the user

- ~~[YC Startup Library](https://startup-library.ycombinator.com)~~ — **dead link (NXDOMAIN), confirmed 2026-09-15.** This subdomain no longer resolves; do not cite it. Use YC Library below instead.
- [YC Library](https://www.ycombinator.com/library) — verified reachable 2026-09-15.
- [AO Network — GTM Launch Checklist](https://aonetwork.com/templates/gtm-launch-checklist-template) — verified reachable 2026-09-15; content confirmed to match (60-item, 8-section B2B SaaS GTM checklist).
- [Code & Tell — SaaS Launch Checklist](https://codeandtell.com/blog/saas-launch-checklist) — verified reachable 2026-09-15; content confirmed to match (47-item SaaS launch checklist).
- [Sell Successfully — B2B SaaS GTM Checklist](https://sellsuccessfully.io/blog/go-to-market-checklist-saas-launch/) — **not verified.** Fetch attempts on 2026-09-15 timed out (looks like anti-bot blocking, not a confirmed 404) — treat as unconfirmed, neither dead nor validated, until someone checks it in a real browser.

The briefing that seeded this project also mentions *The Mom Test*, general interview practice, and the Superhuman product-market-fit case as relevant reading. **Full texts of those were not provided and have not been read** — do not present them elsewhere in this repo as sources that were actually consulted.

## Gbrain YC corpus (local research tool, not a runtime dependency)

- Executable used: `/Users/user01/.bun/bin/gbrain`
- Source: `default`
- Inventory at time of research: 420 pages — 394 transcripts, 26 notes (user had estimated ~397 transcripts)
- **16 representative transcripts were read**, not the full corpus. Treat any claim sourced from gbrain as based on that sample, not exhaustive coverage.
- Useful commands: `gbrain sources list`, `gbrain list`, `gbrain search`, `gbrain get` (consult installed `--help` for filters — flags may have changed since this was written).
- gbrain is an **optional, during-use** research aid. It is never a requirement to install or run any founder-skills skill, and its corpus is not distributed with this repository (see CONTRIBUTING.md).

### Transcripts consulted

| Theme | Sources |
|---|---|
| Ideas and interviews | [How to Get and Test Startup Ideas](https://www.youtube.com/watch?v=vDXkpJw16os), [How To Talk To Users](https://www.youtube.com/watch?v=z1iF1c8w5Lg) |
| MVP and launch | [How To Build An MVP](https://www.youtube.com/watch?v=qRZ_l7CVzZU), [The Best Way To Launch Your Startup](https://www.youtube.com/watch?v=u36A-YTXiow) |
| First customers and sales | [First 10 Customers](https://www.youtube.com/watch?v=_FBivfgOvuE), [Enterprise Sales](https://www.youtube.com/watch?v=0fKYVl12VTA), [Sales Playbook For Founders](https://www.youtube.com/watch?v=DH7REvnQ1y4) |
| Pricing and models | [How To Price For B2B](https://www.youtube.com/watch?v=4hjiRmgmHiU), [Startup Business Models and Pricing](https://www.youtube.com/watch?v=oWZbWzAyHAE) |
| Retention and PMF | [How To Keep Your Users](https://www.youtube.com/watch?v=VNxBZ7ka5J0), [The Real Product Market Fit](https://www.youtube.com/watch?v=FBOLk9s9Ci4), [Peter Reinhardt / Segment](https://www.youtube.com/watch?v=l-vfn97QTr0) |
| Bootstrap and scale | [Bootstrap or Raise Venture Capital?](https://www.youtube.com/watch?v=D81y-kh11oI), [Building A $2 Billion SaaS Company](https://www.youtube.com/watch?v=rjyJsbUunQ4) |
| Pivots | [Favorite Pivot Stories](https://www.youtube.com/watch?v=DmehFuCMtvc), [From Pivot Hell To $1.4 Billion Unicorn](https://www.youtube.com/watch?v=5WN8bfG06Hk) |

## Format, attribution, packaging

- [Agent Skills — specification](https://agentskills.io/specification) — verified reachable 2026-09-15, content confirmed to match (frontmatter and packaging rules).
- [Skills CLI — install](https://www.skills.sh/docs/cli) — verified reachable 2026-09-15, content confirmed to match (`npx skills add` docs).
- [Marketing-for-Founders — license](https://github.com/EdoStra/Marketing-for-Founders/blob/main/LICENSE.md) (CC BY-SA) — content downloaded and confirmed CC BY-SA 4.0 on 2026-09-15.

## Implementation-time additions

Add a row here whenever a skill (Task 3–6) or an eval (Task 7) is written using a specific external source not already listed above, including the commit/date it was consulted at.

| Skill / eval | Source consulted | Commit / date | Note |
|---|---|---|---|
| _pending_ | | | |
