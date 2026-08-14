# Ambush AI plugins for Grok

The official Grok Build marketplace for Ambush AI. It publishes the Ambush
Streams plugin, which connects Grok to the production Ambush MCP server through
OAuth and teaches Grok how to manage personalized news streams, per-event
processing, and delivery safely.

## Install in Grok Build

Add the Ambush AI marketplace:

```sh
grok plugin marketplace add Ambush-AI/grok-plugins
```

Install and trust the Ambush Streams plugin:

```sh
grok plugin install ambush-streams --trust
```

Start a new Grok session or reload plugins from `/plugins`. The first Ambush
tool call opens OAuth in your browser. You can also open `/mcps`, select
`ambush-streams`, and press `i` to connect your account.

Verify the installation:

```sh
grok plugin details ambush-streams
grok mcp doctor ambush-streams
```

Never paste an Ambush API key into Grok configuration or chat.

## Try it

- "Create a stream for material cybersecurity incidents affecting Canadian banks."
- "Pause my AI regulation stream."
- "Show the five latest items from my semiconductor supply-chain stream."
- "For every event from that stream, produce a trade thesis or no-trade result and send it to my Trade Ideas Slack channel."

## Grok on the web

At [grok.com/connectors](https://grok.com/connectors), create a **Custom**
connector with this MCP server URL:

```text
https://api.ambush.ai/mcp
```

Complete the Ambush OAuth flow. The web connector exposes the same tools, while
the Grok Build plugin additionally bundles Ambush workflow and deletion-safety
guidance.

## MCP-only installation

To expose the tools in Grok Build without the bundled skill:

```sh
grok mcp add --transport http ambush-streams https://api.ambush.ai/mcp
```

Grok handles OAuth automatically. Prefer the plugin for normal use because it
also teaches Grok how to resolve stream names, handle pagination, configure
delivery, and confirm permanent deletion.

## Repository layout

```text
.grok-plugin/
  marketplace.json
  plugin-index.json
plugins/
  ambush-streams/
    .grok-plugin/plugin.json
    .mcp.json
    skills/manage-ambush-streams/SKILL.md
```

## Development

Validate the plugin package with a current Grok Build installation:

```sh
grok plugin validate ./plugins/ambush-streams
```

Test this checkout as a local marketplace:

```sh
grok plugin marketplace add /absolute/path/to/grok-plugins
grok plugin install ambush-streams --trust
```

Remove the test installation with:

```sh
grok plugin uninstall ambush-streams --confirm
grok plugin marketplace remove /absolute/path/to/grok-plugins
```

