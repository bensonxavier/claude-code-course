# Week 3-4: CLAUDE.md

## Goal
Learn to write CLAUDE.md files that give Claude Code deep, accurate context
about your projects — so it acts like a developer who already knows your codebase.

## What You'll Learn
- What CLAUDE.md is and where Claude reads it from
- How to write effective project context
- Rules, constraints, and style guides
- Memory patterns across sessions
- Global vs project-level context

## Key Concept
CLAUDE.md is a Markdown file that Claude Code reads automatically when you
start a session in that directory. Think of it as onboarding docs for Claude.

## File Locations Claude Checks
1. `./CLAUDE.md` — current project (most specific)
2. Parent directories up the tree
3. `~/.claude/CLAUDE.md` — global (applies everywhere)

## Anatomy of a Great CLAUDE.md
```markdown
# Project Name

## What This Is
[2-3 sentence description of what the project does]

## Tech Stack
- Language: TypeScript
- Framework: Next.js 14
- Database: PostgreSQL + Prisma
- Testing: Vitest

## Folder Structure
src/
  components/   UI components
  lib/          Shared utilities
  app/          Next.js app router pages

## Rules
- Always use strict TypeScript (no `any`)
- Write tests before implementation (TDD)
- Never commit directly to main

## Current Task
[What you're working on right now]

## Known Issues
[Bugs or quirks Claude should be aware of]
```

## Step-by-step practice

1. Create a temporary project folder and add a small sample file so you have something concrete to work with.
2. Write a minimal CLAUDE.md file with sections for project description, tech stack, folder structure, and rules.
3. Start Claude Code inside that folder and ask: "What context do you have about this project?"
4. Add a few practical rules, such as coding style preferences or workflow constraints, and test whether Claude follows them.
5. Create a nested subfolder with its own CLAUDE.md and verify that the extra context only applies there.
6. Review the result, refine the file, and note what worked best in your notes.

## Before/after example

Before: a CLAUDE.md file with only a short project description.

After: a CLAUDE.md file with sections for project purpose, stack, folder structure, rules, and current task. This makes Claude's responses more structured and more aligned with the project.

## When Stuck
- Ask Claude: "What context do you have about this project?"
- Docs: https://docs.anthropic.com/en/docs/claude-code/memory
- Check `resources/hints.md` → Week 3-4 section
