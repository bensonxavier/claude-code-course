# Glossary

Key terms used throughout the Claude Code course.

---

**Agentic loop**
A mode where Claude takes a sequence of actions autonomously (read → write → run → fix)
without waiting for a prompt after each step. Continues until a goal is met or it needs input.

**CLAUDE.md**
A Markdown file Claude Code reads automatically at session start.
Acts as persistent memory and project context. Lives in project root or `~/.claude/`.

**Claude Code**
Anthropic's agentic coding CLI tool. Lets you interact with Claude from the terminal
with native access to your files, shell, and git.

**Context window**
The amount of text Claude can "see" at once. Large files may exceed this. You can
provide focused excerpts rather than full files.

**MCP (Model Context Protocol)**
An open standard for connecting Claude to external tools and data sources —
databases, APIs, file systems, web browsers. Configured via `mcp.json`.

**MCP server**
A process that implements the MCP protocol and exposes tools to Claude.
Can be local (a script you run) or remote (a hosted service).

**Orchestrator**
In parallel subagent setups, the "parent" Claude session that coordinates work
and delegates to subagents.

**Plan mode**
A Claude Code mode (`--plan`) where Claude proposes a multi-step plan for review
before executing any steps. Useful for complex or risky tasks.

**REPL**
Read-Eval-Print Loop. The interactive `claude` session where you have a back-and-forth
conversation. Start it by running `claude` with no arguments.

**Subagent**
A Claude Code instance spawned by an orchestrator to handle a specific subtask
in parallel with other subagents.

**System prompt**
Background instructions given to Claude before your conversation starts.
CLAUDE.md content is injected as part of the system prompt.

**Token**
The basic unit Claude processes text in. Roughly 0.75 words = 1 token.
Your API costs and context window limits are measured in tokens.
