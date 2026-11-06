---
name: drops
description: Find names about to drop (expired and heading to deletion) for a keyword, best first. Use when someone asks what is dropping, expiring names to catch or backorder, or says /domaintoolbelt:drops coffee.
---

# Names about to drop

Find expired names for a keyword that are heading toward deletion, and pick the best to catch or backorder.

Input: a keyword, e.g. "coffee". Optional: an ending (default com), "short" (max 10 letters) or a pattern such as LLL. With no keyword, ask for one, or use a pattern if they gave one.

## Steps

1. **list_expiring_domains** with query set to the keyword, tld (default "com"), no_hyphens=true, no_numbers=true and limit=25. Add max_length=10 if they asked for short names, or pattern if they gave one.
2. If fewer than 5 rows come back, run it once more without the tld filter, and say so.
3. For the best 3 only: **check_name_across_tlds** with the name without its ending, for demand.
4. Nothing else. For a deep look at one name, point to /domaintoolbelt:check.

## Answer

Start with one line: how many names and the soonest drop date.

Then the best 5-10, best first, as a short list. For each: the name, the estimated days to drop, the phase (grace, redemption or pending), its age if given, taken in N endings (best 3 only), why in a few words, and the domaintoolbelt.com link.

Say once that drop days are estimates, and that the owner can still renew during grace and redemption. To catch a name, use a backorder service before the drop day.

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
