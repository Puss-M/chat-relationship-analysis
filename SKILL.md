---
name: chat-relationship-analysis
description: Analyze exported one-to-one chat files and produce an evidence-based relationship assessment grounded in message excerpts, fixed labels, a five-part scorecard, Sternberg's triangular theory, and social exchange theory. Use when the user asks to judge what a chat relationship looks like, whether warmth is romantic or platonic, whether there is escalation, or whether the interaction is becoming one-sided. Best for `reports/chat_*.txt` and compatible with merged monthly transcripts from `wechat-backup`.
---

# Chat Relationship Analysis

## Overview

Use this skill to assess a single relationship from exported chat files without drifting into generic dating advice. The output should stay anchored to the file, separate friendliness from romantic progression, and surface imbalance risk with restrained language.

Read [references/framework.md](references/framework.md) when you need the label definitions, scorecard anchors, theory mapping, or output template.

## Supported Inputs

Prefer these input forms:

- `reports/chat_<name>.txt`
- a chronologically merged transcript assembled from `wechat-backup/<contact>/*.md`

If the user points at monthly backup files instead of a merged transcript, merge them in time order before analyzing. Do not analyze a fragmented month in isolation unless the user explicitly asks for a partial read.

## Workflow

1. Confirm the input is a single-contact chat transcript, not a group chat.
2. Skim the transcript to understand time span, density, and who tends to initiate.
3. Extract repeated evidence clusters rather than over-weighting one vivid line:
   - initiative and follow-up
   - emotional disclosure and support
   - praise and admiration
   - invitations and real-world progression
   - exclusivity or romantic framing
   - task/resource exchange
   - boundary-setting or distancing language
4. Score the five fixed dimensions from the reference file.
5. Assign exactly one main label and up to two modifiers.
6. Map the evidence into:
   - Sternberg: intimacy, passion, commitment
   - Social exchange: reciprocity, asymmetry, extraction risk
7. Write the short result first, then the full report.

## Core Rules

- Base every non-trivial conclusion on message evidence.
- Distinguish `warmth`, `admiration`, and `trust` from `romantic escalation`.
- If the file supports ambiguity, say so directly instead of forcing a decisive romantic verdict.
- Prefer repeated patterns over isolated statements.
- Avoid manipulative advice, certainty claims, and armchair diagnosis.

## Output Contract

Always return both layers:

### Layer 1

- one-sentence verdict
- one main label
- one-line risk note when needed

### Layer 2

Use this fixed section order:

1. `速判`
2. `关系标签`
3. `理论映射`
4. `评分卡`
5. `证据摘录`
6. `建议动作`

Keep the language concrete and low-drama. The report should help the user judge the relationship more clearly, not intensify it theatrically.

## Evidence Handling

For each important conclusion, include:

- timestamp
- speaker
- short quote or tight paraphrase
- why that line matters

If evidence conflicts, report the conflict and lower confidence. Do not flatten contradictory signals into a fake-clean story.

## When To Be Conservative

Default to a conservative interpretation when:

- the transcript shows high trust but weak real-world progression
- admiration is strong but exclusivity is absent
- support is warm but clearly framed as friendship, collaboration, or learning
- the user appears to be doing more emotional labor or practical labor than the other side

In those cases, a label like `学习搭子`, `高信任朋友`, or `单向情绪承接` is usually safer than `模糊暧昧` or `明显推进`.

## Examples Of Good Use

- "Use $chat-relationship-analysis to judge whether this exported chat is romance, friendship, or mostly learning-partner energy."
- "Use $chat-relationship-analysis on `reports/chat_24杜呦呦.txt` and tell me the main label, the evidence, and whether the exchange is becoming one-sided."
- "Use $chat-relationship-analysis on these merged monthly transcripts and tell me whether the warmth is actually progressing or just high-trust friendship."
