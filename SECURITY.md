# Security

## How access works

- **Every request runs as a user of the instance.** The agent signs in as the user who connected it, or as the owner of the personal MCP token, and never sees more than that user — the same rights, the same allowed IP addresses.
- **Only administrators.** The MCP server can be used only by users with administrator rights. The instance can narrow this further to a list of administrators allowed to use the MCP server.
- **Reading and writing are separate.** On the consent screen, or in the settings of a personal token, reading and writing are two permissions. An agent that only answers questions gets reading and cannot change anything.
- **Sign-in without a token.** Claude and ChatGPT connect through OAuth with PKCE; no password or token is copied anywhere. The connected applications are listed in the instance and can be disconnected at any time.
- **Personal tokens.** A token (`ngt_...`) is stored in the instance only as a hash. Deleting the token ends the access immediately. Keep it in an environment variable, never in a configuration file or a repository.
- **Changes stay visible.** Changes of the model show up in the instance immediately; data can be written together with a record in the change history.

The details are in [The integrated MCP server](https://www.netgenium.com/en/docs/agentic-development/mcp-data-server?utm_source=github).

## Reporting a vulnerability

Please report security issues privately to **support@netgenium.com** — not in a public issue. Describe the affected address, the steps to reproduce and the impact you observed. We will confirm the receipt and keep you informed about the fix.
