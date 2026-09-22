# amber-commandcode

Public periodic [AMBER](https://github.com/getaskclaw/amber) benchmark results of models served by CommandCode (api.commandcode.ai). **Cases stay private; results are public.** 中文说明：[README.md](README.md)

## What this is

- A 'lane' is one vendor's shop/API for a model name; a 'case' is one task, a 'run' is one sitting (a multi-variant case has several runs).

- One `results/YYYY-Www.md` per issue: same cases, same harness (the program that runs the exam and scores it), full library per model; same model name across vendors side by side.
- Each issue pins: library size and hashes, per-case defect-hunt score and pass/fail, terminal states (how the run process exited), token usage (when the lane reports it) and latency, environment fingerprint, and a qualitative verdict written under evidence discipline.
- Cases, oracles, transcripts (full answer logs)s and intermediates are **never published**.
- Sister repos: [amber-deepseek](https://github.com/getaskclaw/amber-deepseek) (official DeepSeek lane), [amber-opencode](https://github.com/getaskclaw/amber-opencode) (OpenCode Go lane), [amber-gpt](https://github.com/getaskclaw/amber-gpt), [amber-crof](https://github.com/getaskclaw/amber-crof), [amber-ollama](https://github.com/getaskclaw/amber-ollama), [amber-devin](https://github.com/getaskclaw/amber-devin), [amber-workbuddy](https://github.com/getaskclaw/amber-workbuddy) (WorkBuddy ACP lane), [amber-doubao](https://github.com/getaskclaw/amber-doubao), [amber-goldenpotato](https://github.com/getaskclaw/amber-goldenpotato), [amber-kimi](https://github.com/getaskclaw/amber-kimi), [amber-stepfun](https://github.com/getaskclaw/amber-stepfun). This repo's comparison axis is **same-name cross-vendor duels** — the same model name on CommandCode / OpenCode Go / the official DeepSeek API can be a different endpoint, and every cross-repo citation carries an explicit date and band declaration.

## Publication red lines

1. Publish only: scores and aggregates, token usage (when reported), speed, qualitative verdicts.
2. Never publish: case content, oracles/graders, transcripts, candidate workspaces, anything that could reconstruct a case.
3. Every issue pins: model ID, effort band (the thinking-effort setting), date (UTC), harness version, per-case bundle hash — verifiable against the public hash index in [amber](https://github.com/getaskclaw/amber).
4. Case numbering is private: public matrices use stable aliases (A-xxxxxxxx, hash-derived) plus bundle hashes only.
5. Tone: community measurement, not vendor attacks.

## A methodological premise

Same model name, same provider, two runs can still score differently — inference parameters, load, and server-side versions drift. Relay/aggregator lanes add an upstream routing layer: the same name may not be the same endpoint. Every conclusion here is dated and banded, and we re-test periodically. A single day's number is a snapshot, not a law.

## Results index

| Issue | Content | Headline |
|---|---|---|
| [2026-W37](results/2026-W37.md) | deepseek/deepseek-v4.1-flash full-library debut (23 cases, GA day) | **17/23** (15/21 public subset); full marks on the UI-build paper (fifth repo to publish a pass); 8/9 on the defense case that used to kill everyone; all three same-name lanes verified genuine v4.1; adversarial-review and vision are its weak faces |
| [2026-W38 correction notice](results/2026-W38-correction.en.md) | W38 full-library review: 0 cells reversed · 14 held here; plus the triple-exam mimo legs filed | 14 W37 ladder papers held (2 high-band cells + case-level tallies), no re-exam while the lane is frozen; addendum: mimo-v2.6-pro 17 pass / 6 fail / 1 held, mimo-v2.6-flash 13 pass / 6 fail / 5 held (A-be92627f dies differently per leg — recorded per paper) |

## Disclaimer

Not affiliated with or sponsored by CommandCode or DeepSeek. Scores are dated, band-specific snapshots, not purchasing advice.
