# Repository Agent Guidance

Use the repo-maintainer agent for repository maintenance tasks in this workspace.

## When to use the agent
Choose the repo-maintainer agent when the request is about:
- local and remote git maintenance
- branch creation or switching
- commits, pushes, and syncs
- remote URL inspection or fixes
- GitHub repository handoff when `gh` is unavailable
- deployment safety for pull requests targeting main

## Preferred approach
- Inspect repo state before changing anything.
- Act as the manager of all repositories in this workspace rather than treating each repository in isolation.
- Before a push-related action, inspect the status of all local repositories in the workspace and identify any repositories with local modifications.
- If any repository in the workspace has local modifications and a push-related action is requested, confirm the intended push/commit workflow with the user before proceeding.
- Preserve existing deployed pages and deployment outputs. Do not disturb live deployment targets unless the user explicitly requests a change.
- For any pull request targeting main, treat deployment safety as a required gate. Review the repo-specific deployment workflow before making changes.
- If a deployment issue is observed, follow a short test → verify → fix → re-test loop. Keep fixes minimal and reversible.
- If a problem cannot be resolved safely and needs human judgment, pause and request confirmation before applying a fix.
- If a sync or update request identifies a repository that exists remotely but not locally, ask the user for confirmation before pulling the remote main/master branch into the local workspace.
- Treat this confirmation step as part of every sync request and any explicit request to update from a remote repository.
- If the local repository has uncommitted or unpushed changes, confirm the intended pull/sync action with the user before proceeding.
- Use the repo-specific build, test, and deployment commands from the repository docs or workflow files rather than assuming one workflow fits every repo.
- Prefer native git commands over GitHub CLI.
- Avoid repeated `gh` retries when the tool is missing.
- Use the repo-maintenance skill for repeatable maintenance patterns.
- For larger tasks, coordinate multiple specialist subagents when helpful.

## Repository-specific notes
- Repository remotes are GitHub-based and should be read from the current repo's `origin`.
- Maintenance requests typically involve status checks, branch setup, and safe pushes.
- If a GitHub operation cannot be done through `gh`, provide the repository URL and a ready-to-paste summary.
