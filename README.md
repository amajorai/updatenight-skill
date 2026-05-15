# Update Night Skill

Claude Code skill for browsing the Update Night catalog of AI dev tools, agent frameworks, MCP servers, and AI news from any AI agent session.

Once installed, ask your AI assistant to find tools, browse categories, read recent AI news, or look up a specific MCP server or agent framework without leaving your session.

## What it does

- Search the catalog by query or task description
- Browse entries by category (agent frameworks, vector DBs, RAG, MCP servers, and more)
- Fetch recent AI dev news from the last N days
- Look up a specific tool, skill, or MCP server by name and get install instructions

## Usage examples

```
find me an agent framework that works with TypeScript
what MCP servers are available for databases?
show me the latest AI dev tool news
how do I install the Browserbase MCP?
what are the best RAG tools right now?
```

The skill is invoked as `/updatenight:updatenight` or you can just describe what you want and Claude will use it automatically.

## Installation

### Claude Code (plugin install)

```bash
claude --plugin-url https://github.com/amajorai/updatenight-skill/archive/refs/heads/main.zip
```

Or clone locally and load:

```bash
git clone https://github.com/amajorai/updatenight-skill
claude --plugin-dir ./updatenight-skill
```

### Claude Code (manual skill)

Copy `SKILL.md` into your project's `.claude/skills/updatenight/` directory:

```bash
mkdir -p .claude/skills/updatenight
curl -fsSL https://raw.githubusercontent.com/amajorai/updatenight-skill/main/SKILL.md \
  -o .claude/skills/updatenight/SKILL.md
```

The skill becomes available as `/updatenight` in that project.

### Claude Code (via MCP instead)

If you prefer to give Claude Code direct API access rather than using the skill, add the MCP server:

```bash
claude mcp add updatenight /usr/local/bin/updatenight-mcp
```

See [Update Night MCP](https://github.com/amajorai/updatenight-mcp) for how to build the MCP server binary.

## Authentication

Semantic search requires an Update Night account. Run `un login` with the [Update Night CLI](https://github.com/amajorai/updatenight-cli) to authenticate. Text search works without an account.

## Configuration

Set `UPDATENIGHT_API_URL` to override the default API endpoint (`https://server.updatenight.com`).

## Plugin structure

This repo is structured as a Claude Code plugin:

```
updatenight-skill/
├── .claude-plugin/
│   └── plugin.json       # plugin manifest
├── skills/
│   └── updatenight/
│       └── SKILL.md      # skill definition (invoked as /updatenight:updatenight)
├── SKILL.md              # root copy for direct project use
└── README.md
```

## Related

- [Update Night CLI](https://github.com/amajorai/updatenight-cli) -- terminal UI for browsing the catalog
- [Update Night MCP](https://github.com/amajorai/updatenight-mcp) -- MCP server for AI assistants to search the catalog
