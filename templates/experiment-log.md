# Experiment log

Lives at `.founder/experiments.md` (or one file per experiment under `.founder/experiments/`, if the founder's workspace is large enough to want that — either is fine, pick one and stay consistent). Every commercial experiment run through any founder-skills skill gets an entry here, so `founder-review` and future sessions can resume the thread instead of re-litigating it.

A pivot does not delete or rewrite a prior entry — it adds a new one and marks the old one superseded, with the evidence that changed the founder's mind. History stays intact.

```markdown
## <short experiment name> — <date started>

**Status:** running / concluded / superseded (if superseded, by which entry and why)

**Hypothesis:** the specific, falsifiable thing being tested. Not "improve activation" — "founders who complete setup within 10 minutes of signup convert to paid at a higher rate than those who don't."

**Action:** what was actually done. Be specific enough that "did we do this" isn't ambiguous later.

**Owner:** who's driving it — matters once more than one person touches `.founder/`.

**Cost:** money and/or time spent, even if the estimate is rough.

**Metric:** the number this experiment lives or dies by, and how it's measured.

**Observation window:** how long before the metric is read as a result — don't leave this open-ended.

**Evidence:** what was actually observed by the end of the window. If the window hasn't closed yet, say so — don't fill this in early.

**Decision:** what happens next given the evidence — continue, stop, change approach, escalate to a pivot. Tie this explicitly to the evidence above, not to how the experiment "felt."
```

## Notes for whoever is filling this in

- An experiment that produced shipped code but no commercial read yet is **not concluded** — leave it running until the commercial metric is actually observed. Technical delivery and commercial validation are different events; see `docs/PLAN.md` §2.
- If a metric is genuinely unknown, write "unknown" in Evidence — never estimate a number to make the entry look complete.
