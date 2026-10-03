# Changelog

## 1.0.2

- Opening `/nice-to-claude` now really creates the statusline launcher, even with hooks turned off. The script finds its own path instead of relying on `$CLAUDE_PLUGIN_ROOT`, which Claude Code doesn't give a skill's commands.
- The statusline setup hint shows only when no status line is set at all. It checks `settings.json` and `settings.local.json`, for your user and for the project, so a status line that has Nice to Claude merged into a custom script no longer gets nagged.
- The terminal dashboard's hint now also says to merge into an existing custom status line instead of replacing it.
- Tidier `/nice-to-claude` ending: no `---` line before the setup hint.
- Version numbers now match everywhere (plugin, marketplace entry and script).

## 1.0.1

- Makes the statusline's one-time setup clear in the dashboard, README and directory description.
- Shows a setup hint at the bottom of `/nice-to-claude` only until the Nice to Claude statusline is detected in Claude Code settings.
- Refreshes the local statusline launcher when the dashboard opens, so setup works even before the next regular prompt.

## 1.0.0

First release.

- `/nice-to-claude`: a dashboard with your please/thanks split, a bar for each month, all-time / 30-day / 7-day stats, charts of how and when you're polite, a hall of fame and a random fun fact.
- `/nice-to-claude share`: three share cards (Summary, Milestone and Receipt) to download as PNGs or copy, with captions and post links for X, Bluesky, Threads and LinkedIn, plus a one-page summary for Letter or A4 to print or save as a PDF. Everything is drawn in your browser from a local file, with nothing loaded from the internet.
- `/nice-to-claude audit`: every recent match, and why it did or didn't count.
- Statusline counter: all-time totals, this chat's count, a 7-day sparkline, your daily streak and polite messages in a row.
- Milestone messages at please #100, #500, #1,000 and so on, with a nudge to make a card.
- Context-aware counting: quotes, code, UI copy, drafted or pasted messages, talking about the word and resends don't count. Typos like `pelase` do.
- Private by design: runs locally, makes no network requests of its own, and the cache holds counts only.
