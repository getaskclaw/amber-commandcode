# amber-commandcode

Public periodic [AMBER](https://github.com/getaskclaw/amber-eval) benchmark results of models served by CommandCode (api.commandcode.ai). **Cases stay private; results are public.** 中文说明:[README.md](README.md)

## What this is

- One `results/YYYY-Www.md` per issue: same cases, same harness, full library per model; same model name across vendors side by side.
- Each issue pins: library size and hashes, per-case d2 score and pass/fail, terminal states, token usage (when the lane reports it) and latency, environment fingerprint, and a qualitative verdict written under evidence discipline.
- Cases, oracles, transcripts and intermediates are **never published**.
- Sister repos: [amber-deepseek](https://github.com/getaskclaw/amber-deepseek) (official DeepSeek lane), [amber-opencode](https://github.com/getaskclaw/amber-opencode) (OpenCode Go lane), [amber-gpt](https://github.com/getaskclaw/amber-gpt), [amber-crof](https://github.com/getaskclaw/amber-crof), [amber-ollama](https://github.com/getaskclaw/amber-ollama), [amber-devin](https://github.com/getaskclaw/amber-devin). This repo's comparison axis is **same-name cross-vendor duels** — the same model name on CommandCode / OpenCode Go / the official DeepSeek API can be a different endpoint, and every cross-repo citation carries an explicit date and band declaration.

## Publication red lines

1. Publish only: scores and aggregates, token usage (when reported), speed, qualitative verdicts.
2. Never publish: case content, oracles/graders, transcripts, candidate workspaces, anything that could reconstruct a case.
3. Every issue pins: model ID, effort band, date (UTC), harness version, per-case bundle hash — verifiable against the public hash index in [amber-eval](https://github.com/getaskclaw/amber-eval).
4. Case numbering is private: public matrices use stable aliases (A-xxxxxxxx, hash-derived) plus bundle hashes only.
5. Tone: community measurement, not vendor attacks.

## A methodological premise

Same model name, same provider, two runs can still score differently — inference parameters, load, and server-side versions drift. Relay/aggregator lanes add an upstream routing layer: the same name may not be the same endpoint. Every conclusion here is dated and banded, and we re-test periodically. A single day's number is a snapshot, not a law.

## Results index

| Issue | Content | Headline |
|---|---|---|
| [2026-W37](results/2026-W37.md) | deepseek/deepseek-v4.1-flash full-library debut (23 cases, GA day) | **17/23** (15/21 public subset); full marks on the UI-build paper (third model ever); 8/9 on the defense case that used to kill everyone; all three same-name lanes verified genuine v4.1; adversarial-review and vision are its weak faces |

## Disclaimer

Not affiliated with or sponsored by CommandCode or DeepSeek. Scores are dated, band-specific snapshots, not purchasing advice.
