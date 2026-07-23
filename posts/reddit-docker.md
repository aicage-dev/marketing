# Reddit post for r/docker

## Title

I built a tool to run AI coding agents in Docker containers for host isolation

## Body

Hey r/docker,

I've been running AI coding agents (Claude Code, Codex, Gemini CLI, etc.) directly on my machine for months. These agents read code, run shells, install packages – and their safety checks are limited. Some even require relaxing safety modes to work properly.

So I built [aicage](https://github.com/aicage/aicage) – it runs these agents inside Docker containers. You mount only what the agent needs, and the rest of your host is unreachable.

**How it works:**

```bash
pipx install aicage
aicage claude    # or codex, gemini, copilot, goose, etc.
```

It starts a container with your project mounted, the agent installed, and a full dev toolchain. There's a TUI setup screen where you pick the agent, base image, extensions, and Docker args.

**What I found interesting from a Docker perspective:**

- Per-project config with automatic UID/GID matching
- Rootless Docker support
- Image signature verification (cosign) before pulling
- Extension system that can add custom base images and host mounts
- Optional Docker socket passthrough for agents that need to build/run containers themselves

**Supported agents:** Claude Code, Codex, GitHub Copilot, Gemini CLI, Goose, OpenCode, Qwen Code, Crush, Factory CLI, Antigravity CLI

Has anyone else been running AI agents in containers? Curious about other approaches.

GitHub: https://github.com/aicage/aicage
