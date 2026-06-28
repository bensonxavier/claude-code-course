# Claude Code Course

This repository is a self-paced learning path for building practical Claude Code skills from setup through advanced workflows. Each week focuses on a specific capability, and the course is designed to be completed one module at a time.

## What this course covers

- Claude Code installation and environment setup
- Basic CLI usage, REPL interaction, and file context
- Writing effective CLAUDE.md files for project guidance
- Planning mode and agentic loop workflows
- MCP server integration
- Parallel subagent coordination
- Git-based workflows with Claude Code

## How to use this repository

1. Read this file first for the overall flow.
2. Open [instructions.md](instructions.md) and follow the setup steps for your operating system.
3. Start with the current weekly module folder, beginning with [week-01-02-claude-cli](week-01-02-claude-cli/).
4. Read that module's README and follow the numbered task files in its [tasks](week-01-02-claude-cli/tasks/) folder.
5. Track your progress in [PROGRESS.md](PROGRESS.md) by marking completed items with [x].
6. Keep notes in [resources/my-notes.md](resources/my-notes.md) as you go.
7. Use [resources/hints.md](resources/hints.md) if you get stuck instead of skipping ahead.

## Suggested study rhythm

- Days 1-3: read the module README, review the concepts, and complete the first half of the tasks.
- Days 4-6: finish the remaining tasks and experiment with the tool in a small project.
- Day 7: review what you learned, update your notes, and mark progress in [PROGRESS.md](PROGRESS.md).

## Practical learning approach

This course is designed to build usable Claude Code skills, not just to complete checklists. Each module encourages a repeatable loop:

1. Start with a realistic task or mini-project.
2. Give Claude a clear prompt and context.
3. Inspect the result carefully and identify what was useful or weak.
4. Refine the prompt, context, or instructions.
5. Repeat until the outcome is genuinely useful.

For concrete project ideas and success criteria, see [resources/practice-projects.md](resources/practice-projects.md). For module-level outcomes and assessment checkpoints, see [resources/learning-outcomes.md](resources/learning-outcomes.md).

## Recommended setup before Week 1

Make sure you have:

- Node.js 18 or newer
- A working Claude Code installation
- Your ANTHROPIC_API_KEY configured in your shell profile

Example quick start on macOS:

```bash
brew install node
npm install -g @anthropic-ai/claude-code
export ANTHROPIC_API_KEY="your-key-here"
claude --version
claude "say hello"
```

## Weekly module flow

- Week 1-2: Claude CLI
- Week 3-4: CLAUDE.md
- Week 5-6: Plan and Loop Modes
- Week 7-8: MCP Servers
- Week 9-10: Parallel Subagents
- Week 11-12: Git Integration

Work through each module in order. Later modules are intended to build on the habits and knowledge you developed earlier.

## Progress tracking

Use [PROGRESS.md](PROGRESS.md) as your main tracker. It contains the task checklist for each week. When you finish a task, update the corresponding line from [ ] to [x].

## Notes and support

- Write down discoveries, examples, and mistakes in [resources/my-notes.md](resources/my-notes.md).
- Refer to [resources/glossary.md](resources/glossary.md) for terminology.
- If a task is unclear, check [resources/hints.md](resources/hints.md) before searching elsewhere.

## Capstone project

At the end of the course, learners should complete a capstone project that brings together the skills from all modules. A good capstone could be:

- build a small project helper that uses Claude Code to generate, review, and refine files,
- create a project-specific CLAUDE.md and use it to improve a real coding workflow,
- or produce a mini automated workflow that includes planning, testing, and Git-based review.

The capstone should be judged by whether the final outcome is genuinely useful, not just whether the checklist is complete.

## Goal

The goal is not to rush through the course, but to build confidence with Claude Code through repeated practice, careful notes, and steady progress.
