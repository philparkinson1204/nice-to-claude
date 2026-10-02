# Privacy policy

nice-to-claude is a Claude Code plugin that counts the pleases and thank-yous you type to Claude. It runs entirely on your own computer. The developer runs no server and never receives, collects or stores any of your data.

## What it reads

- **Your Claude Code prompt history:** `~/.claude/history.jsonl`, or `$CLAUDE_CONFIG_DIR/history.jsonl` if you've set that. The plugin reads it on your machine to find pleases and thank-yous. Your prompts can contain personal information, but the plugin only counts words in them.
- **Each prompt as you send it:** its one hook (`UserPromptSubmit`) checks whether that prompt hit a milestone, such as please #100. It never blocks or changes your prompt.

## What it stores

Everything it stores stays on your machine, in `~/.cache/nice-to-claude/`:

- **Counts only:** your totals, a count per day, and a count per recent chat.
- **A fingerprint of each chat's latest message:** a one-way SHA-256 hash and its length, used to recognize a message you stopped and sent again. The text itself is never stored.
- **The share page:** `share.html`, with your numbers in it. It has no prompt text and no project names.
- **A statusline launcher:** `statusline.sh`, a two-line script that runs the plugin's own statusline.

Nothing expires on its own. Delete `~/.cache/nice-to-claude/` to remove it all. Uninstalling the plugin doesn't touch your history file.

## What leaves your machine

The plugin makes no network requests of its own. Data leaves your machine only in these cases:

- **When you post a card:** the share page's post links open X, Bluesky, Threads or LinkedIn only when you click one, and send that site the caption you see (your totals and a link to this plugin) as a draft. That site's own privacy policy then applies.
- **When you run `/nice-to-claude`:** like any slash command, its output goes through a quick reply from Claude (Haiku). That's the dashboard's numbers and your politest project's folder name, or for `/nice-to-claude audit`, short snippets of your past prompts. Anthropic's privacy policy applies to that, as it does to everything else you send to Claude.

## Children

nice-to-claude is not directed at children under 18.

## Contact

Questions or concerns: open an issue at https://github.com/philparkinson1204/nice-to-claude/issues

## Changes

Any change to this policy will be made in this file, and its history is public in the repository.
