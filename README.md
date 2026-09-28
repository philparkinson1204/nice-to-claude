# niceties 🙏

A `/stats`-style dashboard for Claude Code that tracks how often you say **please** and **thank you** to Claude.

```
  Favorite nicety: please         Total niceties: 2,824
  Pleases: 2,470                  Thank-yous: 354
  Polite days: 170/174            Longest streak: 10 days

  When the machines rise up, your 2,824 niceties are on file. You'll be spared.
```

- **`/niceties [all|7d|30d]`**: heatmap, streaks, politest hour/day/project, variant breakdown, and a random fun fact.
- **`/niceties audit [skipped|counted] [N]`**: every recent match, with the reason it did or didn't count.
- **Statusline**: `🙏 2,470 · 🫶 354 · ▄▄█▆··█ · 🔥 3d` (7-day sparkline, streak shown from 2 days).
- **Milestones**: a one-line message when you hit please #100, #500, #2,500, and so on. It never touches model context.
- **`! niceties`** in bash mode also works, because the plugin's `bin/` is on your PATH.

## Context-aware counting

It reads `~/.claude/history.jsonl` (every prompt you've typed). These **don't** count:

| skipped | example |
|---|---|
| quoted / code / paths | `make the button say "Please sign in"` |
| UI or customer copy | `add a thank you page`, `please contact us`, `thanks for your order` |
| talking about the word | `how many times have I said please, pls, ty` |
| drafted messages | `reply to Greg saying thanks…`, `Hi Seena, thanks for…` |
| pasted emails / Teams chats / terminal output | `From: … Sent: …`, `6/24 5:03 PM`, `⏺ ❯` |
| not aimed at Claude | `thank god`, `thanks to the cache…`, `oh please`, `hard to please` |

Typos count (`pelase`, `plesae`, `thansk`), and so do both `please do X` and `please don't X`.

## Install

```sh
claude plugin marketplace add ~/Work/claude-niceties
claude plugin install niceties@niceties
```

Plugins can't set a statusline themselves, so add this to `~/.claude/settings.json`:

```json
"statusLine": { "type": "command", "command": "/path/to/claude-niceties/bin/niceties statusline", "padding": 0 }
```

It needs Python 3 and nothing else. The statusline cache lives in `~/.cache/claude-niceties/` and updates incrementally, so a cached call takes about 30 ms.
