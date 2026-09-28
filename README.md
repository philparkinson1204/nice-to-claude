# niceties 🙏

How polite are you to Claude? A tiny Claude Code plugin that counts every **please** and **thank you** you type, with a `/stats`-style dashboard and a statusline counter.

```
🫶 2,362 (▲ +4 please) · 🙏 340 (▲ +4 thanks) · ▃▃▅▄··█ · 🔥 3d
```

## What you get

- **`/niceties`**: a dashboard with a color heatmap, all-time / 30-day / 7-day stats, charts of how and when you're polite, and a random fun fact.
- **Statusline**: all-time totals, this chat's count in parentheses, and a 7-day sparkline.
- **Milestones**: a one-line message when you hit please #100, #500, #1,000 and so on.
- **`/niceties audit`**: every recent match, and why it did or didn't count.

## Install

```sh
git clone https://github.com/<you>/claude-niceties ~/claude-niceties
claude plugin marketplace add ~/claude-niceties
claude plugin install niceties@niceties
```

Restart Claude Code and run `/niceties`. It needs Python 3.8+ and nothing else.

### Statusline (optional)

Plugins can't set the statusline themselves, so add this to `~/.claude/settings.json`:

```json
"statusLine": { "type": "command", "command": "~/claude-niceties/bin/niceties statusline", "padding": 0, "refreshInterval": 10 }
```

`refreshInterval` keeps the totals in sync when you have several Claude Code windows open. Without it, a window only updates when something happens in it. Each refresh takes about 20 ms.

| Part | Meaning |
|---|---|
| `🫶 2,362 (▲ +4 please)` | pleases: all time, then this chat |
| `🙏 340 (▲ +4 thanks)` | thank-yous: all time, then this chat |
| `▃▃▅▄··█` | the last 7 days, today on the right (`·` means none) |
| `🔥 3d` | polite days in a row (shows from 2) |
| `» 3 in a row` | polite messages in a row in this chat (shows from 2) |

## What counts

It reads `~/.claude/history.jsonl`, the prompts you've typed into Claude Code. It counts please, pls, pretty please, thank you, thanks, thx, ty and appreciate it, plus typos like `pelase` and `thansk`.

Niceties that aren't aimed at Claude are skipped:

| Skipped | Example |
|---|---|
| quotes, code and paths | `make the button say "Please sign in"` |
| UI or customer copy | `add a thank you page`, `thanks for your order` |
| talking about the word | `how many times have I said please?` |
| drafted or pasted messages | `reply to Alex saying thanks`, pasted emails and chats |
| not meant for Claude | `thank god`, `thanks to the cache`, `hard to please` |
| resends | a message you stop and send again counts once |

## Privacy

It all runs on your machine: it reads your history file and keeps a small cache in `~/.cache/claude-niceties/`. The only thing that reaches Claude is what `/niceties` shows you, because slash commands display their output through a quick Haiku reply. That's the dashboard's numbers and your politest project's folder name, or for `/niceties audit`, short snippets of your past prompts.

## Other ways to run it

`niceties` is on your PATH while the plugin is enabled:

```sh
! niceties                  # the dashboard, from Claude Code's bash mode
! niceties audit skipped    # what was thrown out, and why
```

To uninstall, run `claude plugin uninstall niceties@niceties` and remove the `statusLine` entry.
