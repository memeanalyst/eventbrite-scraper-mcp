# Eventbrite Scraper — MCP Server

Search every event on Eventbrite by city, category or keyword from your AI agent or MCP client — title, start and end in the event's own timezone, the moment it was listed, venue and city, category, format and tags, as clean structured records. Recurring series come back as a single record. With monitoring mode on, scheduled runs deliver only newly listed events instead of the same corpus again.

This repo is the MCP listing for the [Eventbrite Scraper](https://apify.com/magnova/eventbrite-scraper) Actor by Magnova on Apify. The server is hosted by Apify at the pinned endpoint below — there is nothing to install or run from this repository; you just point your MCP client at the URL.

## Tools

The pinned connection loads a focused tool set:

- **magnova--eventbrite-scraper** — Search Eventbrite events by city, category or keyword, with an optional only-new monitoring mode. Returns structured records: title, start/end with timezone, listed-at time, venue and city, category, format and tags, plus event URL.
- **fetch-actor-details** — Fetch the Actor's full input schema, pricing, and documentation, so an agent can check parameters and cost before running it.
- **get-actor-run / get-dataset-items** — Run and storage helpers, loaded automatically, used to fetch the results a run produced.

## Connect

Pinned endpoint (Streamable HTTP):

```
https://mcp.apify.com?tools=fetch-actor-details,magnova/eventbrite-scraper
```

On first connect, your client will ask you to sign in with your Apify account (OAuth). If your client cannot do OAuth, pass your Apify API token as an `Authorization: Bearer <YOUR_APIFY_TOKEN>` header instead.

### Cursor / VS Code / other Streamable HTTP clients

```json
{
  "mcpServers": {
    "eventbrite-scraper": {
      "url": "https://mcp.apify.com?tools=fetch-actor-details,magnova/eventbrite-scraper"
    }
  }
}
```

### Claude Desktop

Claude Desktop's config file only runs local commands, so use the `mcp-remote` bridge:

```json
{
  "mcpServers": {
    "eventbrite-scraper": {
      "command": "npx",
      "args": [
        "-y",
        "mcp-remote",
        "https://mcp.apify.com?tools=fetch-actor-details,magnova/eventbrite-scraper"
      ]
    }
  }
}
```

The same pinned URL also lives in this repo's `.mcp.json`, and `server.json` is the listing for the Official MCP Registry, published as `io.github.memeanalyst/eventbrite-scraper-mcp`.

## Pricing

Pay per event, billed to your own Apify account: **$0.01 per event returned — $10 per 1,000 events**. No start fee, no subscription, and you are only charged for records actually delivered.

## Links

- Actor on Apify Store: https://apify.com/magnova/eventbrite-scraper
- MCP endpoint: https://mcp.apify.com?tools=fetch-actor-details,magnova/eventbrite-scraper

*Event records come from Eventbrite's public destination pages.*
