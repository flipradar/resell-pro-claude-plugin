---
name: market-trends
description: Discover emerging Vinted trends with Resell Pro. Use when the user asks for tracked breakout keywords, brands, categories, or recent market momentum in a country.
---

# Market trends

Use only the `discover_market_trends` tool from the Resell Pro MCP for trend
data. Do not use shell commands, HTTP clients, scraped pages, browser
automation, or other side channels to obtain market data.

The tool accepts one optional input:

- `country`: a Vinted country code, defaulting to `fr`. Accepted values are
  `fr`, `de`, `es`, `it`, `uk`, `us`, `nl`, `be`, `pl`, `lt`, `cz`, `at`, `se`,
  `lu`, `pt`, `sk`, `hu`, `ro`, `dk`, `fi`, `hr`, `gr`, and `ie`.

State the returned country, date range, generation time, `keyword_status`, and
`snapshot_status` before interpreting the lists. Report only the returned
keywords, brands, and categories and their returned measures such as observed
sales, comparative expected-sales field, growth percent, score, breakout flag,
and unique sellers.

Treat `expected_sales_7_days` as a comparative field from the returned
snapshot, not a forecast or guarantee. Do not claim profit, complete marketplace
coverage, exact transaction timing, or future demand. Any sales figures are
tracked observations, and results should guide further research rather than a
sourcing or pricing decision by themselves.

For a promising keyword, offer a follow-up with `analyze_market_segment` using
that keyword and a supported 7-, 14-, or 30-day window. For a brand comparison,
offer `compare_brands`. If the result has `available: false`, say that analytics
are unavailable and do not invent a trend. If `demo.sample_data: true` is
present, label it representative sample data and do not use it for real
decisions.
