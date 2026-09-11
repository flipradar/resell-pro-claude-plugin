---
name: compare-brands
description: Compare tracked Vinted brands with Resell Pro. Use when the user asks to rank brands or assess observed sales, revenue, selling prices, seller competition, or short-term momentum.
---

# Compare brands

Use only the included Resell Pro MCP tools for market reads. Use
`compare_brands` for the comparison itself. Do not use shell commands, HTTP
clients, scraped pages, browser automation, or other side channels to obtain
market data.

Call the tool with only its supported inputs:

- `period_days`: an integer from `7` through `90`; it defaults to `30`.
- `country`: optional Vinted country code: `fr`, `de`, `es`, `it`, `uk`, `us`,
  `nl`, `be`, `pl`, `lt`, `cz`, `at`, `se`, `lu`, `pt`, `sk`, `hu`, `ro`, `dk`,
  `fi`, `hr`, `gr`, or `ie`.
- `query`: optional brand-name search, 1 to 64 characters.
- `sort`: `revenue`, `sold`, `average_price`, `median_price`, `sellers`,
  `growth`, or `brand`. It defaults to `revenue`.

Start with `marketplace_overview` with no arguments only when a broad market
context is helpful before the comparison. Otherwise call `compare_brands`
directly. Explain the period and returned `date_from`, `date_to`, currency, and
timezone. Compare only returned fields: observed items sold, revenue, average
and median selling prices, unique sellers, the two seven-day sales counts, and
sales growth percent.

Revenue is not profit or margin. Sales are items first observed as sold, not
exact Vinted transaction timestamps. Do not present results as complete
marketplace coverage, a recommendation guarantee, or a prediction of future
sales. Treat the results as tracked observations for further research.

If the result has `available: false`, state that analytics are unavailable and
do not fill gaps with estimates. If `demo.sample_data: true` is present, state
that the response is representative sample data and do not use it for real
sourcing or pricing decisions.
