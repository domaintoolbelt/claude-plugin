---
name: brief
description: Morning auction brief for the signed-in user's Keyword Watch words - auctions ending soon priced against recent results, new drops and unread alerts. Use when someone asks for their daily brief, what to bid on today, or says /domaintoolbelt:brief.
---

# Morning auction brief

What matters today for the user's own keywords, in one screen.

Needs a signed-in DomainToolBelt account with at least one Keyword Watch. If there are none, say so and offer /domaintoolbelt:alerts to set them up.

## Steps

1. **list_keyword_watches** to get the user's keywords.
2. **list_alerts** with unread_only=true.
3. For up to 5 keywords (the user's choice, else the first 5): **get_keyword_watch_matches** with the watch id. It returns auctions, names for sale, names about to drop and recent sales for that word.
4. For each keyword that has live auctions: **search_auctions** with query = the word, ended=true, has_bids=true, sort=price, to see what similar names went for this week.

Do not make other calls. A brief costs about 12 credits.

## Answer

Start with one line: how many auctions end in the next 24 hours across all keywords, and how many unread alerts.

Then one short section per keyword, skipping keywords with nothing new:
- **Worth a look:** live auctions ending within 24 hours whose current bid is below what similar names went for. Name, current bid, ends (UTC), link.
- **About to drop:** names from the matches that drop soon.
- **For sale:** names priced well against the recent results.

Then the unread alerts in one line each. Do not mark alerts read unless the user asks.

All times in UTC.

## Running it every morning

If the user wants it daily: in Cowork, offer a scheduled task that runs /domaintoolbelt:brief at the time they pick. In Claude Code, they can run /loop or a scheduled trigger. Nothing is saved on the DomainToolBelt side.

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
