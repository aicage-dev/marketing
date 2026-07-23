# aicage Marketing Strategy

## Product summary

**aicage** runs AI coding agents (Claude Code, Codex, Gemini CLI, Copilot, and 6 more) inside Docker containers. It gives you a hard security boundary between the agent and your host machine while keeping the developer experience identical.

- Install: `pipx install aicage`
- Run: `aicage <agent>`
- 10 built-in agents, customizable via extensions
- Nice TUI setup screen, per-project config
- No telemetry, image signature verification

## Target audiences

| Audience | Where they hang out | What they care about |
|---|---|---|
| Security-conscious devs | HN, r/programming | Agent safety, host isolation |
| Docker/container users | r/docker, r/selfhosted | Container tooling, dev environments |
| Local AI enthusiasts | r/LocalLLaMA, HN | Running agents locally, privacy |
| AI power users | Twitter/X, HN | Multi-agent workflows, tooling |

## Key messaging angles

### Primary: Security isolation
AI coding agents have deep access to your machine. aicage puts a hard Docker boundary around them. You mount only what the agent needs. The agent can't touch the rest.

### Secondary: Multi-agent flexibility
One tool, ten agents. Switch between Claude, Codex, Gemini, Copilot, Goose, and more without different setups. Same workflow, same config.

### Tertiary: Developer experience
Not a compromise. The agent sees your project, your configs, your credentials. It just runs in a container. Setup UI, per-project config, extensions.

## Channel strategy

### Hacker News (highest ROI)
- **Format:** Show HN post
- **Timing:** Tue-Thu, 9-11am US Eastern
- **Tone:** Technical, concise, show the problem and solution
- **Key:** Lead with the security problem, not the product

### Reddit
- **r/docker:** Focus on containerization angle, dev environment isolation
- **r/LocalLLaMA:** Focus on running AI agents locally with security
- **r/programming:** General "running agents in containers" concept
- **r/selfhosted:** Self-hosted AI coding setup

### Twitter/X
- **Format:** Thread with screenshots/GIFs
- **Tone:** Punchy, visual, link-heavy

## Content assets needed

- [ ] Screenshot of TUI overview screen (already exists in wiki)
- [ ] GIF of `aicage claude` starting up
- [ ] Terminal output showing the setup flow
- [ ] Architecture diagram (optional)

## Posting schedule

See [calendar.md](calendar.md) for the detailed timeline.

## Success metrics (first 30 days)

- GitHub stars: target 100+
- GitHub forks: target 20+
- HN front page (top 30)
- Reddit posts: 50+ upvotes combined
- First community contributions or issues from new users
