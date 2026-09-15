# Out of scope for v1

Recorded per `docs/PLAN.md` §12. These are deliberate exclusions, not oversights — if you're tempted to add one of these while implementing a skill, don't; note the temptation here instead and move on.

- **A promise of US$1M ARR, or a fundraising playbook.** US$1M ARR is a guiding reference point used throughout the library's framing; it is never presented as guaranteed, and this library does not cover raising capital.
- **A skills marketplace, web dashboard, or SaaS product built around this library.** This is a skill library, not a product.
- **Automatic installation of Matt Pocock Skills, Superpowers, or gstack.** founder-skills detects and integrates with them when present; it never installs, updates, or modifies them.
- **Distribution of YC transcripts or full CC BY-SA templates.** Sources are synthesized, not redistributed — see `CONTRIBUTING.md`.
- **B2C, marketplace, hardware, or any non-SaaS business as the primary focus.** The library is B2B SaaS-first for v1.
- **Conventions, CI, or scaffolding copied from swe-factory or any other sibling repo.** This project is independent by design (`docs/PLAN.md` §1).
- **Reading the full Matt Pocock Skills / Superpowers / gstack catalogs as a v1 prerequisite.** Only the specific connection points in `docs/PLAN.md` §4 were researched and are relied upon; the rest of those catalogs may or may not be compatible and wasn't assumed to be.
- **A dedicated landing-page / website-conversion skill.** Reviewing [Marketing-for-Founders](https://github.com/EdoStra/Marketing-for-Founders)'s "Landing Pages, Messaging and Positioning," "Pricing," and "Conversion Rate Optimization" sections surfaced a real gap: none of the 14 skills owns turning an already-decided offer and price into an actual persuasive page (homepage copy, CTA, social proof/case studies, pricing-page layout) and iterating on its visitor→signup conversion rate. `founder-positioning` deliberately stops at the offer sentence; `founder-pricing` sets the number and packaging, not the page. This is a real capability gap, not an oversight — it's excluded from v1 to keep the 14-skill catalog in `docs/PLAN.md` §3 closed as planned. Candidate for a v2 skill (working name `founder-landing-page`) if this becomes a recurring need.
