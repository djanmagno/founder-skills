# Handoff (founder-skills ↔ complement)

Used whenever a founder-skills skill hands technical work to Matt Pocock Skills, Superpowers, or gstack, and again when that work comes back. Plain Markdown, no special tooling required. See `docs/PLAN.md` §5 for the contract this implements, and `docs/examples/handoff.md` for a complete worked example.

Where this lives is up to the founder's workspace convention — often a short-lived note in `.founder/`, sometimes just pasted into the chat when the complement is invoked interactively. It does not need to be committed to this repository.

## Outbound (founder-skills → complement)

```markdown
## Handoff: <short title> — <date>

**Problem, customer, evidence:** what's actually known, from `.founder/context.md` — not invented for this handoff.

**Commercial hypothesis and expected result:** what this technical work is meant to test or achieve commercially.

**Requested change, scope, constraints:** what to build/fix/investigate, and what's explicitly out of scope. Current authorization for spend, publishing, or production access, if relevant.

**Technical acceptance criteria:** how the complement (or the founder) will know the technical work is done.

**Commercial metric and observation window:** which experiment-log entry this maps to, and what will actually be read as success or failure once the technical work ships.

**References:** links to existing docs — do not copy them into this handoff.
```

## Inbound (complement → founder-skills)

```markdown
## Handoff result: <short title> — <date>

**Changes made:** what was actually built or changed.

**Verification evidence:** tests run, checks passed — be specific, don't just assert "it works."

**Open items:** anything left undone or deferred, and why.

**Links:** spec, tickets, diffs, tests, deploy/PR links.
```

## What happens after

The inbound handoff goes back to `founder-review`, which records the result in the relevant experiment-log entry and decides the next step. Shipped code closing out the technical acceptance criteria does **not** by itself close the commercial experiment — the commercial metric still has to be observed over its window before the experiment-log entry is marked concluded.
