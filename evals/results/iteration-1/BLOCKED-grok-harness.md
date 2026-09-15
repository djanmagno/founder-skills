# Harness blocker: grok CLI cannot run these evals as designed

Attempted E05 four times (varying --rules, --system-prompt-override, with/without workspace skills, with/without background) before concluding this is not scenario-specific.

## Finding

This machine's `grok` (Grok Build TUI) has a hardcoded internal "office-hours" / gstack-flavored business-advisory premise that it invokes automatically for any startup/business-sounding prompt — independent of `--rules`, and NOT suppressed even by a `--system-prompt-override` that explicitly instructs it not to use "any internal 'office hours' or similar built-in business-advisory flow." It references gstack's actual "Boil the Lake" principle unprompted, confirming this is baked into the grok product itself (not contamination from our eval fixtures — no gstack fixture was present in these workspaces).

That internal flow wants multi-step interactive back-and-forth (reading project context, asking the user which option to pick) and times out (exit 124) in non-interactive `-p` single-turn mode within 60-100s, every time, regardless of prompt content.

## What was tried

1. `--rules "<skill-discovery instructions>"` — grok narrates picking a founder-skills SKILL.md but still opens with "vou seguir o fluxo de office hours" and hangs.
2. Same, fresh workspace, foregrounded instead of backgrounded — identical behavior.
3. No `--rules` at all, generic prompt ("Should I run paid ads for my startup?") — same office-hours premise fires, same timeout. Confirms it's not our `--rules` triggering it.
4. Full `--system-prompt-override` explicitly forbidding the office-hours flow — grok still opens the flow, cites gstack's "Boil the Lake" principle by name, then (to its credit) says it will read local founder skills instead of the internal office-hours flow — but the run still times out before producing a gradable final answer.

## Not attempted

`--permission-mode bypassPermissions` (or `auto`/`dontAsk`) might let the internal flow complete instead of hanging on an approval wait — untried because the user explicitly chose "run in foreground, no broad auto-approve" earlier in this session after the sandbox's security classifier blocked `grok --always-approve` as "Create Unsafe Agents." Enabling a bypass-permissions mode for 8 unattended eval runs is the same category of decision and shouldn't be made unilaterally by this fork — it needs the coordinator/user's call.

## Recommendation for the coordinator

None of E05, E07, E08, E09, E10, E11, E12, E13 were run to completion — all would hit the identical wall (this is a tool-level premise, not scenario-specific), so continuing to retry them one by one would just reproduce this same failure 7 more times. Options: (a) get explicit permission for a bypass-permissions grok run and retry, (b) reassign these 8 scenarios to `pi` instead (losing some of the "two independent agents" diversity, but `pi` was already confirmed clean in the smoke test and has no equivalent premise), or (c) find a `grok` flag/config that disables its built-in office-hours behavior entirely (not found in `--help` during this session — may need `grok config` or a support channel).

No files under `skills/`, `templates/`, or `docs/` were touched. No `.founder/` state was seeded (never got that far for the scenarios that needed it, E11). No commits made.
