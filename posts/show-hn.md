# Show HN: aicage - Run AI coding agents in Docker for host isolation

## Post title

Show HN: aicage – run AI coding agents in Docker with host isolation

## Post URL

https://github.com/aicage/aicage

## Post body

AI coding agents (Claude, Codex, Gemini, Copilot, etc.) need deep access to your machine – they read code, run shells, install packages. Their built-in safety checks are limited, and some require relaxing safety modes to function fully.

aicage runs these agents inside Docker containers. You mount only what the agent needs. The rest of your host is unreachable.

**Quick start:**

```
pipx install aicage
aicage claude
```

**What it does:**

- Wraps 10 AI coding agents in Docker containers
- Mounts your project directory and agent config into the container
- Provides a TUI setup screen for choosing agents, base images, extensions, and Docker args
- Per-project config saved automatically
- Supports custom agents, extensions, and base images

**Built-in agents:** agy, claude, codex, copilot, crush, droid, gemini, goose, opencode, qwen

**Why containers?**

- Allow/deny lists only cover known patterns – unexpected commands can slip through
- "Read-only project" features are software rules – other files still sit on the same host
- Containers create a hard boundary: the agent accesses only what you explicitly mount

**Key details:**

- No telemetry, no user data collection
- Image signature verification before use
- 96% unit test coverage, integration tests for real Docker runs
- Rootless Docker support
- Works on Linux, macOS, Windows (WSL)
- Extensible: add your own agents, base images, and tool extensions

GitHub: https://github.com/aicage/aicage

---

## Tips for posting

- Post between 9-11am US Eastern, Tue-Thu
- Reply to every comment in the first 2 hours
- Keep responses technical and concise
- If someone finds a bug, thank them and link to the issue tracker
- Don't be defensive about criticism – engage constructively
