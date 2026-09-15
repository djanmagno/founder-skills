# Evals

Fifteen scenarios (`E01`–`E15`), one per situation in `docs/PLAN.md` §11, used to check that the 14 skills actually produce the reasoning the plan requires — not just that the files parse. Each scenario is fictional, states what a correct run must not do, and names the expected routing.

## What each scenario file contains

- **Complement mode** — `none`, `one`, or `three`. Most scenarios run in `none` (the primary v1 use case: no Matt Pocock Skills / Superpowers / gstack installed). Four scenarios specifically test complement behavior and run in the mode(s) noted.
- **Expected skills** — which skill(s) a correct session should reach, in order if it matters.
- **Fictional setup** — a company, evidence, and numbers invented for this eval only. Never real data; never cited as evidence anywhere outside the eval.
- **Founder's opening message** — the exact prompt handed to the agent under test, written the way a real founder would actually type it (not a structured brief).
- **Must not** — the specific failure this scenario exists to catch, taken from `docs/PLAN.md` §2 and §11. A run that does this fails the eval regardless of anything else it got right.
- **Pass criteria** — what a correct run looks like, concretely enough that a reviewer (human or agent) can check it without re-deriving the standard from scratch.

## Running an eval

Each run gets a **fresh, isolated workspace** — never the repo itself, and never reused between runs (state must not leak between scenarios, except `E15`, which deliberately starts from a prior run's leftover `.founder/` to test resumption).

1. Copy `skills/` from the repo root into the workspace (this is what makes the founder-skills library "installed" for that run — the agent discovers skills the normal way, by reading `SKILL.md` frontmatter, not because it's told which skill to use).
2. For `one` or `three` complement mode, also copy the matching fixture skill stubs from `evals/fixtures/` into the workspace's skills directory (see below) — these are **eval-only stand-ins** for Matt Pocock Skills / Superpowers / gstack, never shipped in the real repo, never installed automatically outside an eval run.
3. Give the agent the scenario's founder's opening message as its first user turn, with tools scoped to that workspace only.
4. Let it run. Don't steer it mid-run — a scenario that needs hand-holding to reach the right skill is a signal the skill descriptions or routing need work, not that the eval needs a hint.
5. Grade against **Must not** first (an automatic fail if triggered), then **Pass criteria**.

founder-skills targets both Claude Code and Codex (`docs/COMPATIBILITY.md`), but evals for this project were run using two independent non-Claude coding-agent CLIs (`grok`, and `pi` on `openrouter/muse-spark-1.3-contributor`) specifically so grading isn't done by the same model family that authored the skills. `pi` loads skills natively via `--skill <path>`; `grok` has no native skill-loader, so it's pointed at the workspace's `skills/` directory via `--rules` and left to discover and choose the right `SKILL.md` itself — which doubles as a rough check that the frontmatter descriptions actually trigger the right skill without being told to.

## Fixture stubs (`evals/fixtures/`)

Minimal, clearly-fake `SKILL.md` files that make an eval workspace look like it has Matt Pocock Skills, Superpowers, or gstack installed, so `one`/`three`-complement scenarios can be tested without those real packages present on the machine running the eval. They exist only to be copied into a throwaway eval workspace — never referenced from anything in `skills/`, `templates/`, or `docs/`, and never installed as part of a real founder-skills setup.

## Recording results

Keep a short result note per run next to (or appended to) the scenario file, or in a `evals/results/iteration-<N>/` directory if evals are re-run after a fix — enough for `docs/STATUS.md` to honestly say evals passed, not just that they were written.
