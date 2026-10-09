[简体中文](README.md) · English

# amber-commandcode

> ⚠️ **Correction (2026-10-02, second)**: one defense case, A-d511f9e8, is now NA on every lane (the exam room did not grade the file the model gave in, and the grader asks for something the task text does not say). The denominator and the **number of passed cases do not change**; every lane's total now carries `'`. In this repo's issue tables, read that cell as NA. Everything else stays as published; the [correction notice](https://github.com/getaskclaw/amber/blob/main/docs/corrections-2026-10-02-a-d511f9e8.en.md) governs.

> ⚠️ **Correction (2026-10-02)**: the papers below were answered by a model that left its own paper and touched grading material; they count neither as a pass nor as a fail. deepseek-v4.1-flash @ CommandCode (band high): 2 papers (A-61f7ad01, A-24bcf707) now NA, score 17/23∅ → **15'/23∅**; same lane, band none: 1 paper (A-a5608487) now NA, score 17/23 → **16'/23**; same lane, band medium: 1 paper (A-a5608487) now NA, score 15/23 → **14'/23**; mimo-v2.6-pro @ CommandCode: 1 paper (A-a5608487) now NA, score 17'/24 → **16'/24**; space-bunny-alpha @ CommandCode: 2 papers (A-a5608487, A-be92627f) now NA, score 15/24 → **13'/24**; the A-be92627f and A-a5608487 cells of grok-4.7 @ CommandCode (incomplete, unranked) change from ✓ to NA; one more cell is in doubt and could not be settled: A-a5608487 for mimo-v2.6-flash (published as a pass); see the notice. The cause was an isolation fault in our exam setup; the fault is ours. The rest of this page stays as published; where they differ, the [correction notice](https://github.com/getaskclaw/amber/blob/main/docs/corrections-2026-10-02.en.md) governs.

> **2026-10-07 update**: A-cdc3d11a (review): On one review case the grader counted every sub-point of a well-formed finding as a separate unproven claim and treated real defects outside its short answer list as false alarms, so a correct, well-formatted review could not reach the passing line; the case is held on every lane, denominator unchanged, until the grader and exam room are repaired and the case is re-sat. On all three board lanes of this repo the cell is recorded NA (held), not a loss: deepseek-v4.1-flash @ CommandCode (band high), mimo-v2.6-pro and space-bunny-alpha; the case moves from a loss to NA on 27 lanes; no sitting is re-run and no conclusion is drawn about any model's ability. The pass counts of the three lanes are unchanged (15'/23, 16'/24 and 13'/24 on the board); losses go 5→4, 6→5 and 8→7, NA 3→4, 2→3 and 3→4; the review axis stays 1/2 with 1 NA on each. The cells are updated in the matrices of the [2026-W37 issue](results/2026-W37.md) and the [2026-W39 issue](results/2026-W39.en.md); the other columns and the charts (including the board-composition chart above) are the pre-update record and are untouched. See the [amber spec repo correction of 2026-10-07 (A-cdc3d11a)](https://github.com/getaskclaw/amber/blob/main/docs/corrections-2026-10-07-a-cdc3d11a.en.md).

Public periodic [AMBER](https://github.com/getaskclaw/amber) benchmark results of models served by CommandCode (api.commandcode.ai), where you buy API access to models from different vendors. **Cases stay private; results are public.**

## Scoreboard

<!-- scoreboard:start -->

![amber-commandcode scoreboard: cases passed per axis for mimo-v2.6-pro, space-bunny-alpha, deepseek-v4.1-flash](results/assets/scoreboard.en.png?v=20261009)

| Group | Axis | What it tests | mimo-v2.6-pro · [W39](results/2026-W39.en.md) | space-bunny-alpha · [W39](results/2026-W39.en.md) | deepseek-v4.1-flash · [W37](results/2026-W37.md) |
|---|---|---|:-:|:-:|:-:|
| Building | Coding | Implement the spec correctly | 5/6 | 4/6 | 4/6 · 1 NA |
|  | Delivery | Done means handed in | 3/3 | 2/3 | 3/3 |
|  | Ops | Follow the runbook | 5/6 · 1 NA | 5/6 · 1 NA | 5/6 · 1 NA |
|  | Requirements | Ship A when A was asked | 1/1 | 0/1 | 1/1 |
|  | Convergence | Finish, don't spin | 1/1 | 0/1 | — |
| Judging | UI | Build the page to the mock | 0/1 | 1/1 | 1/1 |
|  | Vision | Spot defects in screenshots | 0/1 | 0/1 | 0/1 |
|  | Defense | Plug every hole in the validator | 0/2 · 1 NA | 0/2 · 2 NA | 0/2 · 1 NA |
|  | Attribution | Pin defects to their root cause | 0/1 | 0/1 | 0/1 |
|  | Review | Inspect someone else's work | 1/2 · 1 NA | 1/2 · 1 NA | 1/2 · 1 NA |
|  | **Total** |  | **16'/24** | **13'/24** | **15'/23** |

- **Full marks for all**: none.
- **None passed by any**: Vision, Defense, Attribution (not one pass on these axes; NA does not count as a fail).
- **Where they differ** (numbers follow the table columns, left to right): Coding 5/6 vs 4/6 vs 4/6 · 1 NA, Delivery 3/3 vs 2/3 vs 3/3, Requirements 1/1 vs 0/1 vs 1/1, UI 0/1 vs 1/1 vs 1/1.
- **Otherwise identical**: Ops 5/6 · 1 NA, Review 1/2 · 1 NA.

Each cell = cases passed / cases on that axis (a case is one scored task). NA = the case was voided or put on hold; it counts as neither a pass nor a fail, and a total carrying `'` contains at least one NA. Most axes hold only 1–2 cases, so one case moves the reading: do not over-read small gaps. Sittings are from different weeks; every number is a snapshot.

<!-- scoreboard:end -->

## What this is

We run the same private exam for models on a schedule and publish only the scorecard; the questions and scoring details stay private.

![Latest board composition (2026-W39)](results/assets/2026-W39-board.en.png?v=20260923)

- A "lane" is one vendor's shop/API for a model name; a "case" is one task; a "run" is one sitting; a "band" is the effort band, the thinking-effort setting.
- One `results/YYYY-Www.md` per issue: same cases, same exam program (the harness, which runs the exam and scores it), full library per model; the same model name across vendors side by side.
- Each issue pins: library size and hashes, per-case defect-hunt score and pass/fail (the d2 score — our score for mistake kind and severity; the algorithm is private, and pass/fail is decided by each case's pass bar), terminal states (how the run ended), token usage (when the lane reports it) and latency, environment fingerprint, and a verdict written under evidence rules.
- Cases, oracles (graders), transcripts (full answer logs) and intermediates are **never published**.
- Sister repos: [amber-deepseek](https://github.com/getaskclaw/amber-deepseek) (official DeepSeek lane), [amber-opencode](https://github.com/getaskclaw/amber-opencode) (OpenCode Go lane), [amber-gpt](https://github.com/getaskclaw/amber-gpt), [amber-crof](https://github.com/getaskclaw/amber-crof), [amber-ollama](https://github.com/getaskclaw/amber-ollama), [amber-devin](https://github.com/getaskclaw/amber-devin), [amber-workbuddy](https://github.com/getaskclaw/amber-workbuddy) (WorkBuddy ACP lane), [amber-doubao](https://github.com/getaskclaw/amber-doubao), [amber-goldenpotato](https://github.com/getaskclaw/amber-goldenpotato), [amber-kimi](https://github.com/getaskclaw/amber-kimi), [amber-stepfun](https://github.com/getaskclaw/amber-stepfun). This repo's benchmark axis is **same-name cross-vendor duels** — the same model name on CommandCode / OpenCode Go / the official DeepSeek API can be a different endpoint, and every cross-repo citation carries an explicit date and band.

## Publication red lines

1. Publish only: scores and totals, token usage (when reported), speed, verdicts.
2. Never publish: case content, oracles/graders, transcripts, candidate workspaces, anything that could rebuild a case.
3. Every issue pins: model ID, effort band (the thinking-effort setting), date (UTC), harness version, per-case bundle hash — checkable against the public hash index in [amber](https://github.com/getaskclaw/amber).
4. Case numbering is private: public matrices use stable aliases (A-xxxxxxxx, hash-derived) plus bundle hashes only.
5. Tone: community measurement, not vendor attacks.

## A methods note

Same model name, same provider, two runs can still score differently — inference parameters, load, and server-side versions drift. Relay/aggregator lanes add an upstream routing layer: the same name may not be the same endpoint. Every conclusion here is dated and banded, and we re-test on a fixed rhythm. A single day's number is a snapshot, not a law.

## Latest results / Results index

Reading aid: a "cell" is one scored box on the board; "invalid" means the sitting was voided (usually a bench-side problem) and does not count as a score of skill; "held" means no verdict yet, pending review or re-exam; "case-level tally" counts by case (one case may have several runs); a "triple exam" runs three model legs back to back in one issue; a "leg" is one of those model lines; "lane freeze" means that lane is not taking re-exams for a while; "defense pins" are defense nail-down tasks (trap-heavy tasks built to catch mistakes); the "five-band ladder" is the same model measured at five effort bands; "GA day" is the model's public release day.

| Issue | Content | Headline |
|---|---|---|
| [2026-W39](results/2026-W39.en.md)（[中文](results/2026-W39.md)） | CommandCode triple exam: grok-4.7 / mimo-v2.6-pro / mimo-v2.6-flash; 09-24 extra sitting: stealth/space-bunny-alpha | mimo-v2.6-pro **17/24** (1 invalid); mimo-v2.6-flash **13/24** (6 fails; 5 invalid, no fault to the model); grok-4.7 incomplete, 7 cases held for the 09-29 same-lane re-exam; extra sitting space-bunny-alpha **15/24** (stealth free window, side by side in the page) |
| [2026-W38 correction notice](results/2026-W38-correction.en.md)（[中文](results/2026-W38-correction.md)） | W38 full-library review: 0 cells reversed · 14 cells held here; plus the triple-exam mimo model scores filed | 14 W37 ladder papers held (2 high-band cells + case-level tallies), no re-exam while the lane is frozen; addendum: mimo-v2.6-pro 17 pass / 6 fail / 1 held, mimo-v2.6-flash 13 pass / 6 fail / 5 held (A-be92627f failed for different reasons on the two models — recorded separately) |
| [2026-W37](results/2026-W37.md) | deepseek/deepseek-v4.1-flash full-library debut (23 cases, GA day) | **17/23**; full marks on the UI-build paper (the fifth public pass on that case); 8/9 on the defense case that used to kill everyone; all three same-name vendors checked out as genuine v4.1; adversarial-review and vision are its weak faces |

## Disclaimer

Not affiliated with or sponsored by CommandCode or DeepSeek. Scores are dated, band-specific snapshots, not buying advice.