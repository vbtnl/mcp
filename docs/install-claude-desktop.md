# Install the vbtnl MCP server in Claude Desktop and claude.ai

vbtnl is listed in the Claude connector directory. In Claude Desktop and on claude.ai you add it in two clicks, with no terminal and no config file.

You need a Claude account and a vbtnl account. The free vbtnl plan is enough: [app.vbtnl.com/login](https://app.vbtnl.com/login).

## 1. Add vbtnl from the directory

1. Open the [vbtnl page in the Claude directory](https://claude.ai/directory/vbtnl).
2. Press **Connect**.
3. A vbtnl page opens: log in and press **Allow**.

You can also find it inside Claude: open **Customize** in the sidebar (on some accounts it is called **Plugins**), choose **Connectors** and search for `vbtnl`.

Claude Desktop uses the same account as claude.ai. After you connect on one, vbtnl is there on the other too.

## 2. Use it in a chat

Start a new chat and make sure the vbtnl connector is switched on for it. Then ask:

```text
Make a page for my coffee shop with a menu and a booking form, and host it on vbtnl.
```

Claude asks for permission the first time it calls a vbtnl tool. Tools that only read run without a question. Tools that change or delete something ask first.

Claude writes the files, runs the app and replies with a link. Say "ship it" and it publishes to production.

## Add it as a custom connector instead

If your organization only allows custom connectors, add vbtnl by its address:

1. Open **Customize** (or **Plugins**) in the sidebar, then **Connectors**.
2. Press **Add**, then **Add custom connector**.
3. Name it `vbtnl` and paste the address:

```text
https://api.vbtnl.com/mcp
```

4. Press **Add**, then **Connect**, log in to vbtnl and press **Allow**.

The Free Claude plan allows one custom connector.

## Disconnect

Remove the connector in Claude, or open your vbtnl account and disconnect the client in the list of connected apps. Either one stops access at once.

## Troubleshooting

- **You can't find Connectors in Settings.** They moved. Look for **Customize** or **Plugins** in the sidebar.
- **Sign-in fails on the vbtnl page.** Open [app.vbtnl.com](https://app.vbtnl.com), sign in, accept the current terms and connect again.
- **Claude answers without using vbtnl.** Check that the connector is switched on for this chat, and name it in your request: "host it on vbtnl".

## More

- [vbtnl docs for Claude Desktop](https://vbtnl.com/docs/claude-desktop)
- [Claude connectors: what they are and how to add one](https://vbtnl.com/blog/how-to/claude-connectors)
- Other clients: [Claude Code](install-claude-code.md), [Codex](install-codex.md), [Cursor](install-cursor.md), [ChatGPT](install-chatgpt.md)
