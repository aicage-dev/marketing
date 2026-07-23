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

There's also the privacy angle: some projects I'm legally not allowed to share with LLMs in certain countries. Running the agent in a container with only the project mounted gives me at least some control over what the LLM can access, while still letting the agent do its job.

This isn't perfect security. Sharing the Docker socket lowers the boundary. But the risk is never higher than running the agent directly on your host, and for casual use (agent accidentally reading things it shouldn't, installing stuff where it shouldn't) it's much lower. The agent would have to actively try to break out, not just be careless.

What makes it actually comfortable instead of a constant fight with Docker:

- Container uses your UID/GID and username, so file permissions just work. No chown, no permission errors.
- Agent updates land within 15 minutes of release. Old images get cleaned up automatically.
- Your existing agent config (API keys, preferences) is mounted in. No re-setup.
- Extensions can add tools on top of any agent image. Custom agents and base images supported.

What you keep: same source code files, same git diff in your IDE, same workflow. What you lose: the agent's ability to casually mess with your system.

Built-in agents: Claude, Codex, Gemini, Copilot, Goose, OpenCode, Qwen Code, and more.

No telemetry. Image signatures verified. Works on Linux, Windows (WSL). macOS is experimental (I don't have the hardware).

https://github.com/aicage/aicage

---

## Tips

- Reply to comments, especially critical ones
- If someone points out a real limitation, agree and explain your tradeoff
- Don't oversell the security angle – be honest about what Docker can and can't do
