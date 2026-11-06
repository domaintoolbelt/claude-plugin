---
name: sales
description: Price research - what names like a keyword or domain sold for, with a typical price range. Use when someone asks what similar names sold for, how much to bid or ask, comparable sales, or says /domaintoolbelt:sales coffee.
---

# What did names like this sell for

Find comparable sales for a keyword or a domain and give a typical price range.

Input: a keyword (e.g. "coffee") or a full domain (use its main word as the keyword and its ending as the tld). Optional: an ending and a time window.

## Steps

1. **search_domain_sales** (paid) with query set to the keyword, sort=price and limit=25. Add tld if they gave one. Then once more with sort=date for the latest sales, only if the first call returned 10 or more rows.
2. On a free account it says it needs a paid plan. Then use **search_auctions** with ended=true, has_bids=true, sort=price and the same query instead. Say these are auction results, not reported sales, and give the domaintoolbelt.com link for full sales.
3. **get_keyword_trend** for the keyword: sales count, median and top price over 12 months. The sales change_pct is the change in the word's share of all sales, not in the count. Report the counts and do not call it rising or falling from change_pct alone.

## Answer

Start with one line: typical range $low to $high, median $X, from N sales.

Then the 5-10 closest sales as a short list: name, price, date, venue and link. Leave out outliers (over 10x the median) from the range, but name the biggest one.

If there are fewer than 5 sales, say the range is rough. Estimates are not offers.

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
