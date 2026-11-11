# NET Genium MCP server

[![NET Genium MCP connector](https://glama.ai/mcp/connectors/online.netgenium.mcp/net-genium/badges/score.svg)](https://glama.ai/mcp/connectors/online.netgenium.mcp/net-genium)

Every [NET Genium Online](https://www.netgenium.com/en/products/netgenium-online?utm_source=github) instance has a built-in MCP server. Connect Claude, ChatGPT, Claude Code, Codex, Microsoft Copilot Studio or any other MCP client, and your agent works directly in your instance:

- **reads and writes the data** of your applications, including the change history and attachments,
- **reads and changes the application model** — edit forms, view pages, controls, queries, scripts, permissions and the SQL data model — so it builds and extends real applications, not just rows,
- **searches the platform documentation**, so what it builds follows the conventions of the platform.

Underneath is a real SQL database with no limit on records. A single-user instance is free, with no time limit and no payment card.

This repository holds the connection guide, ready-made client configurations, the list of tools and example prompts. The server itself is part of NET Genium and is not open source.

## Connect

| | Address | Authentication |
|---|---|---|
| **One address for all instances** | `https://mcp.netgenium.online/api.aspx` | OAuth — you pick your instance during the sign-in |
| Address of your instance | `https://<instance>.netgenium.online/api.aspx` | OAuth, or a personal MCP token (`Authorization: Bearer ngt_...`) |
| Self-hosted NET Genium | `https://<host>/api.aspx` | OAuth (instance in the root of an HTTPS site), or a personal MCP token |

Reading and writing are two separate permissions: on the consent screen you decide whether the agent may only read, or write as well. Only users with administrator rights can use the MCP server, and every request runs as the user who signed in — the agent never sees more than that user.

### Claude and ChatGPT

Add a custom connector with the address `https://mcp.netgenium.online/api.aspx`, enter the name of your instance, sign in to it and choose what the agent may do. Nothing is copied or stored by hand. The connected applications are listed in your instance and can be disconnected at any time.

### Claude Code, Codex and other tools

Developer tools connect with a personal MCP token, which you generate in your instance under **Change password → MCP token**. The same tab offers a **setup prompt** you can paste into Claude Code or Codex, and the tool writes its configuration on its own. To configure it by hand, see [`clients/`](clients/).

The full guide, including Microsoft Copilot Studio and troubleshooting, is [Connecting an AI tool to the MCP server](https://www.netgenium.com/en/docs/agentic-development/mcp-server-setup?utm_source=github).

## Tools

21 tools in three groups: documentation (administrators), reading (token permission *Reading all data and the model via the MCP server*) and writing (*Writing all data and the model via the MCP server*). See [TOOLS.md](TOOLS.md).

## Examples

- [Build a CRM with Claude](examples/crm.md) — one conversation from an empty instance to a working CRM, with a video.
- [Prompts for six common business areas](examples/prompts/) — orders, approvals, complaints, stock, tasks and contracts.

## Links

- Official MCP registry: `com.netgenium/instance`
- [NET Genium AI](https://www.netgenium.com/en/products/ai?utm_source=github) · [Agentic development](https://www.netgenium.com/en/docs/agentic-development?utm_source=github) · [Pricing](https://www.netgenium.com/en/pricing?utm_source=github)
- [Create a free instance](https://www.netgenium.com/en/register.aspx?utm_source=github)

Questions and support: [support](https://www.netgenium.com/en/support?utm_source=github) or support@netgenium.com. Security issues: see [SECURITY.md](SECURITY.md).
