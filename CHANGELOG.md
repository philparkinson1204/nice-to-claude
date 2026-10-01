# Changelog

## 1.1.0

- `/nice-to-claude share`: four share cards (Summary, Milestone, Streak and Receipt) to download as PNGs or copy, with captions and post links for X, Bluesky, Threads and LinkedIn, plus a one-page summary to print or save as a PDF. Everything is drawn in your browser from a local file, with nothing loaded from the internet.
- `/nice-to-claude` works as typed. It was a command, which Claude Code only runs by its full name (`/nice-to-claude:nice-to-claude`). It's now a skill, which also answers to the short name.
- The command's settings block is valid YAML now, so stricter checkers (like the plugin directory's) can read it.
- Milestone messages now point to `/nice-to-claude share`.
- Fun facts read right with very small numbers ("your one nice word", "~1 token").

## 1.0.0

First release.

- `/nice-to-claude`: a dashboard with your please/thanks split, a bar for each month, all-time / 30-day / 7-day stats, charts of how and when you're polite, a hall of fame and a random fun fact.
- `/nice-to-claude audit`: every recent match, and why it did or didn't count.
- Statusline counter: all-time totals, this chat's count, a 7-day sparkline, your daily streak and polite messages in a row.
- Milestone messages at please #100, #500, #1,000 and so on.
- Context-aware counting: quotes, code, UI copy, drafted or pasted messages, talking about the word and resends don't count. Typos like `pelase` do.
- Private by design: runs locally, makes no network requests, and the cache holds counts only.
