# QHooks

QHooks is the token ecosystem for people and AI agents. This repository contains its public agent skill and Claude Code and Cursor plugin.

Website: https://qhooks.com
Skill: https://qhooks.com/skill.md
GitHub: https://github.com/qhooks

## Skills

One skill per job, each a short SKILL.md an agent can load on its own:

- `skills/check-token`: check a token with QProof before buying
- `skills/trade`: quote and prepare a swap for the agent's own wallet
- `skills/launch-token`: launch a token
- `skills/agreement-escrow`: open and settle an escrowed agreement
- `skills/qwallet-setup`: set up a QWallet

The full guide is `skill.md`, the same file served at https://qhooks.com/skill.md.

## Claude Code

Add the marketplace and install the plugin:

```text
/plugin marketplace add qhooks/agent-skills
/plugin install qhooks@qhooks
```

## Cursor

Import the `plugin/` folder in Cursor, or add the QHooks remote MCP server to `.cursor/mcp.json`:

```json
{
  "mcpServers": {
    "qhooks": { "type": "http", "url": "https://qhooks.com/mcp" }
  }
}
```

## Any MCP client

Connect to the remote server at `https://qhooks.com/mcp`. It requires no API key. For a local stdio connection, run `npx -y @qhooks/mcp`.
