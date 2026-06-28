# Week 1-2: Claude CLI

## Goal
Get comfortable using Claude Code from the command line. By the end of this
module you should be able to drive Claude to read, write, and modify files
without touching a GUI.

## What You'll Learn
- Installing and configuring Claude Code
- Basic CLI flags and usage patterns
- Interactive (REPL) vs one-shot mode
- Passing files and stdin as context
- Reading and piping output

---

## Setup Checklist

### 🍎 macOS

```bash
# 1. Install Node.js (if not already)
brew install node
node --version   # v18+ required

# 2. Install Claude Code
npm install -g @anthropic-ai/claude-code

# 3. Set API key (add to ~/.zshrc to persist)
export ANTHROPIC_API_KEY="sk-ant-your-key-here"
source ~/.zshrc

# 4. Verify
claude --version
claude "say hello"
```

### 🪟 Windows (WSL 2 — recommended)

Run all commands inside your **Ubuntu (WSL)** terminal, not PowerShell.

```bash
# 1. Install Node.js inside WSL
curl -fsSL https://deb.nodesource.com/setup_20.x | sudo -E bash -
sudo apt-get install -y nodejs
node --version   # v18+ required

# 2. Install Claude Code
npm install -g @anthropic-ai/claude-code

# 3. Set API key (add to ~/.bashrc to persist)
echo 'export ANTHROPIC_API_KEY="sk-ant-your-key-here"' >> ~/.bashrc
source ~/.bashrc

# 4. Verify
claude --version
claude "say hello"
```

> If you haven't set up WSL yet, see the full guide in `instructions.md` → Windows Setup.

---

## Key Commands Reference

| Command | What it does |
|---------|-------------|
| `claude "prompt"` | One-shot prompt |
| `claude` | Start interactive REPL |
| `claude -f file.txt "prompt"` | Include file as context |
| `claude --output json "prompt"` | JSON output |
| `claude --verbose "prompt"` | Show token usage |
| `cat file \| claude` | Pipe stdin (Mac/WSL) |

---

## Step-by-step practice

1. Create a small practice folder and add a sample file such as `notes.txt` or `hello.py`.
2. Install Claude Code and verify it works with `claude --version` and `claude "say hello"`.
3. Run a one-shot prompt with file context, for example: `claude -f notes.txt "summarize this"`.
4. Start the interactive REPL with `claude` and ask it a few follow-up questions in the same session.
5. Try a few flags such as `--output json`, `--verbose`, and piping output to a file.
6. Ask Claude to create or modify a tiny script, then review the result carefully and explain what changed.

## Practical success criteria

By the end of this module, you should be able to:
- start Claude Code from the terminal,
- give a clear prompt with enough context,
- inspect the output for accuracy and usefulness,
- and refine the prompt when the first response is incomplete.

### Before/after prompt example

Before: `claude "summarize this file"`

After: `claude -f notes.txt "Summarize this file in 5 bullet points for a beginner audience and highlight the most important action items."`

See [resources/learning-outcomes.md](../resources/learning-outcomes.md) for the formal module assessment criteria.

## Platform-Specific Notes

### macOS
- Default shell is **zsh** — your config file is `~/.zshrc`
- Use `open .` to open the current folder in Finder
- Terminal shortcut: `Cmd+T` for new tab, `Cmd+K` to clear

### Windows (WSL)
- You're running **bash** inside Ubuntu — config file is `~/.bashrc`
- Access your Windows files at `/mnt/c/Users/YourName/`
- From WSL, open VS Code in current folder: `code .` (requires WSL extension)
- Copy/paste in Windows Terminal: `Ctrl+Shift+C` / `Ctrl+Shift+V`

---

## When Stuck
- Run `claude --help` for full flag reference
- Docs: https://docs.anthropic.com/en/docs/claude-code/cli-reference
- Check `resources/hints.md` → Week 1-2 section

## Practice Project
Create a folder `practice/` inside this module and use it for all exercises.
Don't delete your work — reviewing it later is part of learning.
