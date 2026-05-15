# Update Night Skill

Claude Code skill for browsing the Update Night catalog of AI dev tools, skills, and MCP servers from any AI agent.

Once installed, you can ask your AI assistant to find tools, browse categories, read recent AI news, or look up a specific MCP server or agent framework -- all without leaving your coding session.

## What it does

- Search the catalog by query or task description
- Browse entries by category (agent frameworks, vector DBs, RAG, MCP servers, and more)
- Fetch recent AI dev news from the last N days
- Look up a specific tool, skill, or MCP server by name and get install instructions

## Install

Add the skill to your Claude Code project:

```
/add-skill amajorai/updatenight-skill
```

## Usage examples

```
find me an agent framework that works with TypeScript
what MCP servers are available for databases?
show me the latest AI dev tool news
how do I install the Browserbase MCP?
```

## Authentication

The skill calls the Update Night API. Semantic search requires an Update Night account. Run `un login` with the [Update Night CLI](https://github.com/amajorai/updatenight-cli) to authenticate, or visit [updatenight.com](https://updatenight.com) to sign up.

## Configuration

Set `UPDATENIGHT_API_URL` to override the default API endpoint (`https://server.updatenight.com`).

## Related

- [Update Night CLI](https://github.com/amajorai/updatenight-cli) -- terminal UI for browsing the catalog
- [Update Night MCP](https://github.com/amajorai/updatenight-mcp) -- MCP server for AI assistants to search the catalog
