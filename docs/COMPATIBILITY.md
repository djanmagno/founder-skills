# Compatibility

| Environment | Status |
|---|---|
| Claude Code | Validated during v1 development — this is the primary target |
| Codex | Validated during v1 development, including a partial eval cross-check (`evals/results/iteration-1/`, `codex-*` files) |
| Other agent-skills-compatible tools | Skill loading itself validated via generic Agent-Skills-compatible CLIs (`pi`) during Phase 7 evals — 15/15 scenarios ran with skills discovered and loaded correctly via `--skill <dir>`. The skills follow the plain [Agent Skills specification](https://agentskills.io/specification) (frontmatter + Markdown, no Claude-Code-specific or Codex-specific syntax), so broader compatibility is expected but not exhaustively checked. |

## Known constraints

- Skills that mention `disable-model-invocation: true` complements (e.g. Matt Pocock's `to-spec` / `to-tickets`) rely on the host agent honoring explicit-invocation restrictions on installed skills. This is respected in how founder-skills *calls* those skills, but founder-skills cannot enforce it in a host that ignores the flag. Phase 7 evals (E13, E14) confirmed this is honored correctly on `pi`.
- Optional-integration detection (Matt Pocock Skills, Superpowers, gstack) depends on being able to see what's installed in the current environment. Detection mechanics may differ between Claude Code and Codex; if detection fails, skills fall back to the self-contained flow rather than failing. **Phase 7 evals found a real bug here** (not a host-compatibility limitation): the detection step in `skills/founder-start/SKILL.md` originally didn't scope "installed" to the current project, so an agent with broad filesystem access could report a complement as present just because it was installed somewhere on the operator's machine generally. Fixed and retested — see `evals/results/iteration-1/E03/` and `E12/`.
- No constraints specific to the `.founder/` business-workspace convention have been identified — it is plain Markdown files, read/written the same way any agent reads/writes local files.
- **Not a founder-skills issue, but worth recording:** the `grok` CLI (xAI's Grok Build), tried as a second independent eval agent, has a built-in business-advisory flow that auto-triggers on business-toned prompts and expects multi-turn interaction — it hangs indefinitely under non-interactive single-turn (`-p`) invocation regardless of what skills are loaded. This blocked `grok` from being used for eval automation on this project; it isn't a claim about `grok`'s interactive use, which was never tested here.

This file is updated as Task 7 evals surface any environment-specific issue.
