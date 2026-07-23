# Twitter/X thread

## Tweet 1 (hook)

AI coding agents have root-level access to your machine.

Claude, Codex, Gemini, Copilot – they all read your code, run shells, install packages. Their safety checks are limited.

I built a tool to fix this. 🧵

## Tweet 2 (solution)

aicage runs AI coding agents inside Docker containers.

You mount only what the agent needs. The rest of your host is unreachable.

```bash
pipx install aicage
aicage claude
```

## Tweet 3 (what it supports)

10 built-in agents:

- Claude Code
- Codex CLI
- GitHub Copilot
- Gemini CLI
- Goose
- OpenCode
- Qwen Code
- Crush
- Factory CLI
- Antigravity CLI

One tool, any agent.

## Tweet 4 (how it works)

How it works:

1. `aicage claude` starts a Docker container
2. Your project directory is mounted in
3. Agent config (API keys, preferences) is mounted in
4. A full dev toolchain is pre-installed
5. The agent runs – but can only see what you mounted

## Tweet 5 (security details)

Security features:

- No telemetry, no user data collection
- Image signature verification (cosign) before pull
- Rootless Docker support
- Per-project config with automatic UID/GID matching
- Optional Docker socket passthrough (opt-in only)

## Tweet 6 (extensibility)

Extensible:

- Custom base images (add CUDA, specific tools, etc.)
- Extensions for additional packages and host mounts
- Custom agent definitions for any CLI-based agent
- Your existing agent config is mounted automatically

## Tweet 7 (CTA)

Try it:

```
pipx install aicage
aicage <agent>
```

GitHub: github.com/aicage/aicage

If you've been running AI agents directly on your host, this is worth a look.

---

## Tips for posting

- Post thread as a single thread (use Twitter's thread feature)
- Add a screenshot of the TUI between tweets 2 and 3
- GIF of `aicage claude` starting up is gold for engagement
- Reply to replies quickly in the first hour
- Pin tweet 1 to your profile
