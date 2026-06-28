# Hints & Common Gotchas

Use this before Googling. Each section maps to a module.

---

## Week 1-2: Claude CLI

### 🍎 macOS Issues

**"command not found: claude"**
→ npm global bin isn't in your PATH. Fix:
```bash
echo 'export PATH="$(npm bin -g):$PATH"' >> ~/.zshrc
source ~/.zshrc
```

**API key resets after closing terminal**
→ You used `export` in the session but didn't save it. Add to `~/.zshrc`:
```bash
echo 'export ANTHROPIC_API_KEY="sk-ant-..."' >> ~/.zshrc
source ~/.zshrc
```

**Permission denied installing npm packages**
→ Never use `sudo npm install -g`. Instead, fix npm permissions:
```bash
mkdir ~/.npm-global
npm config set prefix '~/.npm-global'
echo 'export PATH=~/.npm-global/bin:$PATH' >> ~/.zshrc
source ~/.zshrc
npm install -g @anthropic-ai/claude-code
```

---

### 🪟 Windows (WSL) Issues

**"command not found: claude" inside WSL**
→ npm global bin path isn't set. Fix:
```bash
echo 'export PATH="$HOME/.npm-global/bin:$PATH"' >> ~/.bashrc
npm config set prefix '~/.npm-global'
source ~/.bashrc
npm install -g @anthropic-ai/claude-code
```

**WSL not installed / "wsl command not found"**
→ You need Windows 10 version 2004+ or Windows 11. Open PowerShell as Administrator:
```powershell
wsl --install
# Then restart your computer
```

**API key not persisting in WSL**
→ Add to `~/.bashrc`, not `~/.zshrc` (WSL Ubuntu uses bash by default):
```bash
echo 'export ANTHROPIC_API_KEY="sk-ant-..."' >> ~/.bashrc
source ~/.bashrc
```

**Can't access Windows files from WSL**
→ Your C: drive is at `/mnt/c/`. Example:
```bash
cd /mnt/c/Users/YourName/Documents
```

**VS Code not connecting to WSL**
→ Install the "WSL" extension in VS Code, then from your WSL terminal run:
```bash
code .
```

**Copy/paste not working in WSL terminal**
→ Use `Ctrl+Shift+C` / `Ctrl+Shift+V` in Windows Terminal (not `Ctrl+C/V`).

---

### Both Platforms

**Claude truncates long files**
→ Break large files into focused sections. You don't need to pass the whole file — just the relevant parts.

**Output looks garbled / broken formatting**
→ Try `--no-stream` to get output all at once instead of streamed.

**Node.js version too old**
→ Claude Code requires Node 18+. Check: `node --version`
- macOS: `brew upgrade node`
- WSL: `sudo apt-get install -y nodejs` may give an old version; use the NodeSource install instead (see Week 1-2 README)

---

## Week 3-4: CLAUDE.md

**Claude isn't following my rules**
→ Be more explicit. "Never use var" is vague — try "Always use `const` or `let`. Never use `var` — treat it as a compile error."

**Claude doesn't seem to read my CLAUDE.md**
→ Check you're running `claude` from the same directory as CLAUDE.md.
Run `claude "what context do you have?"` to verify.

**CLAUDE.md is getting too long**
→ Good instinct. Keep it under ~300 lines. Move detailed docs to separate files and reference them from CLAUDE.md.

**Finding CLAUDE.md on Windows (WSL)**
→ Your home directory in WSL is `~` = `/home/yourusername/`. Global CLAUDE.md lives at `~/.claude/CLAUDE.md`. This is separate from your Windows user folder.

---

## Week 5-6: Plan & Loop Modes

**Agentic loop runs forever**
→ Always give a clear success condition: "stop when all tests pass" or "stop after creating 3 files."

**Claude keeps asking for permission**
→ You can pre-approve specific actions in your project config. See the permissions docs.

**Plan mode output is confusing**
→ Ask Claude to explain each step before approving: "explain what step 3 will actually do."

---

## Week 7-8: MCP Servers

**MCP server won't connect**
→ Check your `mcp.json` syntax. Run `claude mcp list` to see what's registered.
Restart Claude Code after config changes.

**MCP config file location**
- macOS: `~/.claude/mcp.json`
- Windows WSL: `~/.claude/mcp.json` (inside WSL home, not Windows home)

**"Tool not found" error**
→ The MCP server may not have started. Check the server's own logs.

**Building your own MCP server**
→ Start from the official TypeScript SDK template. Don't reinvent the wire protocol.

---

## Week 9-10: Parallel Subagents

**Subagents making conflicting changes**
→ Design tasks to be independent. Each subagent should own specific files/modules only.

**Orchestrator losing track**
→ Have the orchestrator write a `coordination.md` that each subagent reads and updates.

---

## Week 11-12: Git Integration

**Git not installed**
- macOS: `brew install git`
- WSL: `sudo apt-get install git`

**Commit messages are too generic**
→ Pass the diff, not just the description: `git diff --staged | claude "write commit message"`

**Claude suggests wrong branch strategy**
→ Add your branching strategy (gitflow, trunk-based, etc.) to your project's CLAUDE.md.

**Merge conflicts: Claude picks wrong side**
→ Tell it explicitly: "prefer the changes from the feature branch, keep the main branch's error handling."

**Line ending issues on Windows (CRLF vs LF)**
→ Configure git inside WSL:
```bash
git config --global core.autocrlf input
```
This prevents Windows-style line endings from polluting your commits.
