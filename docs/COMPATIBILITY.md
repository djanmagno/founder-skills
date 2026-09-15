# Compatibility

| Environment | Status |
|---|---|
| Claude Code | Validated during v1 development — this is the primary target |
| Codex | Validated during v1 development |
| Other agent-skills-compatible tools | Untested. The skills follow the plain [Agent Skills specification](https://agentskills.io/specification) (frontmatter + Markdown, no Claude-Code-specific or Codex-specific syntax), so they are *expected* to load elsewhere, but that has not been checked. |

## Known constraints

- Skills that mention `disable-model-invocation: true` complements (e.g. Matt Pocock's `to-spec` / `to-tickets`) rely on the host agent honoring explicit-invocation restrictions on installed skills. This is respected in how founder-skills *calls* those skills, but founder-skills cannot enforce it in a host that ignores the flag.
- Optional-integration detection (Matt Pocock Skills, Superpowers, gstack) depends on being able to see what's installed in the current environment. Detection mechanics may differ between Claude Code and Codex; if detection fails, skills fall back to the self-contained flow rather than failing.
- No constraints specific to the `.founder/` business-workspace convention have been identified — it is plain Markdown files, read/written the same way any agent reads/writes local files.

This file is updated as Task 7 evals surface any environment-specific issue.
