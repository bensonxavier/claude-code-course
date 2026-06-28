# Claude Code Course — Instructions & Learning Guide

## Welcome

This 12-week course takes you from zero to confident with Claude Code —
Anthropic's agentic coding tool. Each two-week module focuses on one core
skill area with hands-on tasks you can complete at your own pace.

---

## Platform Setup

Follow the section for your operating system before starting Week 1.

---

### 🍎 macOS Setup

**Step 1 — Install Homebrew (if not already installed)**
```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

**Step 2 — Install Node.js 18+**
```bash
brew install node
node --version   # should print v18.x.x or higher
```

**Step 3 — Install Claude Code**
```bash
npm install -g @anthropic-ai/claude-code
claude --version
```

**Step 4 — Set your API key (persists across sessions)**
```bash
# Open your shell config
open ~/.zshrc     # for zsh (default on macOS Catalina+)
# or: open ~/.bash_profile   # for bash

# Add this line:
export ANTHROPIC_API_KEY="sk-ant-your-key-here"

# Reload the config
source ~/.zshrc
```

**Step 5 — Verify everything works**
```bash
echo $ANTHROPIC_API_KEY   # should print your key
claude "say hello"
```

**Recommended Terminal:** Terminal.app, iTerm2, or the VS Code integrated terminal.

**Recommended Editor:** VS Code — install from https://code.visualstudio.com

---

### 🪟 Windows Setup

Claude Code works best on Windows via **WSL 2** (Windows Subsystem for Linux).
This gives you a real Linux terminal, which is the standard environment for Claude Code.

**Step 1 — Enable WSL 2**

Open PowerShell as Administrator and run:
```powershell
wsl --install
```
Restart your computer when prompted. This installs Ubuntu by default.

**Step 2 — Open Ubuntu**

After restart, search "Ubuntu" in the Start menu and open it.
Complete the Linux username/password setup on first launch.

**Step 3 — Install Node.js 18+ inside WSL**
```bash
# Inside the Ubuntu terminal:
curl -fsSL https://deb.nodesource.com/setup_20.x | sudo -E bash -
sudo apt-get install -y nodejs
node --version   # should print v20.x.x
```

**Step 4 — Install Claude Code**
```bash
npm install -g @anthropic-ai/claude-code
claude --version
```

**Step 5 — Set your API key (persists across sessions)**
```bash
# Open your shell config
nano ~/.bashrc

# Add this line at the bottom:
export ANTHROPIC_API_KEY="sk-ant-your-key-here"

# Save: Ctrl+O → Enter → Ctrl+X to exit nano

# Reload:
source ~/.bashrc
```

**Step 6 — Verify everything works**
```bash
echo $ANTHROPIC_API_KEY   # should print your key
claude "say hello"
```

**Recommended Terminal:** Windows Terminal (install from Microsoft Store) running Ubuntu (WSL).

**Recommended Editor:** VS Code with the "WSL" extension — it connects VS Code to your WSL environment seamlessly. Install the extension, then from WSL run: `code .`

> **Note on native Windows (without WSL):** Claude Code can technically run in PowerShell or Command Prompt via Node.js for Windows, but many features behave differently. WSL is strongly recommended for the best experience and most accurate match to the course material.

---

## How the Course Works

### Weekly Rhythm (suggested)
- **Days 1-3:** Read the module README, watch any linked resources, do the first half of tasks
- **Days 4-6:** Complete remaining tasks, experiment freely
- **Day 7:** Review, write notes, commit progress, unlock next module

### Task Types
Each task is tagged with one of:
- 📖 **Read** — understand a concept or doc
- 🛠️ **Do** — hands-on exercise you complete in terminal
- 🧪 **Experiment** — open-ended exploration
- ✅ **Check** — verify you understand with a mini quiz or reflection

### Progress Tracking
Open `PROGRESS.md` and check off tasks using `[x]` as you complete them.
Update your `ACTIVE MODULE` in `CLAUDE.md` when you advance.

---

## Module Summaries

### Week 1-2: Claude CLI (32 tasks)
Learn to install, configure, and drive Claude Code from the command line.
By the end, you'll be fluent with the basic REPL loop, flags, and file context.

**Key skills:** installation, `claude` command basics, stdin/file input, output modes

---

### Week 3-4: CLAUDE.md (45 tasks)
Master the project context file that Claude Code reads automatically.
You'll learn how to write effective project context, rules, and memory.

**Key skills:** writing good CLAUDE.md files, project-level instructions, memory management

---

### Week 5-6: Plan & Loop Modes (21 tasks)
Discover how to use planning mode for complex tasks and loop mode for
iterative, multi-step work without constant hand-holding.

**Key skills:** `--plan` flag, agentic loops, approval workflows, auto-fixing

---

### Week 7-8: MCP Servers (37 tasks)
Connect Claude Code to external tools and APIs via Model Context Protocol.
Build and use MCP servers to extend what Claude can do in your projects.

**Key skills:** MCP concepts, connecting servers, building simple MCP tools

---

### Week 9-10: Parallel Subagents (20 tasks)
Run multiple Claude agents in parallel to tackle large codebases, refactors,
and multi-file tasks efficiently.

**Key skills:** spawning subagents, coordinating work, merging results

---

### Week 11-12: Git Integration (41 tasks)
Use Claude Code natively with Git — commits, branches, PR review, conflict
resolution, and automated changelog generation.

**Key skills:** git workflows, commit message generation, PR automation, diff review

---

## Tips for Success

1. **Type everything yourself** — copy-pasting kills retention. Even if you peek at an answer, retype it.
2. **Break things on purpose** — the best way to understand a tool is to watch it fail.
3. **Keep `my-notes.md` open** — jot discoveries and "aha" moments as they happen.
4. **Don't rush modules** — depth > speed. A concept you truly understand beats five you kind of know.
5. **Revisit earlier modules** — after Week 5, go back and notice how your CLAUDE.md files could improve.

---

## Getting Help

- Check `resources/hints.md` before searching externally
- Claude Code docs: https://docs.anthropic.com/en/docs/claude-code
- Each module README has a "When Stuck" section
