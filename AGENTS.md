# Repository Agent Guidance

Use the repo-maintainer agent for repository maintenance tasks in this workspace.

## When to use the agent
Choose the repo-maintainer agent when the request is about:
- local and remote git maintenance
- branch creation or switching
- commits, pushes, and syncs
- remote URL inspection or fixes
- GitHub repository handoff when `gh` is unavailable

## Preferred approach
- Inspect repo state before changing anything.
- Prefer native git commands over GitHub CLI.
- Avoid repeated `gh` retries when the tool is missing.
- Use the repo-maintenance skill for repeatable maintenance patterns.
- For larger tasks, coordinate multiple specialist subagents when helpful.

## Repository-specific notes
- Repository remotes are GitHub-based and should be read from the current repo's `origin`.
- Maintenance requests typically involve status checks, branch setup, and safe pushes.
- If a GitHub operation cannot be done through `gh`, provide the repository URL and a ready-to-paste summary.
