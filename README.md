# Marketing Repo KickOff

I wrote `aicage` which "Runs agentic coding assistants in Docker containers" over the last 7-8 months based on earlier
attempts to have my agents run separated from my OS in containers.

By now aicage to me is mature, I've had phases where I use it all day but did not really code much on aicage itself for
weeks.

And just now I added a nice UI, which imho should definitely make it usable comfortable to others.

Now I want to spread the word about this project as right now it lacks users. But I am not into marketing, do not blog
or otherwise write articles.

So in this repo here I want to

- collect resources for marketing
- with help of AI set up a marketing strategy and continuously develop it
- maybe set up AI tools and agents to actively do marketing for me

## aicage - existing resources

> This is mostly internal info about the project and not interesting to users.

> Locally the aicage repos should be available in sibling folders to this repo. Coding agents working on this marketing
> should draw information from those resources.

Currently, aicage lives entirely in the GitHub repos and packages of the `aicage` org.

> A development org `aicage-dev` has clones of repos so I can develop outside the live repos.

### aicage repos and packages

- Repo `aicage`: The Python code for the `aicage` software which users install.
- Repo `aicage.wiki`: The wiki repo for the `aicage` repo
- Repo `aicage-image-base`: Builds base images (based on Linux distro images plus our stack of tools)
- GHCR package `aicage/aicage-image-base`: Holds base images built by repo `aicage-image-base`
- Repo `aicage-image`: Builds aicage images (from base-images with an AI coding agent installed on top)
- GHCR package `aicage/aicage-image`: Holds aicage images built by repo `aicage-image`
- Repo `aicage-custom-samples`: Holds samples of user defined local: base images, agents, extensions
- Repo `aicage-image-util`: Small side repo to build util images to replace tools missing on users box
- Package `aicage/aicage-image-util`: Holds the util image `agent-version`

## Initial steps

- Discussion: How can we spread the word?
  - someone recommended writing texts or articles and spreading them by posts to:
    - [Hacker News](https://news.ycombinator.com/)
    - [Heise](https://www.heise.de/)
    - and so on
  - other approaches, ideas?
- Automation: I'm not much into writing blogs and articles so I am thinking about automation here or using AI agents
  plus code for them or running them.
- more?
