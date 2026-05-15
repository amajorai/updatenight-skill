---
name: updatenight
description: Discover and explore AI developer tools, agent frameworks, MCP servers, and AI news using the Update Night catalog. Use when the user asks about AI tools, wants to find something for a specific task, or wants to browse the latest AI dev tool news.
---

# Update Night

Helps users explore the Update Night catalog of AI developer tools, agent frameworks, SDKs, MCP servers, and AI news using the `un` CLI.

## Setup

First, check if `un` is installed. If not, install it:

```bash
which un 2>/dev/null || cargo binstall -y un
```

If `cargo binstall` isn't available, install from releases:

```bash
# macOS Apple Silicon
curl -fsSL https://github.com/amajorai/updatenight-cli/releases/latest/download/un-aarch64-apple-darwin.tar.gz | tar xz -C /usr/local/bin

# macOS Intel
curl -fsSL https://github.com/amajorai/updatenight-cli/releases/latest/download/un-x86_64-apple-darwin.tar.gz | tar xz -C /usr/local/bin

# Linux x86_64
curl -fsSL https://github.com/amajorai/updatenight-cli/releases/latest/download/un-x86_64-unknown-linux-gnu.tar.gz | tar xz -C /usr/local/bin
```

## Usage

Launch the interactive TUI to search and browse the catalog:

```bash
un
```

Authenticate for semantic search (optional but recommended):

```bash
un login
```

## TUI tabs

- **Search** — type to search the catalog; authenticated users get semantic search
- **News** — recent AI dev news from the last 7 days
- **Browse** — browse by kind (Tools / Skills / MCPs) and category

## Keyboard shortcuts

| Key | Action |
|-----|--------|
| `1` / `Tab` | Search tab |
| `2` | News tab |
| `3` | Browse tab |
| `↑` `↓` / `j` `k` | Navigate list |
| `Enter` | Open detail |
| `o` | Open URL in browser |
| `Esc` | Close detail |
| `q` / `Ctrl+C` | Quit |
| `←` `→` / `h` `l` | Change kind (Browse tab) |
| `[` `]` | Change category (Browse tab) |

## When to use

- User asks "find me an AI tool for X" → run `un`, guide them to Search tab
- User asks about latest AI dev news → run `un`, guide them to News tab
- User wants to browse by category → run `un`, guide them to Browse tab
- User needs to install or learn about a specific tool/skill/MCP → run `un` and open the entry
