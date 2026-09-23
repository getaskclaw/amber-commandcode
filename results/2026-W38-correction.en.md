# 2026-W38 correction notice — amber-commandcode: additive correction to published scores

> 中文版:[2026-W38-correction.md](2026-W38-correction.md)

**Summary**: this notice rewrites no past issue; it **appends** one set of adjudicated results. AMBER ran a full-library review of its published 2026-09 scores: some failures previously counted were adjudged a **bench-side** problem rather than a model-capability problem, and for some papers the evidence was incomplete and the conclusion stays open. This notice lists both classes cell by cell — the **reversals** and the **holds** — with the review method and the guardrails that follow. **No balanced books, no board**: papers with incomplete evidence are named and removed from the board, and enter no aggregate. Past issues stay as published; reversals take effect through this notice.

## 1. Scope of this correction

- Count for this repo in this notice: **0 standalone published cells reversed · 14 standalone published cells held** (count = standalone published cells = actual table rows).
- **Scope in one line**: 14 papers of the W37 five-band ladder are held — the 2 high-band matrix cells (A-cdc3d11a / A-ea80d793) plus the five-band case-level tallies (15/15/17/15) may move up; the lane freeze makes a re-exam infeasible for now.
- Horizon: adjudication signed 2026-09-22; this repo's published numbers stop at 2026-09-21, i.e. a **pre-adjudication** snapshot.
- Unchanged: questions, oracles, transcripts and intermediate artifacts are never published; the alias and bundle_sha handles are unchanged.
- Nature of this notice: **additive**. Past conclusions are not withdrawn, deleted or rewritten; reversals take effect through this appendix.

## 2. Reversal table (adjudicated)

None. This repo has no adjudicated cell.

## 3. Hold table (named, undecided)

| Alias | bundle_sha | Issue | Previous | Status | Action |
|---|---|---|---|---|---|
| A-cdc3d11a | `dbb207a3118d` | W37 | full matrix, high band ✗ -2 | held (re-exam pending) | named and removed from the board; no re-exam while the lane is frozen; excluded from all aggregates pending re-exam |
| A-ea80d793 | `1d69841b029e` | W37 | full matrix, high band ✗ -1.0 | held (re-exam pending) | same |
| A-cdc3d11a | `dbb207a3118d` | W37 | five-band ladder, low band (case-level tally) | held (re-exam pending) | same (case-level tally only; no standalone cell) |
| A-47eea242 | `b4b8d4bb44e3` | W37 | five-band ladder, low band (case-level tally) | held (re-exam pending) | same |
| A-ea80d793 | `1d69841b029e` | W37 | five-band ladder, low band (case-level tally) | held (re-exam pending) | same |
| A-cdc3d11a | `dbb207a3118d` | W37 | five-band ladder, medium band (case-level tally) | held (re-exam pending) | same |
| A-47eea242 | `b4b8d4bb44e3` | W37 | five-band ladder, medium band (case-level tally) | held (re-exam pending) | same |
| A-ea80d793 | `1d69841b029e` | W37 | five-band ladder, medium band (case-level tally) | held (re-exam pending) | same |
| A-d9b79b46 | `d6d63130ecc6` | W37 | five-band ladder, medium band (case-level tally) | held (re-exam pending) | same |
| A-cdc3d11a | `dbb207a3118d` | W37 | five-band ladder, none band (case-level tally) | held (re-exam pending) | same |
| A-d9b79b46 | `d6d63130ecc6` | W37 | five-band ladder, none band (case-level tally) | held (re-exam pending) | same |
| A-47eea242 | `b4b8d4bb44e3` | W37 | five-band ladder, xhigh band (case-level tally) | held (re-exam pending) | same |
| A-ea80d793 | `1d69841b029e` | W37 | five-band ladder, xhigh band (case-level tally) | held (re-exam pending) | same |
| A-d9b79b46 | `d6d63130ecc6` | W37 | five-band ladder, xhigh band (case-level tally) | held (re-exam pending) | same |

> The hold table's 14 rows = 14 papers: 2 of them have standalone matrix cells (high band), the other 12 enter the case-level tally only — a re-exam reversal would move the case-level tallies rather than single cells.
> No re-exam while the lane is frozen.

## 4. Method: why we correct, how we checked, how we prevent

**Why we correct.**
These are our published numbers; if they are wrong, we are the ones who fix them. This review
found that some published failures were not the model failing the task, but the bench side —
a pre-scoring step cut off a healthy attempt, and the paper was recorded as a model failure.
Errors run both ways: judging good work as bad, and bad work as good. We checked both.
The point of a correction is not to look better or worse; it is to make the numbers on the
board match what actually happened.

**How we checked.**
Every paper was independently re-verified by multiple seats. Verifiers read the raw record
first-hand (the attempt log, the scorer output, the ledger timestamps, the fix commit) and
accepted no second-hand conclusion. Two independent directions worked in parallel — one
looking for wrongful failures, one looking for what was missed — and only papers where both
agreed went to adjudication; disagreements were held. Each verdict rests on the same evidence
chain and is re-computable paper by paper, with a signed confirmation on file. Outcomes fall
into four classes: exonerated (cause on the bench side; the capability score is withheld),
confirmed (a genuine model-side failure), held (evidence incomplete — **no quiet conviction
and no quiet pardon**), and report-level corrections that leave history untouched.

**How we prevent it.**
Three small things, one line each: ① **Evidence chain** — each paper's raw process is
recorded out of the driver's reach, append-only and sealed at the end; scoring trusts evidence
completeness only. Cause of death is a conclusion, not a fact — it can be recomputed from the
evidence, and when a rule is wrong we fix the rule and recompute; the raw facts never move.
② **Reconciliation gate** — papers in must equal papers out (scored + bench + held; no bucket
missing, no cell extra). **No balanced books, no board** — there is no "publish first, patch
later." ③ **Brain-identity double-check** — an identity assertion per paper, and no assertion
means no score; we also re-check *passed* papers against the reverse error.
No set of controls stops everything (hardware breaks), but it can make a bad verdict live
less than one reconciliation cycle.

**In one line.** What we sell is not a bench that never errs — it is one that cannot walk away
from a wrong call.

## 5. What comes next

- The remaining held papers go through re-exam / final adjudication; a re-exam may record **"undecided", never "brain too weak"** — a re-exam decides only once the environment differences are enumerated to zero, otherwise a reproduction is not an attribution.
- Once the fixes and guardrails land, affected case-level headlines will move with the next regular issue; reversals **do not retroactively rewrite** past issues — the original cell only gets a pointer mark.
- Sister repos are in step via each repo's README results index.

---

## Addendum: triple-exam scores filed (mimo-v2.6-pro / mimo-v2.6-flash, case-level three-value tally)

Same-day CommandCode triple exam; the two mimo legs have finished and are filed on the
**case-level three-value tally** (pass / fail / held). Multi-variant cases (several variants
sharing one bundle) count as **one case**; for repeated runs the final attempt decides.

| Model | Pass | Fail | Held | Case board |
|---|---|---|---|---|
| `xiaomi/mimo-v2.6-pro` | **17** | **6** | **1** | 24 |
| `xiaomi/mimo-v2.6-flash` | **13** | **6** | **5** | 24 |

- **mimo-v2.6-pro 17/6/1**: the single hold is A-d511f9e8 (`invalid_infrastructure`, zero
  deliverable — a case-level bench defect, also invalid on this week's grok-4.7 leg). A-be92627f,
  recorded as "no deliverable", counts as a **genuine attempt not delivered** on *this* lane —
  scored fail, not held.
- **mimo-v2.6-flash 13/6/5**: the 5 holds = 2 bench holds (A-d511f9e8, A-be92627f, both
  `invalid_infrastructure`) + **3 pending-review holds** (A-791e90ac, A-1fd3683a, A-13854d9d —
  terminal `valid_task_failure` with d2 = `no code block`, the same failure across brains, so we
  **do not convict**: neither pass nor fail, named and held for review). The same cases scored on
  the mimo-v2.6-pro leg (6/6, 2/2, 5/5), so the cases are passable; the flash leg's no-code-block
  pattern is logged as a delivery-reliability observation.
- **Same case, different death — recorded per lane**: A-be92627f is "genuine attempt not
  delivered" = fail on the mimo-v2.6-pro leg, and `invalid_infrastructure` = bench hold on the
  mimo-v2.6-flash leg. Each paper is recorded by its own leg's terminal state.
- **Wire note**: both lanes' state.db is single-brain clean (59/88 usage rows, zero foreign
  brains); the external-agent lane is handled under the declared discipline, with no wire audit.
- Every number is computed by script from the manifests (27 runs / 24 cases, both legs complete);
  nothing is hand-filled. By the time this page shipped the mimo-v2.6-flash leg had finished; the
  "running" line in this repo's 2026-W39 issue is kept as the press-time snapshot, and this
  addendum governs.
