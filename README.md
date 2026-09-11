# Send plugin

Publish what you are working on as a live, shareable web page — without leaving
your agent.

Send creates and edits hosted sites, returns a real URL, and reports who opened
it. This plugin bundles the hosted Send MCP server and a skill that teaches the
agent when to reach for it.

## Install

**Grok Build**

```
grok plugin install send
```

**Claude Code**

```
/plugin marketplace add Sendco/send-plugin
/plugin install send@send
```

Or point any MCP-capable client at the server directly:

```
https://www.send.co/mcp
```

## Authentication

Send uses OAuth 2.1 with dynamic client registration. There is no API key to
copy and nothing to configure.

- Endpoint: `https://www.send.co/mcp` (Streamable HTTP)
- On first tool call your client opens a browser to sign in
- Tokens are held by your client, never by this repository

A free Send account is enough to start. Create one at
[send.co](https://www.send.co).

## What is included

| Component | |
|---|---|
| MCP server | `.mcp.json` — the hosted Send server |
| Skill | `creating-sites-with-send` — when to publish, and the edit loop |

## What it does

- **Create** a hosted page from HTML the agent writes
- **Edit** an existing page so the link you already shared stays good
- **Read back** what is currently published before changing it
- **Manage** sites, link settings and uploaded images

## What it will not do

Send publishes to a public URL. The plugin will not publish without you asking
for it, and the skill instructs the agent to confirm before putting anything
outward-facing at a live link.

## Links

- [send.co](https://www.send.co)
- [Report an issue](https://github.com/Sendco/send-plugin/issues)

## License

MIT — see [LICENSE](LICENSE).
