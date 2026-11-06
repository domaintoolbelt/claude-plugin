---
name: alerts
description: Check what is new in DomainToolBelt alerts - unread alerts, new Keyword Watch matches and changes on watched domains - and help add watches when asked. Use when someone asks what is new, checks their alerts or watches, wants to watch a word or domain, or says /domaintoolbelt:alerts.
---

# Check my alerts

By default, show what is new since the last check. Only set up new watches when the user asks for that.

Needs a signed-in DomainToolBelt account.

## Steps: what is new (default)

1. **list_alerts** with unread_only=true. These are the new alerts for watched domains and keywords.
2. **list_keyword_watches**. For each watch, **get_keyword_watch_matches** with limit=20 and keep only rows marked new. Skip watches with nothing new. With more than 5 watches, check the 5 with alerts turned on first and say how many were left out.
3. Do not call anything else unless the user asks about one name (then use /domaintoolbelt:check).

## Answer

Start with one line: "N new alerts, M new matches across K watches", or "Nothing new since your last check."

Then group by watch or domain, newest first. For each item: the name, what happened (in auction, dropping, for sale, sold, owner or nameserver change), the price and the end time if any, and its link. Mark the 3 best with "Worth a look" and say why in a few words.

End with one line asking if they want the alerts marked as read. Call **mark_alerts_read** only after they say yes.
Do not suggest new watches unless nothing is new and they have fewer than 2 watches. Then offer it in one line.

## Adding watches (only when asked)

Needs a Full access sign-in. If a change is refused as read only, tell the user to reconnect with Full access.

1. Suggest each keyword with its endings and each domain to watch, in a short list.
2. **Wait for the user to confirm.** Then call **add_keyword_watch** or **watch_domain** for each. If a plan limit is reached, stop and say which ones were added.
3. Webhook (paid API plans only), only if they ask: **set_webhook** with their https URL, then **test_webhook**. Never show the signing secret.

Never remove a watch or a saved domain unless the user asks for that exact one.

## Rules for every answer

- If the DomainToolBelt tools are missing or a call says to sign in, stop and tell the person: run /mcp, pick domaintoolbelt, choose Authenticate, sign in with a domaintoolbelt.com account (a free one works), then ask again.
- Use only the DomainToolBelt tools (server "domaintoolbelt"). Make the fewest calls that answer the question and never repeat a call whose answer you already have.
- If a tool says it needs a paid plan, skip it, keep going with the rest, and give the domaintoolbelt.com link it returned instead.
- If a tool says credits or the daily limit ran out, stop, say so in one line and do not retry.
- Say "available" for names anyone can register, never "free". A name missing from a zone is "unconfirmed", not available, until check_availability says so.
- Estimates and price ranges are estimates, not offers. Before anyone buys, point them to the linked domaintoolbelt.com page.
- When a trend has no earlier window to compare (change is empty), give the count and say it has no comparison yet. Do not call it rising.
- Cite the domaintoolbelt.com link that each result carries.
- Short sentences, no em dashes.
