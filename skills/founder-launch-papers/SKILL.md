---
name: founder-launch-papers
description: Write the minimum papers a first outsider needs before they receive a build or submit personal data — a license that actually grants the use, terms they accept on purpose, a privacy note for data the founder will really collect, and third-party notices. Use when a founder asks for a LICENSE, terms, a privacy policy, an evaluation cohort, or "what do I need before I send the tarball." Do not use it to decide whether the founder owns the product (founder-ship-clearance), to keep everyone from using or copying the product (founder-closed-license), to announce or pick channels (founder-launch), or to price and close the first paid accounts (founder-pricing, founder-first-customers).
---

## What this skill does

Produces papers that match the launch in front of the founder — a private evaluation, a paid pilot, or a public release — and refuses pages that describe a different launch. The papers are drafts for a lawyer when the founder will rely on them. They are not filed, published, or pasted over a live site inside this skill.

## When to use it / when not to

Use it when `founder-ship-clearance` is **clear**, or when the founder has no employment or equity agreement that could assign the product, and someone is supposed to install or try the product. If clearance is **consent** or **blocked**, stop and say so. If the posture is not chosen yet, use `founder-license-choice` first. If nobody may use or copy the product, use `founder-closed-license` instead of inventing a grant. Do not use it to write a marketing page, a price, or a sales email. Do not use it to open-source a codebase; a later decision to open the code is a new paper, not a sentence in this one.

## Minimum required context

`.founder/ship-clearance.md` when any paid role or equity grant exists. Otherwise a one-line statement that there is no such agreement, which the founder confirms. Who receives the build (named people, or a capped invite list). What they may do with it. What personal data the founder will store, and where. The dependency and vendored-license list if a package is shipped. `.founder/context.md` if it exists.

## Procedure

1. **Match the paper to the offer.** An evaluation build needs a grant of that evaluation, a term, and a stop. A file that only reserves rights does not license the person who installs it. A public open-source grant is a different offer. Do not describe the repo as readable if the code is not public. Do not promise a future license.

2. **One licensor, the one clearance allowed.** Use the name `founder-ship-clearance` recorded. If the site footer, the license, and the company that does not exist yet are three names, pick the one that exists and say the others are not the licensor. Do not invent a company id, address, or officer.

3. **Grant, then limit.** State the grant in ordinary words: who, what they may do, for how long, on which machines, whether they may give it to anyone else. Then the limits that match the product: no resale, no production use if that is the offer, no published benchmark numbers if the cohort is small enough that a number identifies a person. A ban on reading configuration the product invites the user to edit is the wrong limit. A ban on reverse engineering needs a clause that yields where the law requires interoperability. Say if the copy cannot be switched off remotely, if that is true. Acceptance of the license is a deliberate act (a recorded click or a signed note). A privacy checkbox is not that act.

4. **Customer material stays theirs.** Inputs, repos, and outputs written into the customer's project are not the founder's training set and are not assigned by the evaluation. Feedback on the product can be licensed for use in the product; say whether that license survives for feedback already incorporated. Do not take title to feedback.

5. **Liability in words a free cohort can defend.** Exclude lost profits and indirect damages where the applicable law allows, and say willful misconduct and mandatory rules remain. A cap of zero on a free product is an attempt to waive everything. Do not pick a court until the founder and a lawyer choose it from the founder's real location and from whether the recipient is a consumer. Leave the forum blank rather than naming a city that is not in the file.

6. **Privacy only for data this launch stores.** One row per purpose: what is stored, why, the basis the lawyer must confirm, how long, and who deletes it. Publish a retention number only when a person will actually delete on that day. A platform log that stores an address or an identifier counts even if the application table does not. Name processors whose region is known from their contract. Mark the rest unknown. Do not write "we do not collect addresses" if the host's log might. International transfer stays undescribed until those regions are known. Children: if the offer is to adults, say the founder will delete a request that says the person is under the age the lawyer sets, and do not add an age field just to look complete.

7. **Third-party notices travel with the package.** List vendored components and dependencies with the license that was read, not the license the README hopes for. Permissive code keeps its notice. A strong copyleft license in a package the founder ships to users is a stop until a lawyer says the combination is allowed. Unknown license is a stop, not a permissive default. The product license does not relicense those components. Hosted use and a shipped binary are different obligations; name which one this launch is.

8. **The public text may not outrun the software.** If the product sends prompts to the user's own tools, the page says that. If support is "write us when it is on fire" with no response time, the terms say that. Do not copy a security deadline from a document that is not published with the build.

9. **Save drafts in the business workspace, not on the live site.** Record the lawyer's open questions as questions. Do not close them by picking the aggressive option.

## Deliverables

`.founder/launch-papers.md`:

```markdown
# Launch papers

Last updated: <date>
Offer these papers describe: <evaluation / paid pilot / public release>
Licensor: <from ship clearance>
Outsiders may receive the product: <from ship clearance>
Distribution: <shipped files / hosted service>

## License
- Grant:
- Term and how it ends:
- What is not granted:
- How they accept:
- Remote disable exists: <yes or no>

## Terms
- Support:
- Liability sentence:
- Forum: <blank until chosen>
- Customer material:

## Privacy
| Data | Purpose | Basis to confirm | Kept | Who deletes |
| Processors with a known region: |
| Processors still unknown: |

## Third parties
| Component | License read | Notice path |
| Stop for copyleft or unknown: <none or list> |

## Must match the product
- <claim the software actually supports>

## Open for a lawyer
- <questions this draft did not close>

## Not done by this file
Published, emailed, or swapped onto a website.
```

Draft text the founder can hand a lawyer may sit beside that note in the same workspace. It stays marked draft.

Update `.founder/context.md` **Existing docs** with the path. Do not set publishing to yes.

## Judging results / routing the next action

Success: an outsider can see what they are allowed to do, what data is kept, and which components are under other licenses. Failure: a license that forbids the install the founder is about to request, a privacy page for a company that does not exist, or notices that omit vendored code.

Route:
- Papers drafted and clearance is clear → `founder-launch` for the audience, the channel, and the experiment. Launch still does not publish until the founder authorizes publishing.
- Clearance was skipped and a paid role exists → back to `founder-ship-clearance`.
- The offer itself is undecided → `founder-positioning` and `founder-pricing` before inventing a grant.
- Recipients are named accounts the founder will sell one by one → `founder-first-customers` uses these papers; it does not replace them.

## Working with no complements installed

Write the note and the draft from the product and the agreements already read. No legal marketplace, no plugin install. Generate the draft in the founder's language when they will show it to someone; keep this skill's instructions in English.

## Complement integration

If a license scanner is already installed, use it to fill the third-party table and still open the license files that the scanner marks as copyleft or unknown. Do not treat a scan of metadata as a reading of those files.
