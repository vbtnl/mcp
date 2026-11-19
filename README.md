# vbtnl MCP server

[![vbtnl MCP connector](https://glama.ai/mcp/connectors/com.vbtnl/vbtnl/badges/score.svg)](https://glama.ai/mcp/connectors/com.vbtnl/vbtnl)

[vbtnl](https://vbtnl.com) is hosting that your AI agent runs by itself. Connect it to Claude, Codex, Cursor or ChatGPT and ask for a site, a Telegram bot or an API. The agent writes the code into a cloud sandbox, runs it, reads the logs and publishes it to a public HTTPS address.

```
https://api.vbtnl.com/mcp
```

- Remote server, Streamable HTTP transport.
- Sign-in with OAuth in the browser. There is no token to copy.
- Listed in the [Claude connector directory](https://claude.ai/directory/vbtnl) and in the official MCP Registry as `com.vbtnl/vbtnl`.

This repository holds the connection details and the registry entry. The server itself runs on vbtnl, so there is nothing to install or run locally.

![vbtnl](https://vbtnl.com/og.png)

## Connect

You need a vbtnl account. The free plan is enough to start: [app.vbtnl.com/login](https://app.vbtnl.com/login). Every client below opens a vbtnl page in the browser the first time: log in and press Allow.

### Claude Code

```bash
claude mcp add --transport http vbtnl https://api.vbtnl.com/mcp
```

### claude.ai and Claude Desktop

vbtnl is in the Claude connector directory: open [claude.ai/directory/vbtnl](https://claude.ai/directory/vbtnl) and press **Connect**.

Or add it by hand: Settings → Connectors → Add custom connector. Name it `vbtnl`, paste `https://api.vbtnl.com/mcp` and press Connect.

### Codex

```bash
codex mcp add vbtnl --url https://api.vbtnl.com/mcp
```

### Cursor

Add this to `~/.cursor/mcp.json` (all projects) or `.cursor/mcp.json` (one project):

```json
{
  "mcpServers": {
    "vbtnl": {
      "url": "https://api.vbtnl.com/mcp"
    }
  }
}
```

The file holds only the address, so it is safe to commit.

### ChatGPT (developer mode)

Settings → Connectors → turn on Developer mode → Create. Name it `vbtnl`, paste `https://api.vbtnl.com/mcp`, set Authentication to OAuth and save.

### Other clients

Any client that supports remote MCP servers with OAuth works with the same address.

## Try it

Start a new chat with vbtnl switched on and ask:

```
Make a page for my coffee shop with a menu and a booking form, and host it on vbtnl.
```

The agent creates a project, writes the files, runs the app on a draft address and sends you the link. Say "ship it" and it publishes to production.

## What you can build

Websites and landing pages, web apps, REST APIs, Telegram bots and scheduled jobs. Apps run on Python 3.12, Node.js 22 or as a static site, over HTTPS. The code is yours: you can download the whole project as a .zip at any time.

How a project works:

- **Draft and production.** The agent builds on a draft address. Production changes only when it publishes.
- **Numbered releases.** Every publish is a new version, and production can be rolled back to any earlier one.
- **Database and secrets.** Postgres with separate draft and production databases. Secrets reach the app as environment variables.
- **Production data stays away from the agent.** Reading production data is off by default, and changing it needs a second permission from the owner. Production logs come masked.

## Tools

In Claude, tools that only read run without a question. Tools that change or delete something ask for your confirmation first.

| Group | Tools |
|---|---|
| Projects | `list_projects`, `create_project`, `get_project_context`, `delete_project`, `restore_project`, `get_platform_guide` |
| Files | `list_files`, `read_file`, `write_file`, `write_files`, `edit_file`, `delete_file`, `search` |
| Running code | `exec`, `add_package`, `restart_app`, `run_job`, `get_job_result` |
| Publishing | `publish`, `get_release`, `rollback`, `get_build_logs` |
| Data and settings | `add_database`, `run_sql`, `run_sql_write`, `describe_database`, `set_secrets`, `get_logs` |

What each tool does: [vbtnl.com/docs/mcp-tools](https://vbtnl.com/docs/mcp-tools).

## Plans

| Plan | Price | Projects |
|---|---|---|
| Free | $0 a month | 1 |
| Pro | $19 a month | 3 |
| Max | $49 a month | 10 |

## Links

- Website: [vbtnl.com](https://vbtnl.com)
- Docs: [vbtnl.com/docs/quickstart](https://vbtnl.com/docs/quickstart)
- For AI agents: [vbtnl.com/llms.txt](https://vbtnl.com/llms.txt)
- MCP Registry entry: [server.json](server.json)
- Support: hello@vbtnl.com, or open an issue in this repository

vbtnl is not affiliated with or endorsed by Anthropic or OpenAI.
