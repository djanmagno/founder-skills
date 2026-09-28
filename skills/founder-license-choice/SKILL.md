---
name: founder-license-choice
description: Help a founder choose the product license by what outsiders may actually do — nothing, a bounded trial, a paid run, or public reuse — and name the skill that writes that file. Use when they ask "what license should this have," "MIT or closed," "can people clone this," or "source-available or open source." Do not use it to decide whether the founder owns the code (founder-ship-clearance), to draft the closed file (founder-closed-license), or to draft terms, privacy, and an evaluation grant (founder-launch-papers).
---

## What this skill does

Picks one license posture and writes down what that posture allows a stranger to do. It does not paste a license. The next skill writes the file. A phrase like "source-available" is not a posture.

## When to use it / when not to

Use it when the license type is unset or the current file and the public site disagree. Do not use it after `.founder/license-choice.md` already records a posture the founder still accepts — go to the writing skill named there. Do not use it to price the product or to announce it.

## Minimum required context

What the founder wants a stranger to be able to do with the code. Whether anyone besides the founder will install it, and whether that install is free or paid. Whether the repository is private or public. Whether a copy already left under another license. `.founder/ship-clearance.md` when the founder has a paid role or equity in another company. The third-party notice list if one exists.

## Procedure

1. **Ownership first if someone else may already own the code.** If `founder-ship-clearance` is missing and a paid role or equity grant exists, run that skill before naming a copyright line. A posture can still be chosen as intent. A grant waits until clearance is **clear**. **Consent** or **blocked** means no file goes out that gives outsiders rights.

2. **Four postures, picked by the act the founder is willing to allow.** Ask only until one fits. Do not offer a fifth.

   | Posture | A stranger may | A stranger may not | Next skill |
   |---|---|---|---|
   | Closed | Nothing, until a later written license | Use, copy, clone, modify, any purpose | `founder-closed-license` |
   | Evaluation | Install, for a named look, on their machines, for a fixed time | Redistribute, production, resale, keeping it after the time | `founder-launch-papers` |
   | Commercial | Run what they paid for, under a written grant | The source, unless that grant says so | `founder-launch-papers` after a price exists (`founder-pricing` if it does not) |
   | Open | Use, copy, modify, and fork, under a named family | Whatever that family's conditions still require | Adopt that family's standard text. Do not paraphrase it. |

3. **Say the consequence before they lock it.** Closed on a public repository still lets the clone command succeed; the license makes use an infringement, it does not hide the bytes. Open means a competitor may run and republish the code within the family's rules. Evaluation and commercial are grants: the file must give the install, then limit it. A ban that mentions only production or commercial use leaves copy and private use allowed. Do not call that closed.

4. **"Source-available" is not a choice.** If they want people to read and not use, the posture is closed, and the repository stays private if the goal is that strangers cannot download it. If they want people to read and reuse, the posture is open. Write the rejected phrase in the note so a later edit does not put it back.

5. **Open is a family, not a custom essay.** Permissive (the usual short licenses that allow reuse with attribution, and sometimes a patent grant) leaves the founder's own later license free. Copyleft can require the combined work to stay under that family when the founder ships a binary, or when users reach a modified service, depending on the family. If a notice list contains copyleft or an unknown license, the open choice stops until someone reads those texts. Do not pick a specific license identifier from memory. Name the family. The founder, or a lawyer, picks the identifier. Put that project's own license text in the file unchanged.

6. **A later change does not rewind.** Copies taken under an open or evaluation grant keep that grant. Moving the file to closed affects later distributions. Record whether any copy is known to have left.

7. **Third-party code keeps its license under every posture.** The choice governs the founder's code. It does not rewrite `THIRD_PARTY_NOTICES`.

## Deliverables

`.founder/license-choice.md`:

```markdown
# License choice

Last updated: <date>
Posture: closed | evaluation | commercial | open
What a stranger may do:
What a stranger may not do:
Repository visibility: private | public | unknown
Copies already out under another license: none known | listed
Clearance: clear | consent | blocked | not required
Family, if open: permissive | copyleft | stopped on a third-party license
Rejected: <the other postures, one line each, including "source-available" if they said it>
Next skill: <name>
```

Add the posture under `.founder/context.md` **Existing docs** as a link to that note. Do not set publishing to yes.

## Judging results / routing the next action

Success: the founder can point at one row of the table and accept what a stranger may do. Failure: two postures at once, or a file that says closed while the site offers an evaluation.

Route:
- Closed → `founder-closed-license`.
- Evaluation, or commercial with a price → `founder-launch-papers`.
- Commercial and no price → `founder-pricing`, then `founder-launch-papers`.
- Open, family named, notices clean → put that family's standard text in the license file. Do not send them through `founder-closed-license`.
- Open, copyleft or unknown in the notices → stop. Read those licenses before the file changes.
- Clearance is consent or blocked → do not write a grant. The intent can sit in the note.

## Working with no complements installed

Decide from the founder's answers and the files already in the project. No license scanner and no plugin are required to pick the posture. A scanner, if they have one, only helps the notice check in the open row.

## Complement integration

None. Do not install a license tool.
