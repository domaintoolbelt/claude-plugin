---
name: triage
description: Triage a list of domain names - availability, demand and a keep or drop verdict for each. Use when someone pastes several domains to check, asks which names in a list are worth registering or renewing, or says /domaintoolbelt:triage.
---

# Triage a list of names

Give a quick keep or drop verdict for each name in a list of up to 20 full domains (e.g. brewly.com, coffeefleet.ai).

If there are more than 20 names, do the first 20 and say how many were left out. If a name has no ending, ask which ending once for all of them.

## Steps

1. **check_availability** with all the names in one call (up to 25, 1 credit per name). This shows available, registered or for sale, with prices.
2. **check_name_across_tlds** for each different name without its ending, to see in how many endings it is taken. Skip this for names that are clearly weak (hyphens plus digits, or over 20 letters).
3. Nothing else. For a deep look at one name, point to /domaintoolbelt:check.

## Verdict per name

- **Register** or **Keep**: short or a clear word or brand, taken in 10+ endings, and fair registration and renewal prices.
- **Maybe**: taken in 3-9 endings, or a good name with a high renewal price.
- **Drop**: taken in 0-2 endings, long, hyphens or digits, or a premium price with weak demand.
- Registered, not for sale: say "taken" with no verdict. Registered and for sale: give the asking price.

## Answer

Start with one line, e.g. "Keep 4, maybe 3, drop 10, taken 3 (20 names)."

Then one table, best first:

| Name | Status | Price (reg / renew) | Taken in | Verdict | Why |
|---|---|---|---|---|---|

Keep "Why" to a few words. Give each name's domaintoolbelt.com link.

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
