# Client configurations

The examples are for an instance at `https://identifier.netgenium.online`. For your instance three values differ: the address of the server, the name of the server and the name of the environment variable that holds the token. Copy the address from the **Server address** field on the **MCP token** tab of your instance; the two names are derived from it by the rule in [The name of the server and the environment variable](https://www.netgenium.com/en/docs/agentic-development/mcp-server-setup?utm_source=github#server-name).

The token itself never goes into a configuration file — only the name of the environment variable that holds it.

| Client | File | How |
|---|---|---|
| Claude Code | [`claude-code.mcp.json`](claude-code.mcp.json) | save as `.mcp.json` in the root of the project; approve the server at the first start |
| Codex | [`codex.config.toml`](codex.config.toml) | add the entry to `~/.codex/config.toml` |
| Microsoft Copilot Studio | — | add the server as a tool of the agent: address `https://identifier.netgenium.online/api.aspx`, header `Authorization` with the value `Bearer ngt_...` |
| Any other MCP client over HTTP | — | the same address and header |

## Signing in instead of a token

Claude Code and Codex can also connect by signing in, without a token:

```bash
claude mcp add --transport http netgenium https://identifier.netgenium.online/api.aspx
```

Then start the sign-in with the `/mcp` command in an open conversation.

```bash
codex mcp add netgenium --url https://identifier.netgenium.online/api.aspx
codex mcp login netgenium
```

The personal token is the simpler choice for developer tools — it works for an instance in a subdirectory as well and needs no interactive sign-in.
