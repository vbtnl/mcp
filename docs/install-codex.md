# Install the vbtnl MCP server in Codex

vbtnl is a remote MCP server: Codex connects to its address over HTTP. There is nothing to install or run on your computer.

You need the Codex CLI and a vbtnl account. The free plan is enough: [app.vbtnl.com/login](https://app.vbtnl.com/login).

The commands here were checked with Codex CLI 0.166.

## 1. Add the server and log in

```bash
codex mcp add vbtnl --url https://api.vbtnl.com/mcp
codex mcp login vbtnl
```

A vbtnl page opens in your browser: log in and press **Allow**. Recent versions of Codex start the sign-in right after `codex mcp add`. Then the second command is not needed.

There is no token to copy.

On a machine without a browser, for example over SSH, add `--no-browser`. Codex prints a link, and you open it on any computer.

## 2. Check the connection

```bash
codex mcp list
```

vbtnl should be in the list with `OAuth` in the auth column. Open a new Codex session and ask:

```text
List my vbtnl projects.
```

An empty list is a normal answer for a new account.

## 3. Build something

```text
Build a FastAPI service with a /health check and host it on vbtnl.
```

Codex writes the files into a project on vbtnl, runs the app and gives you a draft address. Say "ship it" and it publishes to production.

## The config file

`codex mcp add` writes the server into `~/.codex/config.toml`. You can also add it by hand:

```toml
[mcp_servers.vbtnl]
url = "https://api.vbtnl.com/mcp"
```

The servers in this file work in every folder. The Codex IDE extension reads the same file, so vbtnl shows up there too.

## Troubleshooting

- **Codex does not see the tools.** Servers are loaded when a session starts. Open a new session after `codex mcp add`.
- **`Not logged in` in `codex mcp list`, or authorization errors.** Run `codex mcp login vbtnl`. If the login expired, run `codex mcp logout vbtnl` and log in again.
- **Sign-in fails on the vbtnl page.** Open [app.vbtnl.com](https://app.vbtnl.com), sign in, accept the current terms and connect again.
- **Codex edits local files instead of the project on vbtnl.** Say it directly: "build this on vbtnl". The code lives on the server, not in your folder.
- **Remove the server:** `codex mcp remove vbtnl`.

## More

- [vbtnl docs for Codex](https://vbtnl.com/docs/codex)
- [Codex MCP: how to add an MCP server to Codex CLI](https://vbtnl.com/blog/how-to/add-mcp-server-to-codex)
- [Codex vs Claude Code in 2026](https://vbtnl.com/blog/comparisons/codex-vs-claude-code)
- Other clients: [Claude Code](install-claude-code.md), [Claude Desktop](install-claude-desktop.md), [Cursor](install-cursor.md), [ChatGPT](install-chatgpt.md)
