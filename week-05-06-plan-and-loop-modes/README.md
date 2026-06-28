# Week 5-6: Plan & Loop Modes

## Goal
Use Claude Code's planning and agentic loop capabilities to handle complex,
multi-step tasks with minimal hand-holding.

## What You'll Learn
- Planning mode (`--plan`) for reviewing work before execution
- Agentic loops for autonomous multi-step tasks
- Permission and approval workflows
- Auto-fix loops (write → test → fix → repeat)

## Key Concept
Instead of one prompt → one response, agentic mode lets Claude take a sequence
of actions (read files, write code, run commands, fix errors) in a loop until
the task is complete or it needs your input.

## When to Use Each Mode
| Mode | Best for |
|------|---------|
| One-shot | Simple, contained tasks |
| Plan mode | Complex tasks where you want to review the approach first |
| Loop mode | Tasks with clear success criteria (e.g., "make tests pass") |

## Step-by-step practice

1. Pick a real multi-step task such as refactoring a small module, fixing several issues, or generating a new feature.
2. Run the task in plan mode and review the proposed approach before allowing execution.
3. Approve the plan and observe how Claude carries out the steps.
4. Try a second run where you reject or modify one step and observe how the plan changes.
5. Create a small failing test or bug and let Claude work through a loop until the issue is resolved.
6. Note which guardrails helped and which steps still needed your supervision.

## Before/after example

Before: `claude "fix the bug"`

After: `claude "Investigate the bug, explain the likely cause, propose a minimal fix, and verify it with a test before changing the code."`

## When Stuck
- Docs: https://docs.anthropic.com/en/docs/claude-code/agentic-loop
- Check `resources/hints.md` → Week 5-6 section
