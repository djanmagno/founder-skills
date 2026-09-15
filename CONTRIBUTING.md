# Contributing

Thanks for considering a contribution to founder-skills. This document exists mainly to keep two things straight: what license original content in this repo carries, and how it relates to the third-party sources the library was researched from.

## Original content vs. sources

Everything under `skills/`, `templates/`, and `docs/` in this repository is **original synthesis** — written for this project, in our own words, from our own reasoning about the founder situations we're covering. It is licensed MIT (see `LICENSE`).

That does not mean the content appeared from nowhere. It was informed by primary sources listed in `docs/SOURCES.md`, including:

- [Matt Pocock Skills](https://github.com/mattpocock/skills), [Superpowers](https://github.com/obra/superpowers), and [gstack](https://github.com/garrytan/gstack), for the optional-integration connection points.
- [Marketing-for-Founders](https://github.com/EdoStra/Marketing-for-Founders), licensed **CC BY-SA**, for customer research, channels, launch, and positioning framing.
- YC Startup Library / YC Library content, and a set of YC-adjacent video transcripts consulted via a local research tool (see `docs/SOURCES.md` for the list and its limits — a representative sample was read, not the full corpus).
- A handful of public GTM/launch checklists (AO Network, Code & Tell, Sell Successfully).

## Rules for any contribution

1. **Do not copy transcripts, full checklists, or CC BY-SA templates into this repo's MIT content.** Summarize and synthesize instead. If a specific phrase or structure is distinctive enough that copying it would raise attribution concerns, don't use it — write the idea in your own words.
2. **CC BY-SA and MIT do not mix silently.** If a contribution leans on Marketing-for-Founders (or another CC BY-SA source) closely enough that it isn't a clean synthesis, say so explicitly in the PR description and flag it for a licensing decision before merge. Don't default to "it's probably fine."
3. **Record what you consulted.** Add or update the relevant row in `docs/SOURCES.md`, including the commit SHA or URL you read, and note if you only sampled part of a larger corpus (as we did with the YC transcripts).
4. **Every skill installs standalone.** If your change to a skill adds a required file, that file lives inside `skills/<name>/`, not only at the repo root. Root-level `templates/` are for human reference and cross-skill consistency, not a runtime dependency.
5. **Keep this project independent.** Do not import conventions, tracking files, or architecture from unrelated repos (this project has explicitly chosen not to reuse a sibling repo's process — see `docs/PLAN.md` §1). If you're integrating with Matt Pocock Skills, Superpowers, or gstack, that goes through the connection points in `docs/PLAN.md` §4 and the guides in `docs/integration/`, never as an automatic install/update of those packages.
6. **English for skills and docs, the user's language for interaction.** SKILL.md files and everything under `docs/` are written in English. Only the agent's live conversation with a founder, and the materials it generates for them, follow the founder's language.

## Evidence discipline

If your contribution touches how the agent reasons about a founder's business (any of the 14 skills, or `founder-start`'s routing), re-read `docs/PLAN.md` §2 and §10 before writing. The short version: don't invent interviews, customers, or metrics; don't treat a shipped feature or a signup count as proven demand; don't recommend more acquisition as the default answer to churn. These aren't style preferences — they're acceptance criteria checked by the evals in `evals/`.
