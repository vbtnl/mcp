# Install the vbtnl MCP server in Claude Code

vbtnl is a remote MCP server: Claude Code connects to its address over HTTP. There is nothing to install or run on your computer.

You need Claude Code and a vbtnl account. The free plan is enough: [app.vbtnl.com/login](https://app.vbtnl.com/login).

## 1. Add the server

```bash
claude mcp add --transport http vbtnl https://api.vbtnl.com/mcp
```

## 2. Log in

Start Claude Code, type `/mcp`, choose **vbtnl** and then **Authenticate**. A vbtnl page opens in your browser: log in and press **Allow**.

You can also log in from the terminal:

```bash
claude mcp login vbtnl
```

There is no token to copy. Claude Code keeps the sign-in and renews it by itself.

## 3. Check the connection

```bash
claude mcp list
```

vbtnl should be listed as connected. Then ask in Claude Code:

```text
List my vbtnl projects.
```

An empty list is a normal answer for a new account.

## 4. Build something

```text
Make a landing page with a waitlist and host it on vbtnl.
```

Claude Code writes the files into a project on vbtnl, runs the app and gives you a draft address. Say "ship it" and it publishes to production.

## Use vbtnl in every folder

By default the server is saved for the current folder only. Add `--scope user` to use it everywhere:

```bash
claude mcp add --scope user --transport http vbtnl https://api.vbtnl.com/mcp
```

## Share it with your team

Add `--scope project` and Claude Code writes the server into `.mcp.json` in the project root. Or create the file by hand:

```json
{
  "mcpServers": {
    "vbtnl": {
      "type": "http",
      "url": "https://api.vbtnl.com/mcp"
    }
  }
}
```

The file holds only the address, so it is safe to commit. Each person logs in to their own vbtnl account.

## Troubleshooting

- **The server shows as failed or needs authentication.** Type `/mcp`, choose **vbtnl** and authenticate again.
- **Sign-in fails on the vbtnl page.** Open [app.vbtnl.com](https://app.vbtnl.com), sign in, accept the current terms and connect again.
- **Claude Code edits local files instead of the project on vbtnl.** Say it directly: "build this on vbtnl". The code lives on the server, not in your folder.
- **Remove the server:** `claude mcp remove vbtnl`.

## More

- [vbtnl docs for Claude Code](https://vbtnl.com/docs/claude-code)
- [Claude Code MCP: how to add an MCP server (local or remote)](https://vbtnl.com/blog/how-to/add-mcp-server-to-claude-code)
- [Claude Code Telegram bot: build and deploy one for free](https://vbtnl.com/blog/how-to/deploy-telegram-bot-free-claude-code)
- Other clients: [Claude Desktop](install-claude-desktop.md), [Codex](install-codex.md), [Cursor](install-cursor.md), [ChatGPT](install-chatgpt.md)
