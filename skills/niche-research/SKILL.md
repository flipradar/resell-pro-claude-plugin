---
name: niche-research
description: Research a Vinted product niche with Resell Pro observed market data. Use when the user asks about demand, sold prices, sell-through, time to sell, active listings, or whether a keyword niche merits further research.
---

# Niche research

Use only the `analyze_market_segment` tool from the Resell Pro MCP for keyword
segment data. Do not use shell commands, HTTP clients, scraped pages, browser
automation, or other side channels to obtain market data.

Ask for keywords when they are missing. Send exactly these supported inputs:

- `keywords`: required plain-text product, niche, or style phrase, 2 to 64 characters.
- `country`: Vinted country code. It defaults to `fr`; accepted values are `fr`,
  `de`, `es`, `it`, `uk`, `us`, `nl`, `be`, `pl`, `lt`, `cz`, `at`, `se`, `lu`,
  `pt`, `sk`, `hu`, `ro`, `dk`, `fi`, `hr`, `gr`, and `ie`.
- `period_days`: `7`, `14`, or `30` complete days; it defaults to `30`.

Use the returned dates, country, currency, and timezone in the answer. Report
only the metrics the tool returns: observed items sold, median sold price,
median days to sell, sold-price buckets, active listings, items posted,
items posted and sold, and sell-through. Define sell-through accurately as the
share of items first listed in the window that were observed sold in that same
window.

Do not claim revenue, profit, margins, seller competition, complete marketplace
coverage, exact transaction timing, or a future outcome. Sales are items first
observed as sold, not exact Vinted transaction timestamps. Treat results as
tracked observations that support further research, not a sourcing or pricing
guarantee.

If the response has `available: false`, say that analytics are unavailable and
do not estimate missing values. If the tool says the segment is too broad,
narrow the keywords, keep one country, or retry with the 7-day window. If a
response contains `demo.sample_data: true`, identify it as representative sample
data and do not use it for real sourcing or pricing decisions.
