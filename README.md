# Bing Webmaster Tools MCP Server by Insightful Pipe

[![MCP Compatible](https://img.shields.io/badge/MCP-Compatible-blue)](https://insightfulpipe.com/mcp-servers/bing-webmaster)
[![Insightful Pipe](https://img.shields.io/badge/Insightful_Pipe-MCP_Servers-purple)](https://insightfulpipe.com/mcp-servers)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

> **Connect Bing Webmaster Tools to AI assistants: Bing search queries, crawl data, indexing and URL submission.**

Part of the [Insightful Pipe MCP Server Collection](https://insightfulpipe.com/mcp-servers) — use Bing Webmaster Tools from Claude, ChatGPT, Cursor, and other AI assistants through the Model Context Protocol (MCP).

<img src="images/bing-webmaster-icon.svg" alt="Bing Webmaster Tools MCP Server" width="64" height="64">

## MCP Server URL

```
https://bing-webmaster.insightfulmcp.com/
```

## What is Bing Webmaster Tools MCP?

Bing Webmaster Tools MCP is a **remote Model Context Protocol server** hosted by InsightfulPipe. Access search queries, impressions, clicks, crawl data, and indexing status from Bing Webmaster Tools.

## Installation

### Claude

1. Copy the MCP Server URL: `https://bing-webmaster.insightfulmcp.com/`
2. Open [Claude Connectors Settings](https://claude.ai/settings/connectors)
3. Scroll to the bottom and click **Add custom connector**
4. Paste the URL and click **Add**
5. Click **Connect** on the connector to start authorization
6. Click **Authorize access** in the browser to complete the connection

### ChatGPT

Custom MCP servers are added through ChatGPT's **Developer mode**. Availability depends on your ChatGPT plan, and workspace admins may need to allow it.

1. Turn on **Developer mode** in ChatGPT settings
2. Create a new app for a remote MCP server and paste the URL: `https://bing-webmaster.insightfulmcp.com/`
3. Authorize with your InsightfulPipe account

See OpenAI's guide: [Developer mode and MCP apps in ChatGPT](https://help.openai.com/en/articles/12584461-developer-mode-and-mcp-apps-in-chatgpt)

### Claude Code

```bash
claude mcp add --transport http bing-webmaster https://bing-webmaster.insightfulmcp.com/
```

### Cursor

Add the server to `~/.cursor/mcp.json` (all projects) or `.cursor/mcp.json` (one project):

```json
{
  "mcpServers": {
    "bing-webmaster": {
      "url": "https://bing-webmaster.insightfulmcp.com/"
    }
  }
}
```

Then authorize the connection when Cursor prompts you.

## Available Actions

52 actions: 34 read, 18 write.

### Read Actions (34)

<details>
<summary>Show all 34 read actions</summary>

| Action | Description |
|--------|-------------|
| `get_active_page_preview_blocks` | List all active page preview blocks for a site |
| `get_blocked_urls` | List all blocked URLs for a site |
| `get_children_url_info` | Get URL information for child pages under a parent URL |
| `get_children_url_traffic_info` | Get traffic information for child pages under a parent URL |
| `get_connected_pages` | List all connected pages for a site |
| `get_content_submission_quota` | Get the remaining content submission quota for a site |
| `get_country_region_settings` | Get geographic targeting settings for a site |
| `get_crawl_issues` | Get crawl issues and errors found for a site |
| `get_crawl_settings` | Get the current crawl rate settings for a site |
| `get_crawl_stats` | Get crawl statistics for a site including pages crawled and errors |
| `get_deep_link_blocks` | List all deep link blocks for a site |
| `get_feed_details` | Get detailed status information for a specific sitemap or feed |
| `get_feeds` | List all submitted sitemaps and feeds for a site |
| `get_fetched_url_details` | Get detailed fetch information for a specific URL |
| `get_fetched_urls` | Get a list of recently fetched URLs for a site |
| `get_keyword_data` | Get keyword data including search volume and competition for a query |
| `get_keyword_stats` | Get detailed keyword statistics including impressions and clicks |
| `get_link_counts` | Get inbound link counts for a site |
| `get_page_query_stats` | Get query statistics for a specific page URL |
| `get_page_stats` | Get page-level traffic statistics for a site |
| `get_query_page_detail_stats` | Get detailed traffic statistics for a specific query and page combination |
| `get_query_page_stats` | Get traffic statistics for a specific query on a site |
| `get_query_parameters` | List URL query parameters configured for a site |
| `get_query_stats` | Get search query statistics for a site including impressions, clicks, and position |
| `get_query_traffic_stats` | Get traffic statistics over time for a specific search query |
| `get_rank_and_traffic_stats` | Get combined rank and traffic statistics for a site |
| `get_related_keywords` | Get related keywords and suggestions for a query |
| `get_site_moves` | List all site move requests for a site |
| `get_site_roles` | List all user roles and permissions for a site |
| `get_sites` | List all sites registered in the Bing Webmaster Tools account |
| `get_url_info` | Get indexing and crawl information for a specific URL |
| `get_url_links` | Get inbound links pointing to a specific URL |
| `get_url_submission_quota` | Get the remaining URL submission quota for a site |
| `get_url_traffic_info` | Get traffic information for a list of URLs |

</details>

### Write Actions (18)

| Action | Description |
|--------|-------------|
| `add_blocked_url` | Block a URL from appearing in Bing search results |
| `add_connected_page` | Add a connected page to a site (e.g. a third-party hosted profile/landing page that should be associated with this site) |
| `add_deep_link_block` | Block deep links (sitelinks) from appearing under a site in search results |
| `add_page_preview_block` | Block page previews (snapshots) from appearing in Bing search results |
| `add_query_parameter` | Add a URL query parameter for Bing to handle during crawling |
| `enable_disable_query_parameter` | Enable or disable a URL query parameter configuration |
| `fetch_url` | Request Bing to fetch a specific URL (like 'Fetch as Bingbot') |
| `remove_blocked_url` | Remove a URL block so it can appear in Bing search results again |
| `remove_deep_link_block` | Remove a deep link block from a site |
| `remove_feed` | Remove a submitted feed from a site |
| `remove_page_preview_block` | Remove a page preview block from a site |
| `remove_query_parameter` | Remove a URL query parameter configuration from a site |
| `remove_sitemap` | Remove a previously submitted sitemap from a site |
| `submit_content` | Submit page content directly to Bing for indexing |
| `submit_sitemap` | Submit a sitemap to Bing for a site |
| `submit_url` | Submit a single URL for indexing by Bing |
| `submit_url_batch` | Submit a batch of URLs for indexing by Bing |
| `update_crawl_settings` | Update crawl rate settings for a site |

## Control What Your AI Can Do

You decide what AI agents can do with each connected account:

- **Turn individual actions on or off** for every connected account, so agents only see the actions you allow.
- **Connect as Read-only or Read & Write.** A read-only connection can only enable read actions.
- **Destructive actions stay off by default.** Actions such as deletes are disabled until an admin enables them.
- **Team access per account.** Restricted team members only use the accounts they are granted, with the read actions enabled on them.

## Usage Examples

```
"Show my top Bing search queries for the last 30 days"
```

```
"Are there any crawl issues on my site?"
```

```
"Submit my sitemap to Bing"
```

## Pricing

The Bing Webmaster Tools MCP server is included in every InsightfulPipe plan, together with all other MCP servers and the CLI. Plans start at $29.99/month with a 7-day free trial. See [insightfulpipe.com/pricing](https://insightfulpipe.com/pricing) for current plans.

## Ready-Made Skills and Prompts

- [Claude skills for SEO and marketing](https://insightfulpipe.com/marketing-claude-skills/marketing) — ready-made skills that run on your connected data

## Explore More MCP Servers by Insightful Pipe

Visit **[insightfulpipe.com/mcp-servers](https://insightfulpipe.com/mcp-servers)** to discover our full collection of MCP servers.

- [Google Search Console MCP](https://insightfulpipe.com/mcp-servers/google-search-console)
- [DataForSEO MCP](https://insightfulpipe.com/mcp-servers/dataforseo)
- [PageSpeed Insights MCP](https://insightfulpipe.com/mcp-servers/pagespeed)

**[View All MCP Servers →](https://insightfulpipe.com/mcp-servers)**

## Resources

- [Documentation](https://insightfulpipe.com/docs)
- [Video Tutorial](https://www.youtube.com/playlist?list=PLJNzvjxzI5Xwe__BJJLAelSF0ewO3mEFk)
- [InsightfulPipe Blog](https://insightfulpipe.com/blog)

## Support

- **Documentation**: [insightfulpipe.com/docs](https://insightfulpipe.com/docs)
- **All MCP Servers**: [insightfulpipe.com/mcp-servers](https://insightfulpipe.com/mcp-servers)
- **Email**: support@insightfulpipe.com

---

**[Insightful Pipe](https://insightfulpipe.com)** — AI-powered marketing analytics through MCP servers. [Explore all integrations →](https://insightfulpipe.com/mcp-servers)

## License

MIT License - see [LICENSE](LICENSE) for details.
