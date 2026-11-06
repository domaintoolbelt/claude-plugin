---
name: alerts
description: Set up DomainToolBelt alerts in chat - Keyword Watches, watched domains and an alert webhook. Use when someone wants to be told about new auctions, drops or sales for a word, wants to watch a domain, or says /domaintoolbelt:alerts.
---

# Set up my alerts

Help the user set up alerts by chatting, then change their account only after they say yes.

Needs a signed-in DomainToolBelt account with Full access. A Read only sign-in cannot change anything: if a change is refused for that reason, tell the user to reconnect with Full access.

## Steps

1. Read what is there: **list_keyword_watches** and **list_watched_domains**.
2. Ask what they want to follow, in one question: words (e.g. "coffee", "ai"), specific domains they would like to own, or both.
3. Suggest the setup in a short list: each keyword with its endings, each domain to watch. Mention their plan limit if the tools return it.
4. **Wait for the user to confirm.** Then call **add_keyword_watch** for each keyword and **watch_domain** for each domain. If a limit is reached, stop and say which ones were added.
5. Webhook (paid API plans only), only if they ask: **set_webhook** with their https URL, then **test_webhook**. Never show the signing secret.

## Answer

What was added, what was already there, and what was skipped and why. Then one line: alerts show in the dashboard and go out by the channels set in their account settings, and /domaintoolbelt:brief summarises them each morning.

Never remove a watch or a saved domain unless the user asks for that exact one.

## Rules for every answer

- Use only the DomainToolBelt tools (server "domaintoolbelt"). Make the fewest calls that answer the question and never repeat a call whose answer you already have.
- If a tool says it needs a paid plan, skip it, keep going with the rest, and give the domaintoolbelt.com link it returned instead.
- If a tool says credits or the daily limit ran out, stop, say so in one line and do not retry.
- Say "available" for names anyone can register, never "free". A name missing from a zone is "unconfirmed", not available, until check_availability says so.
- Estimates and price ranges are estimates, not offers. Before anyone buys, point them to the linked domaintoolbelt.com page.
- When a trend has no earlier window to compare (change is empty), give the count and say it has no comparison yet. Do not call it rising.
- Cite the domaintoolbelt.com link that each result carries.
- Short sentences, no em dashes.
