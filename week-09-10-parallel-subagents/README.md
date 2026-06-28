# Week 9-10: Parallel Subagents

## Goal
Learn to coordinate multiple Claude agents working in parallel on large
codebases, complex refactors, or multi-component tasks.

## What You'll Learn
- What subagents are and when to use them
- Spawning parallel Claude Code instances
- Dividing work across agents
- Merging results and handling conflicts

## Key Concept
For large tasks (migrating a codebase, refactoring multiple modules at once),
a single Claude session becomes the "orchestrator" that spawns subagents —
each working on a separate part — then merges the results.

## Pattern
```
Orchestrator Claude
├── Subagent A: migrate auth module
├── Subagent B: migrate user module  
└── Subagent C: migrate payment module
         ↓
Orchestrator merges, resolves conflicts, runs tests
```

## Step-by-step practice

1. Choose a task that can be split into independent parts, such as refactoring three modules or reviewing different folders.
2. Define a clear role for each subagent so each one knows what to work on.
3. Start the orchestrator workflow and assign one subagent to each part of the task.
4. Ask each subagent to produce a small result or patch, then merge those results into one coherent outcome.
5. Run tests or validation steps and resolve any conflicts between the outputs.
6. Review the process and note where parallel work helped and where coordination was still needed.

## When Stuck
- Docs: https://docs.anthropic.com/en/docs/claude-code/sub-agents
- Check `resources/hints.md` → Week 9-10 section
