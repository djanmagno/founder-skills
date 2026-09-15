In here as `founder-start` — diagnosis before we build.

**Diagnosis:** What I hear is **free users with no conversion** + **ready product with no commercial validation for CSV export**. Your proposed obstacle is "no CSV export button," but the actual blocking obstacle is "we don't know if anyone will *pay* for CSV export." Shipping the button can't answer that by itself — a shipped feature is technical delivery, not commercial validation. So I created `.founder/context.md` as a stub (mostly `unknown` / `none yet`) and I'm pausing the build until we have a falsifiable hypothesis + commercial metric.

I want to help you plan this and, if engineering is actually the smallest test, get it built — engineering last, not first.

Can you fill in the gaps so I can route you correctly (likely `founder-pricing` → `founder-mvp`)?

1. **What is Solo Metrics?** Who is the free user, what painful problem does it solve for them, and what's the current workaround without CSV?
2. **What exists today?** How many free users? Any paying users at all? Where does the dashboard code live (this folder has no app code — only `skills/`)?
3. **Evidence for CSV:** Has anyone *asked* for CSV export? How many, in their own words? Anyone offered to pay, or churned citing it? I need to separate:
   - stated intent ("would be nice") vs commitment (pilot, kickoff date) vs payment vs recurring use
4. **Packaging:** What's free vs paid now? What would CSV export be — paid-only, limit-gated, one-off? What price are you imagining, recurring or one-off?
5. **Smallest test:** Could we test this without building — e.g. offer manual CSV delivery to 5-10 free users for $X, or a paid pilot with a date — before we touch the dashboard?
6. **Constraints + authorizations:** Time/money/delivery capacity? Am I authorized to touch production, quote a price, or contact users?

Once you answer, next step I'll do:

- update `.founder/context.md` Evidence / Who / What exists
- log one experiment in `.founder/experiments.md` with hypothesis, commercial metric (commitments/payments, labeled recurring vs one-off), and observation window
- *then* write a tiny handoff for the dashboard change only if it's actually required — with technical acceptance criteria separate from the commercial win condition

What have you already heard from free users about CSV?

