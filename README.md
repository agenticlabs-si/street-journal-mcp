# Street Journal MCP server

Daily and weekly AI briefings on the stocks you hold, plus per-ticker news with sources, in Claude, ChatGPT or any MCP client.

[Street Journal](https://streetjournal.si) writes a short briefing on your portfolio every morning at 07:00 in your timezone and a weekly recap every Saturday, in your language, with every summary linked to its sources. This hosted MCP server lets your AI assistant read those briefings and ask about your holdings in plain words.

This repository documents the hosted server. The server itself is closed source.

## Connect

| | |
| --- | --- |
| URL | `https://streetjournal.si/mcp` |
| Transport | Streamable HTTP |
| Auth | OAuth 2.1 (dynamic client registration and client ID metadata documents) |
| Registry name | `si.streetjournal/street-journal` |

**Claude:** Settings → Connectors → Add custom connector, paste the URL, then sign in with your Street Journal account.

**Claude Code:**

```sh
claude mcp add --transport http street-journal https://streetjournal.si/mcp
```

**Other clients:** add a remote (Streamable HTTP) server with the URL above. The client opens the Street Journal sign-in page on first use.

## Tools

| Tool | What it returns |
| --- | --- |
| `list_reports` | Your daily and weekly reports, newest first |
| `get_report` | One report as markdown, by id |
| `get_latest_report` | The newest daily or weekly report as markdown |
| `list_ticker_summaries` | The latest news summary for each ticker you hold, with sentiment and sources |
| `get_public_report` | The free Magnificent 7 report (English, Spanish or German), latest or by date |

## Example prompts

- What moved my portfolio this week?
- Summarise today's report in three bullets.
- Any news on NVDA I should know about?

## Pricing

MCP access needs an active subscription: €4.99/week or €99/year, 7 days free. See [pricing](https://streetjournal.si/pricing).

## Links

- [Website](https://streetjournal.si)
- [Privacy policy](https://streetjournal.si/privacy)
- [Terms of service](https://streetjournal.si/terms)
- [X](https://x.com/streetjournalsi)

## Support

Open an issue in this repository.
