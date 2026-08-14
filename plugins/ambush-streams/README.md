# Ambush Streams for Grok

This plugin connects Grok Build to Ambush Streams through the production OAuth
MCP server and adds workflow guidance for safe stream management.

After installing and connecting your Ambush account, ask Grok to create, list,
inspect, rename, update, pause, resume, or permanently delete streams; configure
per-event processing; route future events to existing connected destinations;
or review emitted news.

The MCP API still exposes legacy tool names such as `list_feeds` and
`create_feed`. The bundled skill maps those identifiers to Ambush Streams
terminology. Permanent deletion always requires explicit confirmation of the
exact stream.

No local executable or API key is required.

