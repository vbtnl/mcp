# Install the vbtnl MCP server in ChatGPT

ChatGPT connects to vbtnl as a custom MCP server. You add it from the Plugins page in ChatGPT on the web. The old developer mode switch is gone, and you don't need it.

You need a vbtnl account. The free plan is enough: [app.vbtnl.com/login](https://app.vbtnl.com/login).

You also need a ChatGPT plan that allows custom MCP servers with tools that change things, because vbtnl writes files and publishes. OpenAI lists the plans on its [help page](https://help.openai.com/en/articles/12584461-connecting-custom-mcp-servers-in-chatgpt).

## 1. Add the server

1. Open **Plugins** in the ChatGPT sidebar, or go to `chatgpt.com/plugins`.
2. Press **Add** and choose **Add custom MCP server**.
3. Name it `vbtnl` and paste the address under **Connection**:

```text
https://api.vbtnl.com/mcp
```

4. Leave **Authentication** on **OAuth**.
5. Tick **I understand and want to continue** and press the create button.
6. A vbtnl page opens: log in and press **Allow**.
7. Install the plugin. It shows up under **Installed**.

## 2. Use it

Start a new chat, type `@` and choose vbtnl, then ask:

```text
Use vbtnl. Make a small site with my portfolio and put it online.
```

ChatGPT asks you to confirm actions that change something, such as writing files or publishing. It creates a project, writes the code, starts it and replies with a draft address. Say "ship it" and it publishes to production.

## Troubleshooting

- **There is no "Add custom MCP server" item.** Your plan or your workspace role doesn't allow it. In a workspace, ask an admin.
- **ChatGPT can't write files or publish.** Your plan may allow only tools that read data. vbtnl needs tools that write files and publish.
- **The tools look old.** Open vbtnl on the Plugins page, press **Refresh** and start a new chat.
- **Sign-in fails on the vbtnl page.** Open [app.vbtnl.com](https://app.vbtnl.com), sign in, accept the current terms and connect again.

## More

- [vbtnl docs for ChatGPT](https://vbtnl.com/docs/chatgpt)
- [ChatGPT MCP: how to add an MCP server now that developer mode is gone](https://vbtnl.com/blog/how-to/add-mcp-server-to-chatgpt)
- Other clients: [Claude Code](install-claude-code.md), [Claude Desktop](install-claude-desktop.md), [Codex](install-codex.md), [Cursor](install-cursor.md)
