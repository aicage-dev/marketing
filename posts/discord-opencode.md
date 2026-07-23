# Discord post for OpenCode community projects

I just added Linux clipboard support for OpenCode in [aicage](https://github.com/aicage/aicage), which runs coding agents in Docker containers. OpenCode is one of the built-in agents.

For a first start, this is enough:

```bash
pipx install aicage
cd your-project
aicage opencode
```

Then press Enter / OK through the two config screens and OpenCode starts in a container as if it were on the host.

If you want clipboard support, enable the clipboard option on the first config screen. That option only shows up on Linux hosts.

Repo: https://github.com/aicage/aicage

Feedback welcome, especially from people using OpenCode this way.
