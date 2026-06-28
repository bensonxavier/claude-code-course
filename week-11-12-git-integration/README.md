# Week 11-12: Git Integration

## Goal
Use Claude Code as a first-class participant in your Git workflow — from
commit messages to PR reviews to merge conflict resolution.

## What You'll Learn
- Generating meaningful commit messages
- Automated PR descriptions and changelogs
- Reviewing diffs with Claude
- Resolving merge conflicts with Claude's help
- Branch-level automation

## Key Concept
Claude Code can read your git history, diffs, and staged changes — making it
a powerful co-pilot for all things version control.

## Common Workflows

### Smart Commit Messages
```bash
git add .
claude "write a conventional commit message for these staged changes"
```

### PR Description
```bash
git diff main...feature-branch | claude "write a PR description for this diff"
```

### Conflict Resolution
```bash
# When you have merge conflicts:
claude -f conflicted-file.ts "resolve these merge conflicts, prefer the feature branch logic"
```

### Changelog Generation
```bash
git log v1.0..HEAD --oneline | claude "generate a changelog from these commits"
```

## Step-by-step practice

1. Create a small throwaway Git repository or use a sandbox branch in an existing project.
2. Make a few changes and ask Claude to suggest a conventional commit message.
3. Stage the changes and review the diff together with Claude.
4. Create a pull request description or changelog entry from the diff.
5. Intentionally create a merge conflict in a test branch and ask Claude to help resolve it.
6. Review the final result and document the workflow that felt most useful.

## Tasks (41)
See `PROGRESS.md` — tasks will be detailed here once you unlock this module.

## When Stuck
- Docs: https://docs.anthropic.com/en/docs/claude-code/git
- Check `resources/hints.md` → Week 11-12 section
