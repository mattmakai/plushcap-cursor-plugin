---
name: plushcap-consumer
description: Research developer-facing companies, compare competitors' content, inspect leaderboards, and analyze developer and AI trends using the Plushcap MCP connection.
---

# Plushcap research

Use the connected Plushcap MCP tools to answer research questions. Ground
conclusions in retrieved data and include relevant source, company, trend, or
leaderboard links. Plushcap tools retrieve indexed data; they do not publish
content or start collection jobs.

## Company discovery

1. Use `list_companies` to find valid company slugs. For a supplied website,
   `detect_company_from_url` can identify an indexed company. Do not guess slugs.
2. Use `get_company` to inspect the company's profile and available sources.
3. Search engineering posts and inspect YouTube, X, LinkedIn, or Hacker News
   results relevant to the question. Keep queries small and paginated; request
   full article text only when needed.

## Competitive analysis

1. Identify companies or discover a competitive space with
   `list_competitive_spaces` and `get_competitive_space`.
2. Use `compare_companies` or `get_competitive_space_comparison` for shared
   metrics and time windows. For content research, use
   `research_company_youtube_content` or `research_company_x_content` when
   appropriate to retrieve target activity and peer context.
3. Separate observed activity from interpretations of strategy. Note missing or
   uneven coverage and distinguish the requested period from all-time totals.

## Leaderboards

Use `get_blog_leaderboard` or `get_youtube_leaderboard` for the supported metric.
Report the time window, metric, and ranking criterion before naming leaders.
Hacker News tools provide post activity and attention; do not present those
results as an unsupported company ranking. Link to
[Plushcap leaderboards](https://www.plushcap.com/leaderboards) when useful.

## Developer trends

Discover topics with `get_trend_topics`, then use trend summaries, topic history,
and monthly or yearly metrics as appropriate. Inspect the returned periods and
calculation timestamps before describing a result as current. Compare consistent
windows and distinguish a short spike from sustained growth. Treat empty results
as a coverage limitation, not proof that a company or topic has no activity.
Trend report tools retrieve authored reports; check their dates and access level
before relying on them. Link to [developer trends](https://www.plushcap.com/trends)
and the underlying sources.

## Authentication and limits

This plugin connects to `https://mcp.plushcap.com/mcp` using Plushcap OAuth.
When Cursor requests authentication, have the user follow its browser sign-in
flow, sign in to Plushcap, review the requested access and callback hostname,
and authorize the connection. Open Customize, find this plugin's Plushcap MCP
server, and follow its authentication prompts when needed. Let Cursor manage
access tokens and automatic refresh; do not ask users to paste API keys, OAuth
codes, client secrets, or tokens into chat or configuration files.

If the connection is unavailable, explain how to authenticate and resume once it
is connected. If a request is denied by plan or quota, explain the returned limit
instead of inventing results or switching credentials. Available sources,
history, and usage limits depend on the user's Plushcap plan.

## References

- [MCP setup and OAuth](https://www.plushcap.com/docs/mcp)
- [Companies](https://www.plushcap.com/docs/companies)
- [Blog posts](https://www.plushcap.com/docs/blog-posts)
- [Competitive intelligence](https://www.plushcap.com/docs/competitive)
- [Developer trends](https://www.plushcap.com/docs/trends)
