---
name: nice-to-claude
description: "How polite are you to Claude? Your please & thank-you dashboard (or: share, audit [skipped|counted])"
argument-hint: "[share | audit [skipped|counted]]"
allowed-tools: Bash(python3:*)
model: haiku
disable-model-invocation: true
---

!`python3 "${CLAUDE_PLUGIN_ROOT}/bin/nice-to-claude" $ARGUMENTS --md`

Reply with ONLY the markdown above, copied exactly: every line, emoji, table row and code fence unchanged. Do not wrap it in another code block, and add nothing before or after it.
