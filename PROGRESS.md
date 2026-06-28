# Course Progress Tracker

> Update this file as you complete tasks. Use `[x]` to check off items.
> Last updated: _fill in date_

---

## Overall Progress: 0 / 196 tasks

---

## ✅ Week 1-2: Claude CLI (0/32)

### Setup & Installation
- [ ] 📖 Read the Claude Code overview docs
- [ ] 📖 Read `instructions.md` → your OS platform setup section (macOS or Windows)
- [ ] 🛠️ **macOS:** Install Node.js via Homebrew: `brew install node` — OR — **Windows:** Enable WSL 2 (`wsl --install` in PowerShell as Admin), then install Node inside Ubuntu
- [ ] 🛠️ Verify Node.js: `node --version` (must be v18+)
- [ ] 🛠️ Install Claude Code: `npm install -g @anthropic-ai/claude-code`
- [ ] 🛠️ **macOS:** Add API key to `~/.zshrc` — OR — **Windows (WSL):** Add API key to `~/.bashrc`
- [ ] 🛠️ Reload your shell config and verify: `echo $ANTHROPIC_API_KEY`
- [ ] ✅ Run `claude --version` and confirm it works

### Basic Usage
- [ ] 📖 Read the Claude Code quickstart guide
- [ ] 🛠️ Run your first prompt: `claude "say hello"`
- [ ] 🛠️ Pass a file to Claude: `claude -f myfile.txt "summarize this"`
- [ ] 🛠️ Use stdin: `echo "what is 2+2" | claude` (works on macOS and WSL)
- [ ] 🧪 Ask Claude to explain itself: `claude "what can you do?"`

### Interactive Mode
- [ ] 🛠️ Start the interactive REPL: `claude` (no args)
- [ ] 🛠️ Have a multi-turn conversation in the REPL
- [ ] 🛠️ Use `/help` in the REPL to see available commands
- [ ] 🛠️ Exit with `/exit` or Ctrl+C
- [ ] 🧪 Try asking Claude to write a small script and run it

### Output & Flags
- [ ] 📖 Read about `--output` and `--format` flags
- [ ] 🛠️ Get JSON output: `claude --output json "list 3 fruits"`
- [ ] 🛠️ Use `--no-stream` for non-streaming output
- [ ] 🛠️ Try `--verbose` to see token usage
- [ ] 🛠️ Pipe output to a file: `claude "write a haiku" > haiku.txt`

### Working with Code
- [ ] 🛠️ Ask Claude to write a Python "hello world" function
- [ ] 🛠️ Ask Claude to fix a bug in a file you create with a deliberate error
- [ ] 🛠️ Ask Claude to add comments to an existing function
- [ ] 🧪 Ask Claude to refactor a messy piece of code
- [ ] ✅ Review what Claude changed — do you understand every edit?

### Context & Files
- [ ] 📖 Learn how Claude Code handles file context
- [ ] 🛠️ Pass multiple files: `claude -f a.py -f b.py "compare these"`
- [ ] 🛠️ Ask Claude to generate a new file and save it
- [ ] 🧪 Experiment with how much context Claude can handle

### Reflection
- [ ] ✅ Write 3 things you learned in `resources/my-notes.md`
- [ ] ✅ Write 1 thing that confused you and how you resolved it
- [ ] ✅ Review all tasks above — are there any you want to redo?

---

## 🔒 Week 3-4: CLAUDE.md (0/45)

Complete Week 1-2 before starting this module.

### Understanding CLAUDE.md
- [ ] 📖 Read the official CLAUDE.md documentation
- [ ] 📖 Understand where Claude Code looks for CLAUDE.md files
- [ ] 📖 Learn the difference between project-level and global CLAUDE.md
- [ ] 🛠️ Create a minimal CLAUDE.md in a test project folder
- [ ] 🛠️ Verify Claude Code reads it: start a session and ask "what are your instructions?"

### Writing Project Context
- [ ] 📖 Study examples of effective CLAUDE.md files
- [ ] 🛠️ Add a project description section to your CLAUDE.md
- [ ] 🛠️ Add a "tech stack" section (language, frameworks, tools)
- [ ] 🛠️ Add a "folder structure" section with a tree diagram
- [ ] 🧪 Test: does Claude reference your context in its answers?

### Rules & Constraints
- [ ] 📖 Learn how to write rules Claude will follow
- [ ] 🛠️ Add a coding style rule (e.g., "always use TypeScript strict mode")
- [ ] 🛠️ Add a "never do" rule (e.g., "never use `var`")
- [ ] 🛠️ Add a workflow rule (e.g., "always write tests before implementation")
- [ ] 🧪 Test each rule by asking Claude to do something it should refuse/modify

### Memory & Persistence
- [ ] 📖 Understand how Claude Code's memory works across sessions
- [ ] 🛠️ Add a "current task" section that you update
- [ ] 🛠️ Add a "decisions made" log section
- [ ] 🛠️ Add a "known issues" section
- [ ] 🧪 Start a fresh session — does Claude pick up where you left off?

### Advanced CLAUDE.md
- [ ] 📖 Learn about nested CLAUDE.md files (per-folder context)
- [ ] 🛠️ Create a subfolder with its own CLAUDE.md for a specific component
- [ ] 🛠️ Test that subfolder context only applies inside that folder
- [ ] 🛠️ Add custom slash commands or shortcuts
- [ ] 🧪 Build a CLAUDE.md for a real (or sample) project you care about

### Global CLAUDE.md
- [ ] 📖 Find where your global CLAUDE.md lives (`~/.claude/CLAUDE.md`)
- [ ] 🛠️ Create a global CLAUDE.md with your personal preferences
- [ ] 🛠️ Add your preferred response style
- [ ] 🛠️ Add languages/frameworks you always use
- [ ] ✅ Verify global context applies in a fresh project with no local CLAUDE.md

### Iteration & Refinement
- [ ] 🧪 Review your CLAUDE.md — is any section redundant?
- [ ] 🧪 Ask Claude: "how could this CLAUDE.md be improved?"
- [ ] 🛠️ Apply at least 2 improvements Claude suggests
- [ ] ✅ Write a summary of what makes a great CLAUDE.md in `my-notes.md`

### Reflection
- [ ] ✅ What was the most impactful thing you added to CLAUDE.md?
- [ ] ✅ What did Claude ignore, and why?
- [ ] ✅ What would you change about how you approached this module?

---

## 🔒 Week 5-6: Plan & Loop Modes (0/21)

### Planning Mode
- [ ] 📖 Read the docs on `--plan` / planning mode
- [ ] 🛠️ Run a complex task with `--plan`: `claude --plan "refactor this module"`
- [ ] 🛠️ Review the plan before approving — does it make sense?
- [ ] 🛠️ Approve the plan and watch it execute
- [ ] 🧪 Try rejecting a plan step and see how Claude adapts

### Loop / Agentic Mode
- [ ] 📖 Understand what "agentic loop" means in Claude Code
- [ ] 🛠️ Run a multi-step task without intervening
- [ ] 🛠️ Use `--dangerously-skip-permissions` (in a safe sandbox) and observe
- [ ] 🧪 Give Claude a task with 5+ steps — how far does it get unassisted?

### Approval Workflows
- [ ] 📖 Learn about the permission model (what Claude asks before doing)
- [ ] 🛠️ Configure which actions require approval in your project
- [ ] 🛠️ Set up auto-approval for specific low-risk actions
- [ ] 🧪 Build a small workflow where Claude loops until tests pass

### Auto-Fix Loops
- [ ] 🛠️ Ask Claude to write code, run tests, and fix failures automatically
- [ ] 🛠️ Introduce a failing test and let Claude loop to fix it
- [ ] 🧪 How many iterations does it take? What breaks the loop?

### Reflection
- [ ] ✅ When is plan mode better than just asking? Write your answer.
- [ ] ✅ What guardrails do you want on agentic loops for real projects?
- [ ] ✅ Update `my-notes.md` with your key takeaways

---

## 🔒 Week 7-8: MCP Servers (0/37)

> Tasks listed in `week-07-08-mcp-servers/README.md`

---

## 🔒 Week 9-10: Parallel Subagents (0/20)

> Tasks listed in `week-09-10-parallel-subagents/README.md`

---

## 🔒 Week 11-12: Git Integration (0/41)

> Tasks listed in `week-11-12-git-integration/README.md`

---

## 🏁 Course Complete Checklist

- [ ] All 196 tasks checked off above
- [ ] `my-notes.md` has at least one entry per module
- [ ] Built at least one real project using Claude Code
- [ ] Can explain every module concept without notes
