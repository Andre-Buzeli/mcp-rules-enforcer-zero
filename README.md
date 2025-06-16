# MCP Rules Enforcer Zero

[![npm version](https://img.shields.io/npm/v/@andrebuzeli/mcp-rules-enforcer-zero.svg)](https://www.npmjs.com/package/@andrebuzeli/mcp-rules-enforcer-zero)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

A zero-tool Model Context Protocol (MCP) server that automatically enforces rules from markdown files for AI agents. Perfect for ensuring consistent behavior across VSCode, Cursor AI, Claude Desktop, and other MCP-compatible clients.

## 🚀 Features

- ✅ **Automatic rule injection** into all AI conversations
- ✅ **Environment-based configuration** via `RULE_ROOT`
- ✅ **Hot reload** when rules file changes
- ✅ **NPX ready** - no installation required
- ✅ **TypeScript** implementation with full type safety
- ✅ **IDE integration** for VSCode, Cursor AI, Claude Desktop
- ✅ **Zero tools** - pure automatic functionality
- ✅ **Intelligent caching** for optimal performance

## 📦 Installation & Usage

### Quick Start (NPX - Recommended)

No installation required! Just use NPX:

```bash
npx @andrebuzeli/mcp-rules-enforcer-zero
```

### Global Installation

```bash
npm install -g @andrebuzeli/mcp-rules-enforcer-zero
mcp-rules-enforcer-zero
```

### IDE Integration

#### VSCode / Cursor AI

Add to your `.vscode/mcp.json` file:

```json
{
  "mcpServers": {
    "rules-enforcer-zero": {
      "command": "npx",
      "args": ["@andrebuzeli/mcp-rules-enforcer-zero"],
      "env": {
        "RULE_ROOT": "/path/to/your/rules/directory"
      }
    }
  }
}
```

#### Claude Desktop

Add to your Claude Desktop MCP configuration:

```json
{
  "mcpServers": {
    "rules-enforcer-zero": {
      "command": "npx",
      "args": ["@andrebuzeli/mcp-rules-enforcer-zero"],
      "env": {
        "RULE_ROOT": "/path/to/your/rules/directory"
      }
    }
  }
}
```

## ⚙️ Configuration

### Environment Variables

| Variable | Description | Default |
|----------|-------------|---------|
| `RULE_ROOT` | Path to the `rules.md` file | "rules.md" in current directory |
| `MCP_SERVER_NAME` | Name of the MCP server | "Rules Enforcer Zero" |
| `AUTO_INJECT` | Enable/disable automatic injection | true |

### Rules File

Create a `rules.md` file and point `RULE_ROOT` to it:

```markdown
## Example Rules

1. Always format code with proper indentation
2. Include detailed comments for complex logic
3. Prefer modern syntax over legacy approaches
```

## 📋 How It Works

This server automatically injects rules from your `rules.md` file into AI conversations by:

1. **Resource:** Provides a `rules://current` resource that always returns the current rules
2. **Prompt:** Automatically injects rules into every conversation via an auto-inject prompt
3. **Hot Reload:** Detects when the rules file changes and automatically updates

## 🤔 Why Zero Tools?

This version of the MCP Rules Enforcer is designed for simplicity and minimal complexity. By removing all tools, it:

- Reduces complexity
- Provides a pure "set it and forget it" experience
- Focuses solely on rule injection
- Eliminates unnecessary functions

## 🔧 Testing If It's Working

To verify the rules are being applied:

1. **Ask directly:** "What rules are you following in this conversation?"
2. **Check behavior:** Test if the AI follows your specific rules
3. **Resource access:** Check if `rules://current` resource is available
4. **Logs:** Look for success messages in the server logs

## 🌟 Versions Available

| Version | Description | NPM Package |
|---------|-------------|-------------|
| **Zero** | No tools, just rule injection | `@andrebuzeli/mcp-rules-enforcer-zero` |
| **Simple** | One multi-purpose tool | `@andrebuzeli/mcp-rules-enforcer-simple` |
| **Full** | Multiple specialized tools | `@andrebuzeli/mcp-rules-enforcer` |

## 📄 License

MIT