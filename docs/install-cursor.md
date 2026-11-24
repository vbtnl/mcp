# Install the vbtnl MCP server in Cursor

vbtnl is a remote MCP server: Cursor connects to its address over HTTP. There is nothing to install or run on your computer.

You need Cursor and a vbtnl account. The free plan is enough: [app.vbtnl.com/login](https://app.vbtnl.com/login).

## 1. Add the server

Open `~/.cursor/mcp.json` (for all projects) or `.cursor/mcp.json` in a project folder, and add vbtnl:

```json
{
  "mcpServers": {
    "vbtnl": {
      "url": "https://api.vbtnl.com/mcp"
    }
  }
}
```

If the file already has other servers, add the `vbtnl` entry next to them inside `mcpServers`.

The file holds only the address and no token, so a project-level `mcp.json` is safe to commit.

## 2. Log in

Open **Cursor Settings**, find the MCP section and the **vbtnl** server. Cursor asks you to sign in. A vbtnl page opens in the browser: log in and press **Allow**.

## 3. Build something

Open the Cursor agent chat and ask:

```text
Make a landing page with a waitlist and host it on vbtnl.
```

The agent writes the files into a project on vbtnl, not into your local folder. It runs the app and replies with a draft address. Say "ship it" and it publishes to production.

## Troubleshooting

- **The server has no tools, or sign-in does not start.** Switch the server off and on in the MCP settings, or restart Cursor.
- **Sign-in fails on the vbtnl page.** Open [app.vbtnl.com](https://app.vbtnl.com), sign in, accept the current terms and connect again.
- **The agent writes files locally.** Tell it to build on vbtnl. The project lives on the server.
- **Remove the server.** Delete the `vbtnl` entry from `mcp.json`.

## More

- [vbtnl docs for Cursor](https://vbtnl.com/docs/cursor)
- [How to host an app built with Claude or Codex](https://vbtnl.com/blog/how-to/host-app-built-with-claude-or-codex)
- Other clients: [Claude Code](install-claude-code.md), [Claude Desktop](install-claude-desktop.md), [Codex](install-codex.md), [ChatGPT](install-chatgpt.md)
