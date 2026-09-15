# Out of scope for v1

Recorded per `docs/PLAN.md` §12. These are deliberate exclusions, not oversights — if you're tempted to add one of these while implementing a skill, don't; note the temptation here instead and move on.

- **A promise of US$1M ARR, or a fundraising playbook.** US$1M ARR is a guiding reference point used throughout the library's framing; it is never presented as guaranteed, and this library does not cover raising capital.
- **A skills marketplace, web dashboard, or SaaS product built around this library.** This is a skill library, not a product.
- **Automatic installation of Matt Pocock Skills, Superpowers, or gstack.** founder-skills detects and integrates with them when present; it never installs, updates, or modifies them.
- **Distribution of YC transcripts or full CC BY-SA templates.** Sources are synthesized, not redistributed — see `CONTRIBUTING.md`.
- **B2C, marketplace, hardware, or any non-SaaS business as the primary focus.** The library is B2B SaaS-first for v1.
- **Conventions, CI, or scaffolding copied from swe-factory or any other sibling repo.** This project is independent by design (`docs/PLAN.md` §1).
- **Reading the full Matt Pocock Skills / Superpowers / gstack catalogs as a v1 prerequisite.** Only the specific connection points in `docs/PLAN.md` §4 were researched and are relied upon; the rest of those catalogs may or may not be compatible and wasn't assumed to be.
