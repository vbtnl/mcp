# Installing the vbtnl MCP server

vbtnl is a remote MCP server. There is nothing to clone, build or run locally.

- Address: `https://api.vbtnl.com/mcp`
- Transport: Streamable HTTP
- Auth: OAuth in the browser. Do not ask the user for an API key or token.

## Steps

1. Add the server to the MCP settings with the address only:

```json
{
  "mcpServers": {
    "vbtnl": {
      "type": "streamableHttp",
      "url": "https://api.vbtnl.com/mcp"
    }
  }
}
```

2. On the first connection the client opens a vbtnl page in the browser. The user logs in (or creates a free account at https://app.vbtnl.com/login) and presses Allow.

3. Check the connection by calling `list_projects`. An empty list is a normal answer for a new account.

## Notes

- If the client cannot connect or sign-in fails, the user should open https://app.vbtnl.com, sign in, accept the current terms and connect again.
- Projects live on vbtnl, not in the local folder. Write files with the vbtnl tools, not to disk.
- Read `get_platform_guide` once before building a new project.
