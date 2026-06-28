# Week 7-8: MCP Servers

## Goal
Extend Claude Code by connecting it to external tools and APIs through
the Model Context Protocol (MCP).

## What You'll Learn
- What MCP is and how it works
- Connecting built-in and third-party MCP servers
- Building a simple custom MCP server
- Practical use cases (GitHub, databases, web search, etc.)

## Key Concept
MCP (Model Context Protocol) is a standard that lets Claude connect to
external tools — databases, APIs, file systems, web browsers — as if they
were native capabilities. You configure servers in your Claude Code settings.

## MCP Config Location
```
~/.claude/mcp.json   (global)
.claude/mcp.json     (project-level)
```

## Example Config
```json
{
  "servers": {
    "github": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-github"],
      "env": { "GITHUB_TOKEN": "your-token" }
    }
  }
}
```

## Step-by-step practice

1. Create a simple local project and decide on one tool you want Claude to use, such as reading files or querying a local database.
2. Set up a basic MCP server or use a lightweight example server that exposes one or two tools.
3. Add the server configuration in `.claude/mcp.json` or `~/.claude/mcp.json` and verify that it is discovered.
4. Ask Claude to use the tool for a small task, such as listing files, reading a file, or summarizing data.
5. Extend the setup with a second tool and test how the agent combines them.
6. Write down the workflow and any errors you hit so you can compare it with your later experiments.

## Tasks (37)
See `PROGRESS.md` for the full task list — tasks for this module will be
added here once you unlock it by completing Week 5-6.

## When Stuck
- MCP docs: https://modelcontextprotocol.io
- Claude Code MCP guide: https://docs.anthropic.com/en/docs/claude-code/mcp
- Check `resources/hints.md` → Week 7-8 section
