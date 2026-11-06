---
name: check
description: Due diligence on one domain name before buying or bidding. Use when someone asks if a domain is worth buying, what to pay or bid for it, whether it is safe to buy, or says /domaintoolbelt:check example.com.
---

# Check a domain (due diligence)

Give a buy, bid or skip verdict for one domain, with a fair price range, the main risks and links.

Input: one full domain, e.g. brewly.com. If the user gave only a name without an ending, ask which ending.

## Steps

1. **get_domain_summary** (paid) for status, for sale or in auction, last sale and registration year.
   On a free account it says it needs a paid plan: skip it.
2. **get_registration_details** for registrar, created and expiry dates, nameservers and status flags (3 credits).
   If it is not registered, run **check_availability** with just this name and say what it costs to register. Then stop: no verdict needed beyond "register it".
3. **check_name_across_tlds** with the name without its ending: how many endings it is taken in. 10+ is strong demand, 0-2 is weak.
4. Comparable sales:
   - Paid: **search_domain_sales** with the main word as query, sort=price, to get 5-10 sales of similar names.
   - Free: **search_auctions** with ended=true, has_bids=true, sort=price and the same query, for recent auction results that had real bids. Closeouts with no bids are not comparables.
5. **get_keyword_trend** for the main word: are new registrations and sales rising or falling.
6. Paid only: **get_due_diligence** for trademark matches and website history (2 data queries). Skip on free.
7. Only if steps 1-2 say it is in an auction or for sale and the summary did not give the price: **search_auctions** or **search_for_sale** with the exact name.

## Answer

Start with one line: **Buy**, **Bid up to $X**, **Make an offer up to $X** or **Skip**, and why in a few words.

Then a short table:

| | |
|---|---|
| Status | registered since YYYY, expires YYYY-MM-DD, registrar |
| Price now | asking price, current bid, or "not for sale" |
| Demand | taken in N endings, keyword trend up or down with numbers |
| Comparable sales | 3 closest, price and year |
| Risks | trademark matches, past use (spam, adult, parked), expiry |
| Fair range | $low to $high |

Base the fair range on the comparable sales, not on a guess. If there are fewer than 3 comparables, say the range is rough.
End with the domaintoolbelt.com link for the domain.

## Rules for every answer

- Use only the DomainToolBelt tools (server "domaintoolbelt"). Make the fewest calls that answer the question and never repeat a call whose answer you already have.
- If a tool says it needs a paid plan, skip it, keep going with the rest, and give the domaintoolbelt.com link it returned instead.
- If a tool says credits or the daily limit ran out, stop, say so in one line and do not retry.
- Say "available" for names anyone can register, never "free". A name missing from a zone is "unconfirmed", not available, until check_availability says so.
- Estimates and price ranges are estimates, not offers. Before anyone buys, point them to the linked domaintoolbelt.com page.
- When a trend has no earlier window to compare (change is empty), give the count and say it has no comparison yet. Do not call it rising.
- Cite the domaintoolbelt.com link that each result carries.
- Short sentences, no em dashes.
