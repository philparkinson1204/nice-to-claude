---
description: Politeness stats — how often you've said please & thank you to Claude (all | 7d | 30d | audit)
argument-hint: "[all|7d|30d|audit [skipped|counted]]"
allowed-tools: Bash(python3:*)
model: haiku
disable-model-invocation: true
---

!`python3 "${CLAUDE_PLUGIN_ROOT}/bin/niceties" $ARGUMENTS --plain`

Reply with ONLY the output above, reproduced exactly (every character, space and line) inside a single ```text code block. No intro, no commentary, no summary after it.
