I just added Linux clipboard support for OpenCode in aicage. aicage runs coding agents in Docker containers, and OpenCode is one of the built-in agents.

For a first start, `pipx install aicage`, then in your project folder run `aicage opencode`.

Then just press Enter / OK through the two config screens and OpenCode starts in a container as if it were on the host.

If you want clipboard support, enable the clipboard option on the first config screen. That option only shows up on Linux hosts.

Repo: https://github.com/aicage/aicage

Feedback welcome, especially from people using OpenCode this way.
