# DomainToolBelt for Claude

Domain sales, live auctions, names about to drop, trending keywords and live availability from [DomainToolBelt](https://domaintoolbelt.com), plus ready-made workflows for domain investors.

## Install

In Claude Code:

```
/plugin install domaintoolbelt --marketplace domaintoolbelt/claude-plugin
```

In Cowork, add the GitHub repository domaintoolbelt/claude-plugin as a plugin marketplace, or upload `domaintoolbelt.plugin` from [domaintoolbelt.com/mcp](https://domaintoolbelt.com/mcp).

## Commands

| Command | What you get | Credits a run |
|---|---|---|
| `/domaintoolbelt:check brewly.com` | Buy, bid or skip, a fair price range and the risks | about 7 (paid plans add 4 data queries) |
| `/domaintoolbelt:hunt 24` | Names from a prefix, suffix or word, live-checked and ranked | about 15 |
| `/domaintoolbelt:brief` | Today's auctions for your Keyword Watch words, priced against recent results | about 12 |
| `/domaintoolbelt:trends` | Rising words and names to register with them | about 20 |
| `/domaintoolbelt:alerts` | What is new in your alerts and Keyword Watches; add watches in chat | about 5 to 15 |
| `/domaintoolbelt:triage brewly.com, coffeefleet.ai, ...` | Keep or drop for up to 20 names, with availability and demand | about 2 per name |
| `/domaintoolbelt:drops coffee` | Names about to drop for a keyword, best first | about 4 |
| `/domaintoolbelt:sales coffee` | What similar names sold for and a typical price range | about 3 (paid plans: 1 to 2 data queries) |

You can also just ask, for example "is brewly.com worth $2,000?", and the right workflow runs.

## Sign in

The plugin connects to `https://mcp.domaintoolbelt.com/account`. The first call opens our Connect screen: sign in (a free account works), pick Full access or Read only, and allow. A free account has 10,000 credits a month, up to 500 a day. Paid plans add sales, history and due-diligence data. See [plans](https://domaintoolbelt.com/pricing) and the [MCP docs](https://domaintoolbelt.com/mcp).

## Privacy

[Privacy policy](https://domaintoolbelt.com/privacy-policy). The plugin itself stores nothing. Calls go to the DomainToolBelt MCP server under your account.

## Support

Use [domaintoolbelt.com/feedback](https://domaintoolbelt.com/feedback).
