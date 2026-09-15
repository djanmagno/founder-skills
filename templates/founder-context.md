# Founder context

Lives at `.founder/context.md` in the business workspace by default (reuse the user's existing convention instead, if one already exists — see `docs/PLAN.md` §6). Create this file the first time a skill needs somewhere to persist business context; don't create it speculatively.

Keep every section honest about what's actually known. "Unknown" or "not yet validated" is a valid, expected value — never fill a gap with an invented interview, customer, or number to make the file look complete.

```markdown
# Founder context

Last updated: <date>

## Goal

What the founder is trying to achieve, in their own words.

## Who

- User: who uses the product day to day.
- Buyer: who decides / pays, if different from the user.
- Problem: the problem being solved, as currently understood — mark as hypothesis until there's interview or usage evidence.

## What exists

One of: idea only / manual or concierge service / partial prototype / shipped product with no commercial validation / shipped product with paying customers. Note the evidence for this classification, not just the label.

## Evidence

List what's actually been observed, tagged by type:
- Stated intent (someone said they'd want this)
- Commitment (someone agreed to a next step — a call, a trial, a LOI)
- Payment (money changed hands)
- Recurring use (they came back and used it again)

Don't upgrade a lower tier to a higher one without the evidence for it — a signup is not a commitment, a trial is not a payment.

## Constraints

Time, money, skills, and delivery capacity the founder is actually working with.

## Authorizations

What the founder has explicitly authorized: outbound contact to prospects, publishing/launch actions, spend limits, production deploys. Skills must respect current authorization here rather than assuming consent.

## Existing docs, tools, processes

Links only — do not copy technical documents into this file. If the founder already has a documentation convention (a wiki, a `docs/` folder with its own layout, a project management tool), point to it here instead of introducing a competing structure.

## Complements detected

Which of Matt Pocock Skills / Superpowers / gstack are installed, and the flow the founder has chosen to use for technical work (if any). Re-check only when something material changes or conflicts — don't re-ask every session.
```
