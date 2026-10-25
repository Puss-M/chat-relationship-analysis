# Chat Relationship Analysis

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

A Codex / agent skill that reads an exported one-to-one chat transcript and produces an **evidence-based relationship assessment** — no generic dating advice, no vibing off a single vivid line.

## What it does

Given a single-contact chat file (`reports/chat_<name>.txt` or a merged transcript from `wechat-backup`), the skill:

1. Extracts **repeated evidence clusters** — initiative & follow-up, emotional disclosure, invitations, real-world progression, exclusivity framing, task exchange, distancing language
2. Scores five fixed dimensions into a scorecard (anchors defined in [`references/framework.md`](references/framework.md))
3. Assigns exactly one **main label** plus up to two modifiers
4. Maps the evidence onto theory:
   - **Sternberg's triangular theory** — intimacy / passion / commitment
   - **Social exchange theory** — reciprocity, asymmetry, extraction risk
5. Outputs a short verdict first, then the full report with quoted excerpts for every claim

Key design constraints: friendliness is not romantic escalation, one-sided effort is surfaced explicitly, and every conclusion must trace back to lines in the file.

## Install

```bash
# Codex CLI
git clone https://github.com/Puss-M/chat-relationship-analysis ~/.codex/skills/chat-relationship-analysis
```

Claude Code / other markdown-driven agents: copy `SKILL.md` into your skills or instructions directory. An `agents/openai.yaml` descriptor is included for clients that load interface metadata.

## Use

```
Use $chat-relationship-analysis to analyze reports/chat_*.txt
```

## License

[MIT](LICENSE)
