# Reddit post for r/LocalLLaMA

## Title

aicage - run local AI coding agents (Ollama-compatible, Claude, Codex, etc.) in Docker containers

## Body

I built [aicage](https://github.com/aicage/aicage) to run AI coding agents inside Docker containers. If you're running local models and using coding agents, this might be relevant:

**The problem:** AI coding agents need deep access to your machine. They run shells, install packages, edit files. Even with local models, the agent framework itself has broad host access.

**The solution:** aicage wraps agents in Docker containers. You mount only your project directory and agent config. The agent can't touch anything else on your host.

```bash
pipx install aicage
aicage opencode    # or goose, qwen, or any of 10 built-in agents
```

**Relevant for local setups:**

- Supports OpenCode, Goose, Qwen Code – agents commonly used with local models
- Custom agent support – add your own agent definitions
- Docker socket passthrough option if your agent needs to interact with containers
- Network configurable – you can isolate agent network access
- No telemetry, runs entirely locally

**Extensible:**

- Custom base images (add CUDA, specific Python versions, etc.)
- Extensions for additional tools and host mounts
- Custom agent definitions for any CLI-based agent

The setup is a TUI screen where you pick agent, base image, extensions, and Docker args. Per-project config is saved automatically.

GitHub: https://github.com/aicage/aicage
