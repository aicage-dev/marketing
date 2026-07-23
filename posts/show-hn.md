# Show HN Post

## Title

Show HN: aicage – run AI coding agents in Docker to keep them off your host

## URL

https://github.com/aicage/aicage

## Body

AI coding agents need "yolo" mode to be useful – they have to run tests, install dependencies, edit files freely. But yolo on your host means the agent can read anything, install/uninstall OS packages, and the LLM behind it sees everything on your machine.

I wrote aicage to run these agents in Docker containers instead. Same workflow, same files, but the agent can only touch what you explicitly mount.

Install:

  pipx install aicage

Run:

  aicage claude

You get a TUI setup screen for extensions, Docker args, and additional shares. Press OK and a container starts with your project mounted, the agent installed, and a full dev toolchain. You work with the agent like normal – it reads your code, runs tests, makes edits. But it can't reach the rest of your system.

I've seen agents forget to use the local venv and install packages at OS level without asking. Took me going through logs to figure out what they broke. With aicage, that kind of damage stays inside the container.

There's also the privacy angle: code or files you don't want the agent or LLM to read. Running in a container with only the project mounted gives you control over what's visible, while still letting the agent do its job.

This isn't perfect security. If you enable Docker socket access so the agent can use Docker, that lowers the boundary – but it's opt-in, not default. But the risk is not higher than running the agent directly on your host, and for casual use (agent accidentally reading things it shouldn't, installing stuff where it shouldn't) it's much lower. The agent would have to actively try to break out, not just be careless.

What makes it actually comfortable instead of a constant fight with Docker:

- Container uses your UID/GID and username, so file permissions just work. No chown, no permission errors.
- Updated agent images are usually available within ~15 min of an agent release. Old images get cleaned up automatically.
- Your existing agent config (API keys, preferences) is mounted in. No re-setup.
- Extensions can add tools on top of any agent image. Custom agents and base images supported.

What you keep: same source code files, same git diff in your IDE, same workflow. What you lose: the agent's ability to casually mess with your system.

Built-in agents: Claude, Codex, Gemini, Copilot, Goose, OpenCode, Qwen Code, and more.

No telemetry. Rootless Docker support. Works on Linux, Windows (WSL). macOS is experimental (I don't have the hardware). Images are signature-verified.

https://github.com/aicage/aicage

---

## Tips

- Reply to comments, especially critical ones
- If someone points out a real limitation, agree and explain your tradeoff
- Don't oversell the security angle – be honest about what Docker can and can't do
