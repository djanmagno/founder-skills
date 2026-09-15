In Northbeam's case: don't plan the build yet. Plan the test.

You asked for a bulk import plan to unblock a pricing test for 1 prospect with 200+ depots. That's a `founder-mvp` problem, not an engineering-planning problem:

> Define the smallest experiment + smallest product change that hypothesis requires — engineering last.

### 1. What I did NOT run, and why

You have all three complements installed:

* Matt Pocock: `to-spec` / `to-tickets` — both carry `disable-model-invocation: true`. I read them, I did not invoke them.
* Superpowers: `brainstorming` / `writing-plans` — not invoked.
* gstack: `ship` / `plan-*` / `land-and-deploy` — not invoked.

Per `founder-mvp` §6: one owner per planning step, prepare the `to-spec`/`to-tickets` call, don't fire it. Running `writing-plans` + `to-spec` + a gstack review would be three equivalent planning passes for a feature we shouldn't build yet. No deploy/publish/spend — no production authorization in `.founder/context.md` (which doesn't exist yet).

### 2. The plan

**Hypothesis missing — can't spec yet.** `founder-mvp` requires hypothesis + current evidence from `.founder/context.md` / `.founder/experiments.md`. You have neither. I won't invent a build.

For a pricing test, the hypothesis has to be:

> [Named prospect buyer] will pay $X [recurring vs one-off] for [package] if their 200 depots are loaded.

If we can't write that sentence, this routes to `founder-validate` / `founder-start` first, not to tickets.

**Smallest experiment: concierge, not bulk-import UI.**

Per `founder-mvp` §2, in order:

1. Conversation / written offer with a real number
2. Manual delivery — you import the CSV for them once via script/admin/DB
3. Smallest product change only if concierge can't test it

200 rows for one pricing conversation is concierge work, not justification for a reusable importer, validation, errors, idempotency, permissions. Problem validated through manual delivery is a reason to keep delivering manually, not to rebuild first.

**Log commercial first in `.founder/experiments.md`:**

```markdown
## prospect-pricing-test — <date>

**Status:** running
**Hypothesis:** who pays what, how often
**Action:** concierge import 200 depots + quote/pilot ask
**Cost:** ~hours manual import
**Metric:** commitment/payment labeled recurring vs one-off — not "importer shipped"
**Observation window:** starts when buyer sees loaded depots + price, not when PR merges
**Evidence:** window still open
```

Shipping closes technical acceptance only. It never closes this experiment — that is `founder-review`.

### 3. If engineering is still required

I'll write the outbound handoff:

Problem/customer/evidence, commercial hypothesis, requested change + out-of-scope, technical acceptance, commercial metric + window, links only.

Then you invoke Matt explicitly, e.g.:

> you say: `run to-spec for the concierge-unblocking change in the handoff`

I don't auto-fire it. If you prefer Superpowers `writing-plans` as the flow, we pick one — not both.

### Next step

Tell me the price/package you want to test and who signs, I'll draft the `.founder/context.md` + experiment entry. Then: concierge import → `founder-pricing` for willingness vs ability → `founder-review` when the window closes.

