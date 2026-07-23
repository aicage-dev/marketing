# Reddit post for r/programming

## Title

AI coding agents have root-level access to your machine. I built a tool to fix that.

## Body

AI coding agents (Claude Code, Codex, Gemini CLI, Copilot, etc.) need deep access to work – they read your code, run shells, install packages, edit files. Their built-in safety is limited:

- Allow/deny lists only cover known patterns
- Some agents require relaxing safety modes to function
- "Read-only project" features are software rules, not hard boundaries

I built [aicage](https://github.com/aicage/aicage) to solve this. It runs agents inside Docker containers with only your project and agent config mounted.

```bash
pipx install aicage
aicage claude
```

**What it does:**

- Runs 10 AI coding agents in Docker containers
- TUI setup screen for agent selection, base images, extensions, Docker args
- Per-project config, automatic UID/GID matching
- Custom agents, extensions, and base images
- Image signature verification, no telemetry

**Technical details:**

- Containers create a hard boundary: agent accesses only what you explicitly mount
- Supports rootless Docker
- 96% unit test coverage
- Extension system for adding tools and host mounts
- Works on Linux, macOS, Windows (WSL)

The key insight: existing agent safety is software-based. Containers give you an OS-level boundary without changing the agent experience.

GitHub: https://github.com/aicage/aicage
