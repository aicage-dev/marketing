# AGENTS.md

This repo contains marketing strategy and post drafts for [aicage](https://github.com/aicage/aicage). All content is markdown. No build, test, or lint tooling.

## Product context

aicage runs AI coding agents (Claude, Codex, Gemini, Copilot, etc.) in Docker containers. The author is a developer with 30+ years experience who built this to solve his own problem: agents in yolo mode reading things they shouldn't and installing packages at OS level.

Sibling repos at `../aicage/`, `../aicage.wiki/`, etc. contain the actual product. Read from those when you need product facts.

## Writing rules

- Write from the author's real experience, not from feature lists. The author will reject AI-slop instantly.
- No Twitter/X. The owner will not use that platform.
- Be honest about limitations. Don't oversell security - aicage contains agents, it doesn't sandbox them perfectly.
- macOS support is experimental only (author has no hardware).
- The agent is passed as CLI arg (`aicage claude`), not picked from a menu.
- The TUI configures extensions, Docker args, and shares - not agent selection.
- `details_about_aicage.md` is the author's private notes, not for publication.

## Commits

- Branch: `development`
- Style: short imperative messages, e.g. "Fix Show HN post: reorder features"
- The author edits files directly and expects agents to review his changes, not overwrite them.
