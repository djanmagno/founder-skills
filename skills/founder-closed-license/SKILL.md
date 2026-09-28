---
name: founder-closed-license
description: Write an all-rights-reserved license when the founder wants nobody to use, copy, or clone the product without a written grant. Use when they ask "how do I stop people cloning this," "all rights reserved," "don't make it source-available," or the offer is that no outsider may run the code. Do not use it to choose among closed, evaluation, commercial, and open (founder-license-choice), to grant an evaluation or a paid pilot (founder-launch-papers), to decide whether the founder owns the product (founder-ship-clearance), or to announce the product (founder-launch).
---

## What this skill does

Produces a license file that grants nothing, and checks the public sentences around it so the site does not offer a permission the file withholds. A private repository is a separate lock. This skill does not make a public repository unclonable.

## When to use it / when not to

Use it when the product stays on the founder's machines, or when anyone who receives a copy still needs a later written license before they may run it. Do not use it for a cohort, a trial, or a customer who is supposed to install the product — that is `founder-launch-papers`, which has to grant the install. Do not use it to relicense other people's components that shipped inside the product.

## Minimum required context

Who the copyright line may name (`founder-ship-clearance` if a paid role or equity grant exists; otherwise the founder confirms there is no such agreement). Whether any copy already left under a permissive license. The third-party notice list, if a package exists. Where the license text is repeated (site page, footer, FAQ, package metadata).

## Procedure

1. **Say that no permission is granted.** Name the acts in the same sentence: use, copy, clone, fork, modify, merge, publish, distribute, sublicense, sell, and derivative works, for any purpose. Evaluation, internal review, personal use, production, and commercial use all belong in that list. A ban that applies only "in production or for a commercial purpose" leaves copy and private use allowed. The words "source-available" and "for evaluation" are a permission. Do not use them in a closed license.

2. **Access is not a license.** A sentence that someone may read the file, or may see a private repository, does not allow them to run or copy the software. The written license, when it exists, is a different document.

3. **Do not relicense third parties.** Components under their own notice keep that license. The closed file governs the founder's code. If a strong copyleft component is inside a package the founder might someday ship, stop and say so; this skill does not clear that combination.

4. **Do not pretend to revoke a license already given.** Copies taken while a permissive license was the file in force stay under that license. Say that for those copies only. Later distributions follow the closed file. If the repository was private for the whole permissive window and no copy is known to have left, write "no copy known," not "nobody has a copy."

5. **The same sentence everywhere the public can read it.** Footer, FAQ, and the license page repeat the closed position: no license is granted; use, copy, or clone needs a written license. A footer that says "evaluation license" while the file grants nothing is the false offer. Change the generator and the pages it already wrote.

6. **The git host is the other half.** A private repository is what stops a stranger running clone. This license makes an unauthorized copy an infringement; it does not disable the clone command on a public repository. If the code is public, say that plainly and do not tell the founder the license closed the door.

7. **Save the file the project already ships as its license, and a note.** Do not publish a new site from this skill unless the founder has authorized publishing. Editing the license file and the pages that quote it is the work.

## Deliverables

The license file the package and the site already point at, with no grant.

`.founder/closed-license.md`:

```markdown
# Closed license

Last updated: <date>
Copyright line: <name clearance allows>
Grant: none
Acts requiring a later written license: use, copy, clone, fork, modify, distribute, derivative works, any purpose
Access is a license: no
Third-party notices preserved: <yes, or the stop>
Copies already under a permissive license: <none known / listed>
Repository visibility: <private / public>
Public sentences checked: <license page, footer, FAQ>

## What this does not do
Stop a clone of a public repository. Replace a lawyer's view of enforceability.
```

## Judging results / routing the next action

Success: a reader cannot find a permission to use, copy, or clone, and cannot find a public sentence that offers one. Failure: a ban limited to commercial use, the word source-available, or a footer that still announces an evaluation license.

Route:
- The founder actually wants someone to install it → `founder-launch-papers`, and do not leave this closed file in place for that recipient.
- Ownership is still consent or blocked → `founder-ship-clearance` before the copyright line is treated as settled.
- They are ready to tell a bounded audience that the product exists, without handing out the code → `founder-launch`.

## Working with no complements installed

Edit the license and the pages that quote it. No plugin. Write the file in the language the repository already uses for that license; talk to the founder in their language.

## Complement integration

None.
