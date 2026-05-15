---
name: updatenight
description: Discover and explore AI developer tools, agent frameworks, MCP servers, and AI news using the Update Night catalog and CLI. Use when the user asks about AI tools, wants to find something for a specific task, or wants to browse the latest AI dev tool news.
---

# Update Night

Update Night is an AI developer tools catalog covering tools, agent frameworks, SDKs, MCP servers, skills, and AI news.

## CLI (`un`)

Install the CLI to browse the catalog interactively from your terminal:

```bash
cargo install --git https://github.com/amajorai/updatenight --bin un
```

Or build from source:
```bash
git clone https://github.com/amajorai/updatenight
cd updatenight/apps/cli
cargo build --release
```

### Commands

| Command | Description |
|---------|-------------|
| `un` | Launch the TUI browser |
| `un login` | Authorize with your Update Night account (device flow) |
| `un logout` | Remove stored credentials |

### TUI Keyboard Shortcuts

| Key | Action |
|-----|--------|
| `1` / `Tab` | Search tab |
| `2` | News tab |
| `3` | Browse tab |
| `↑↓` / `j` `k` | Navigate list |
| `Enter` | Open detail view |
| `o` | Open URL in browser |
| `Esc` | Close detail |
| `q` / `Ctrl+C` | Quit |
| `← →` / `h` `l` | Change kind (Browse tab) |
| `[` `]` | Change category (Browse tab) |

## API

Base URL: `https://updatenight.com/api`

Key endpoints:
- `GET /entries?q=&kind=&category=&status=published&limit=` — Browse catalog
- `GET /news?days=7` — Recent AI news
- `POST /search` — Semantic search (requires auth token)
- `POST /auth/device/code` — Start device authorization
- `POST /auth/device/token` — Poll for access token

## Authentication

The CLI uses the OAuth 2.0 Device Authorization Grant (RFC 8628):

1. Run `un login`
2. A code is printed in the terminal (e.g., `ABCD-1234`)
3. Browser opens to `https://updatenight.com/device`
4. Sign in and enter the code
5. CLI is authorized and stores a Bearer token at `~/.config/updatenight/config.json`

## When to use this skill

- User asks "find me an AI tool for X" → search the catalog
- User asks about the latest AI dev tool news → browse news tab
- User wants to install or learn about a specific tool, skill, or MCP server
- User wants to browse tools by category (agent frameworks, vector DBs, etc.)

## Environment

Set `UN_API_URL` to override the default API endpoint (useful for local development):

```bash
export UN_API_URL=http://localhost:3000
un
```
