# Plushcap for Cursor

Research developer and AI trends and compare competitor content with Plushcap.
This plugin combines the hosted Plushcap MCP connection with a research skill
for company discovery, competitive analysis, leaderboards, and developer trends.
Its read-only tools query indexed engineering blog posts, YouTube videos, X
posts, LinkedIn activity, Hacker News attention, and historical trend metrics.
Coverage can be incomplete or delayed; check source dates and metric calculation
timestamps when interpreting results.

## Install and connect

Once the plugin is listed in the [Cursor Marketplace](https://cursor.com/marketplace),
open **Customize** in Cursor, find Plushcap, and install it at project or user
scope. This source package does not imply an approved marketplace listing.

For a local development test, copy this folder's contents, including the hidden
`.cursor-plugin/` directory, into `~/.cursor/plugins/local/plushcap/`:

```bash
mkdir -p ~/.cursor/plugins/local/plushcap
cp -R /path/to/plushcap/. ~/.cursor/plugins/local/plushcap/
```

Restart Cursor or run **Developer: Reload Window**, then open **Customize** and
confirm the Plushcap MCP server and `plushcap-consumer` skill appear. Copy the
files; Cursor skips symlinks whose targets are outside its local plugins folder.
Team administrators may need to allow local plugin imports. An installed
marketplace plugin with the same name takes precedence over a local copy.

Enable the Plushcap MCP server and use Cursor's authentication control when
prompted. Sign in to Plushcap in the browser, review the requested access and
return hostname, and authorize the connection. A Plushcap account is required;
available sources, history, and usage limits depend on your plan. Cursor manages
OAuth tokens and refresh. The server uses Streamable HTTP at
`https://mcp.plushcap.com/mcp` and supports dynamic OAuth client registration with
PKCE. No API key, static OAuth client credentials, or local server process is
required in this configuration.

## Try it

- "Use Plushcap to get Cloudflare's company profile and recent engineering posts."
- "Use Plushcap to compare Cloudflare and Vercel's content activity over the last three months."
- "Use Plushcap to research AI agent trends. Show the periods and calculation dates behind the metrics."

Invoke `/plushcap-consumer` in Cursor chat, or let Cursor select the skill for a
relevant research request. Before publishing, verify local component discovery,
browser OAuth, and a company lookup and content search in a connected Cursor
session. Package validation alone does not verify OAuth or tool execution.

## Publishing

Cursor distributes marketplace plugins through public Git repositories and
reviews submissions manually. For a single-plugin repository, put this folder's
contents at the repository root, keeping `.cursor-plugin/plugin.json`,
`mcp.json`, `skills/`, and `assets/`. A marketplace manifest is only needed for a
multi-plugin repository. Set the optional `repository` field in the plugin
manifest to the final public repository URL before submission.

Submit the repository at [Cursor's publishing form](https://cursor.com/marketplace/publish).
The form requests an organization name and unique handle, contact email,
logotype URL (square SVG or PNG with a background plate), description, public
GitHub repository, owner, and website URL. Publishing also requires accepting
Cursor's Publisher Terms. Building or installing this package does not submit
an application or deploy Plushcap.

- [Cursor plugin reference](https://cursor.com/docs/reference/plugins)
- [Cursor plugin template](https://github.com/cursor/plugin-template)
- [Cursor specification and official plugins](https://github.com/cursor/plugins)

## License and support

The configuration, skill, and documentation are licensed under the
[MIT License](LICENSE). The Plushcap icon and trademarks are excluded; see
[the asset notice](assets/NOTICE). This package license does not grant rights to
Plushcap's service or retrieved data, which remain subject to
[Plushcap's terms](https://www.plushcap.com/legal/terms-of-service) and applicable
third-party rights.

- [Setup documentation](https://www.plushcap.com/docs/mcp)
- [Support](https://www.plushcap.com/support)
- [Privacy policy](https://www.plushcap.com/legal/privacy-policy)
