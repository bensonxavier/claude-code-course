---
name: repo-maintenance
description: Use this skill to perform repository maintenance tasks such as inspecting state, preparing commits, syncing branches, and handling remote repo operations without depending on GitHub CLI.
---

# Repo Maintenance Skill

## When to use
Use this skill when the task involves:
- checking repository status or history
- creating or switching branches
- committing and pushing changes
- setting or fixing remotes
- syncing local and remote repositories
- handling GitHub repository maintenance when `gh` is unavailable

## Preferred workflow
1. Inspect repository state.
2. Identify the current branch and remote.
3. Choose the safest action for the task.
4. Execute the git operation directly.
5. Report the result and any next steps.

## Rules
- Prefer git-native commands over `gh`.
- Avoid repeated `gh` attempts if it is not installed.
- Do not force-push unless the user explicitly requests it.
- If multiple repositories are involved, work through them one by one.
- If the task is large, split it into smaller steps and use specialist subagents.

## Useful commands
- `git status --short --branch`
- `git remote -v`
- `git remote get-url origin`
- `git branch --all`
- `git log --oneline -5`
- `git add -A`
- `git commit -m "..."`
- `git push origin <branch>`

## Fallback behavior
- If `gh` is missing, stop trying it and continue with git.
- Provide the repo URL and a concise summary for manual GitHub actions.
