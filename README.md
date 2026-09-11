# Resell Pro for Claude Code, Cursor, and Gemini CLI

Resell Pro connects compatible AI clients to read-only, observed Vinted market
analytics. Use it to get a market overview, compare brands, research keyword
niches, and find recent country-specific trends.

## Install and connect

| Client | Package entry point | Setup |
| --- | --- | --- |
| Claude Code and Cowork | `.claude-plugin/plugin.json` | Install from Claude's plugin directory once listed. |
| Cursor | `.cursor-plugin/plugin.json` | Install from Cursor's plugin marketplace once listed, or load a local clone for development. |
| Gemini CLI | `gemini-extension.json` | Install the public GitHub repository as an extension. |
| Agent Plugins clients | `plugin.json` and `mcp.json` | Install using the client's Agent Plugins workflow. |

### Claude Code and Cowork

Once this plugin is listed in the Anthropic directory, install **Resell Pro**
from Claude's plugin directory. The plugin automatically configures the remote
MCP endpoint `https://resellpro.com/mcp`.

When Claude starts the connection, complete the normal OAuth flow in your
browser. Sign in directly with Resell Pro and review the consent screen. Do not
paste a password, API key, access token, cookie, or OAuth code into Claude or
into a configuration file.

For local development, validate the extracted plugin directory and load it
directly:

```sh
claude plugin validate /path/to/resell-pro-claude-plugin --strict
claude --plugin-dir /path/to/resell-pro-claude-plugin
```

Claude Code 2.1.128 or newer can also load the release ZIP directly:

```sh
claude --plugin-dir /path/to/resell-pro-claude-plugin-1.0.1.zip
```

### Cursor

Install **Resell Pro** from the Cursor Marketplace once it is listed. For local
development, link a checkout into Cursor's local plugin directory, then reload
the Cursor window and confirm the plugin in **Customize**:

```sh
mkdir -p ~/.cursor/plugins/local
ln -s /path/to/resell-pro-claude-plugin ~/.cursor/plugins/local/resell-pro
```

Cursor loads the included skills and connects to `https://resellpro.com/mcp`.
Complete the normal browser OAuth flow when prompted.

### Gemini CLI

Install the extension from this public repository:

```sh
gemini extensions install https://github.com/flipradar/resell-pro-claude-plugin
```

Restart Gemini CLI after installation. If authentication is needed, run
`/mcp auth resell-pro` inside Gemini CLI and complete the normal browser OAuth
flow.

## Supported MCP tools

| Tool | Inputs | Use it for |
| --- | --- | --- |
| `marketplace_overview` | No arguments | Last 30 days of observed sales, leading tracked brands, and categories. |
| `compare_brands` | Optional `period_days` (7–90), `country`, `query`, `sort` | Brand-level observed sales, revenue, prices, unique sellers, and short-term momentum. |
| `analyze_market_segment` | `keywords`, optional `country`, optional `period_days` (7, 14, or 30) | Keyword-niche observed sales, sold prices, time to sell, active listings, and sell-through. |
| `discover_market_trends` | Optional `country` | Tracked breakout keywords, brands, and categories for one country. |

The included skills are `/resell-pro:niche-research`,
`/resell-pro:compare-brands`, and `/resell-pro:market-trends`.

## Interpretation and limits

Results reflect tracked Resell Pro observations, not complete Vinted marketplace
coverage. A sale means an item first observed as sold; it is not an exact Vinted
transaction timestamp. Revenue is not profit, and no result guarantees a sale,
margin, price, or demand outcome.

If a tool returns `available: false`, analytics are unavailable and the plugin
does not estimate missing data. If a response includes `demo.sample_data: true`,
it is representative sample data only and must not guide real sourcing or
pricing decisions.

This plugin contains no hooks, scripts, embedded secrets, or telemetry code.

## Help and policies

- Support: [hello@resellpro.com](mailto:hello@resellpro.com)
- Documentation: [Resell Pro MCP](https://resellpro.com/tools/mcp)
- Privacy: [Resell Pro MCP privacy notice](https://resellpro.com/mcp/privacy)
- Terms: [Resell Pro MCP terms](https://resellpro.com/mcp/terms)

## License

This plugin source is licensed under the [MIT License](LICENSE). The license
does not grant access to, or rights in, the Resell Pro service, market data, or
Resell Pro brand.
