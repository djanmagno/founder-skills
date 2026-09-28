---
name: founder-ship-clearance
description: Decide whether a founder can license a product to outsiders before launch, by reading the agreements they already signed — employment, contractor, equity, equipment — and comparing the product's job to the job those agreements pay for. Use when a founder is about to send a build, open a repo, or put their own name on a copyright line, or asks "does my employer own this," "can I ship a side project," or "do I need permission." Do not use it to draft the license, terms, or privacy notice (founder-launch-papers), to announce the product (founder-launch), or to sell the first accounts (founder-first-customers).
---

## What this skill does

Stops a launch that gives other people a copy, a login, or a license until the founder can say who owns the product and who has already forbidden outside work. It reads the agreements on disk. It writes a clearance note the next skills can obey. It does not sign, send, or declare ownership.

## When to use it / when not to

Use it when software, a paid pilot, or an evaluation build is about to leave the founder's machines. Use it when the founder is employed, contracting, or holds equity in a company that is not the product. Do not use it for an idea that has not been built and will not be shown. Do not use it to negotiate a customer contract. Do not use it as a substitute for a lawyer's opinion — the note records what the papers say and what is still unknown.

## Minimum required context

The product in one sentence: whose job it completes. The founder's current paid role in one sentence, if any. The actual agreements, not a recollection: employment or services contract, any equity or option grant (often a different company from the employer), equipment or acceptable-use terms, and any confidentiality paper the employment contract names. If a named paper is missing, the clearance stays open. `.founder/context.md` if it exists.

## Procedure

1. **Name the licensor the launch would use.** A natural person, or a company that already exists on a registry document. A brand, a domain, and a planned company are not a licensor. If the copyright line and the footer name differ, write both down. Do not invent a registration number.

2. **List every agreement that can move rights, and the party on the other side.** An employment contract with a local subsidiary does not cancel an equity agreement with a parent. A clause that says "this is the whole agreement" binds the parties named in that file. Read the prevailing language version when the file is bilingual.

3. **Extract only the clauses that change whether outsiders may receive the product.** For each file, record the clause id and a short paraphrase:
   - Assignment: during working hours, related to the paid duties, or everything created in the term. Note whether pay is said to cover the assignment.
   - Exclusivity: any other job or any service to any other organization, paid or not, and whether prior written consent is required. Note the consequence (repayment, discipline, dismissal).
   - Non-compete: during the job and after, how long, which activity, which customers. Note a second non-compete in an equity agreement, including forfeiture of unvested awards.
   - Confidentiality: customer names, prices, plans, internal tools. The product must not carry these.
   - Equipment: company machines are for the paid job.
   - What the file incorporates by name and is not in the folder. Missing paper stays missing.

4. **Compare jobs, not vibes.** Write the paid job's deliverable (what a customer of that employer receives) and the product's deliverable (what a user of the product receives). A shared technique — agents, reviews, documents — does not make the products the same. Record the reading that the product is outside the paid deliverable, and the reading that it is close because the employer is already exploring that technique. Do not pick a winner when the duty list is missing or the product sits next to an internal tool. Duty lists from an old role are not the current role.

5. **Facts the papers do not contain.** Hours, which machine, whether employer material entered the repo, whether anyone outside already received a build. Mark each unknown. Do not tell the founder to delete history to improve the story.

6. **Write the clearance.** One status:
   - **Clear** — the papers that exist do not assign this product and do not forbid this offer, and the duty comparison is unambiguous.
   - **Consent** — a named party must sign before anyone outside receives the product. A letter to the employer does not bind a different company on an equity agreement. Do not send the letter in this skill. List the facts a lawyer should add before anyone sends it.
   - **Blocked** — the product is the paid deliverable, or it contains the employer's confidential material. Shipping is not a paperwork problem.

7. **Statute numbers stay out unless the official text was opened in this session.** Describe the rule (employee software, post-employment non-compete, future-work assignment) and mark the article unchecked. The contract's own clause ids are enough to act.

## Deliverables

`.founder/ship-clearance.md` in the business workspace:

```markdown
# Ship clearance

Last updated: <date>
Licensor the launch would name: <person or existing company>
Product deliverable: <one sentence>
Paid-job deliverable: <one sentence or "no current paid role">
Status: clear | consent | blocked

## Agreements read
- <file, date, other party, clause ids that matter>

## Missing papers
- <named in a contract and not found, or "none">

## Job comparison
- Outside the paid deliverable because:
- Close to the paid job because:
- Decision left open:

## Unknown facts
- Hours / machine / employer material / already shared:

## Before anyone outside receives a build
- <consent from which parties, or "none">
- Letter: not sent

## What this note is not
A lawyer's opinion. Jurisdiction and enforceability are unchecked unless a source is cited from text opened in this session.
```

Update `.founder/context.md` **Authorizations**: publishing and production stay as they were. Add one line, "Outsiders may receive the product," set from the status above. Do not flip publishing to yes because the product is built.

## Judging results / routing the next action

Success: a status that names the papers and refuses to license what those papers may already have assigned. Failure: a copyright line with no file behind it, or a consent email sent during this skill.

Route:
- Status is clear, and the launch will hand someone a build or collect their data → `founder-launch-papers`.
- Status is consent or blocked → stop. The announcement skill does not run.
- No agreements and no paid role → `founder-launch-papers` still has to name a real licensor.
- The product's job is still unclear → `founder-product-audit`, then return here.

## Working with no complements installed

Read the PDFs and notes the founder points at. Paraphrase clauses. Do not install a legal plugin. Do not copy the agreements into the skill repo or into a public issue.

## Complement integration

None. Contract review tools, if the founder already has them, may help extract clause ids. This skill still writes `.founder/ship-clearance.md` and still does not send mail.
