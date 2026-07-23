# Show HN Post

## Title

Show HN: aicage – contain AI coding agents in Docker

## URL

https://github.com/aicage/aicage

## Body

AI coding agents need "yolo" mode to be useful – they have to run tests, install dependencies, edit files freely. But yolo on your host means the agent can read anything, install/uninstall OS packages, and the LLM behind it sees everything on your machine.

I've seen agents forget to use the local venv and install packages at OS level without asking. Took me going through logs to figure out what they broke.

I wrote aicage to contain agents in Docker containers instead. The agent can freely modify your project without freely modifying your machine.

Install:

  pipx install aicage

Run your favorite agent:

  aicage claude
  aicage codex
  aicage gemini
  and many more

You get a TUI setup screen for extensions, Docker args, and additional shares. Press OK and a container starts with your project mounted, the agent installed, and a full dev toolchain. You work with the agent like normal – it reads your code, runs tests, makes edits. But it only sees what you mount or explicitly share.

There's also the privacy angle: code or files you don't want the agent or LLM to read. Running in a container with only the project mounted gives you much tighter control over what's visible, while still letting the agent do its job.

This isn't perfect security. If you enable Docker socket access so the agent can use Docker, that lowers the boundary – but it's opt-in, not default. For the common case of an agent being careless rather than intentionally trying to get at more of your system, this is a big improvement over running it directly on your host.

What makes it actually comfortable instead of a constant fight with Docker:

- Container uses your UID/GID and username, so file permissions just work. No chown, no permission errors.
- Updated agent images are usually available within about 15 minutes of an agent release. Old images get cleaned up automatically.
- Your existing agent config (API keys, preferences) is mounted in. No re-setup.
- Extensions can add tools on top of any agent image. Custom agents and base images supported.

The hard part isn't docker run – it's keeping agent images updated, mapping users correctly, preserving configs, handling extensions, and making it feel like running the agent directly.

What you keep: same source code files, same git diff in your IDE, same workflow. What you lose: the agent's ability to casually mess with your system.

Built-in agents: Claude, Codex, Gemini, Copilot, Goose, OpenCode, Qwen Code, and more.

No telemetry. Rootless Docker support. Works on Linux and Windows. Built-in remote images are signature-verified before pull.

https://github.com/aicage/aicage

---

## Tips

- Reply to comments, especially critical ones
- If someone points out a real limitation, agree and explain your tradeoff
- Don't oversell the security angle – be honest about what Docker can and can't do
