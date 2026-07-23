# Details, Tricks, Problem/Solution parts of aicage

To really make aicage comfortably useful quite a long list of things had to come together over time. I try to loosely
list them here.

## Images

### Tool Stack

Running agents in containers needs images with a broad tool stack for development in popular coding languages.

> Responsibility: image building/defining repo `aicage-image-base`

### Building/Updating

Aicage builds images online or when needed (legal non-redistributable agents or custom base-images/agents/extensions).
It takes care on programm start of when to pull, build, update images itself.

Examples:

- new agent version: When the agent has a new version, aicage typically has a new images 15 minutes later (or instantly
  if locally built).
- weekly updates of base images with broad dev tool chains
- aicage auto-removes old images from local box after updates to free up disk space
- user defined local extensions are automatically added after remote source images are updated.

> Responsibility: image building/defining repos `aicage-image-base`, `aicage-image` and the Python code from repo
> `aicage`.

## Container environment close to host environment

Making the container environment close to the host has advantages in many small places.

Examples:

- user and his UID/GID: aicage uses the same UID and GID as the host. This allows clean sharing of files with the host.
- user HOME and name: aicage uses the same username and HOME path. This eliminates some issues with paths or agents
  using the username.
- image auto-selected for matching distro family: Helps in cases with paths in shared files (Python venv with symlink to
  OS files). Helps users write extensions for the distro they are familiar with.

> on Windows hosts not all apply, aicage strives to still be close and provide the best compromise.
> 
> - Auto-selected distro is Ubuntu.
> - User is root in the container.
> - Host WSL view of paths, etc. is used.

## User UI in aicage

For a long time this was a CLI prompt menu, which was/is limited when updating configs and not very sexy to use. Users
needed to read docs to really understand basics.

Now just recently we added a nice TUI menu, which looks better, handles config updates and hopefully for a large part
frees user from having to read manuals early on for basic things.
