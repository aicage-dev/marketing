# Discord post for OpenCode community projects

I just added Linux clipboard support for OpenCode in [aicage](https://github.com/aicage/aicage).

aicage runs coding agents in Docker containers, and OpenCode is one of the built-in agents.

For a first start, this is enough:

```bash
pipx install aicage
cd your-project
aicage opencode
```

Then just press Enter / OK in the two config screens and it will start OpenCode in a container as if it were running on the host.

If you want clipboard support, enable the clipboard option on the first config screen. It only shows up on Linux hosts. After that, press OK through the second screen and OpenCode starts in the container with host clipboard access wired through.

Repo: https://github.com/aicage/aicage
Feedback welcome, especially from people using OpenCode this way.
