---
name: hunt
description: Find good domain names to register or buy from a prefix, suffix or theme, live-check them and rank them. Use when someone wants name ideas like 24 or 365 names, names with a word, or says /domaintoolbelt:hunt.
---

# Hunt for names

Find names the user can get now, check the best ones live and rank them.

Input: a prefix or suffix (e.g. "24", "365", "get", "ly"), or a theme word (e.g. "coffee"). Optional: ending (default .com), budget, max length. If the input is unclear, take the most likely reading and say which one you used.

## Steps

1. If there is a theme word: **get_keyword_trend** on it, to know if demand is rising.
2. Collect candidates:
   - Prefix or suffix: **build_names** with affix and position (prefix or suffix) and the ending. Needs a signed-in account; if it is refused, skip it.
   - Theme word: **find_available_names** with query = the word and the ending, for names we saw drop that anyone can register now.
   - **search_for_sale** with the word or affix and buy_now=true, plus max_price when the user gave a budget, for good names with an asking price.
3. Pick the best 10 names you would register yourself: short, easy to say and spell, real words, no hyphens or digit mixes unless the affix is a number, no trademarks of big brands.
4. **check_availability** with those 10 names in one call (1 credit per name). Do not check more than 10 unless the user asks; there is a daily limit of names.
5. **check_name_across_tlds** for the top 3 available names, to show demand in other endings.

## Answer

Two short lists:

**Available to register now** (from step 4), best first: name, price to register and renew, one reason it is good, endings it is taken in.

**For sale** (from step 2), best first: name, asking price, marketplace link.

Leave out names step 4 found taken. If nothing good is left, say so and suggest another affix or word.

## Rules for every answer

- Use only the DomainToolBelt tools (server "domaintoolbelt"). Make the fewest calls that answer the question and never repeat a call whose answer you already have.
- If a tool says it needs a paid plan, skip it, keep going with the rest, and give the domaintoolbelt.com link it returned instead.
- If a tool says credits or the daily limit ran out, stop, say so in one line and do not retry.
- Say "available" for names anyone can register, never "free". A name missing from a zone is "unconfirmed", not available, until check_availability says so.
- Estimates and price ranges are estimates, not offers. Before anyone buys, point them to the linked domaintoolbelt.com page.
- When a trend has no earlier window to compare (change is empty), give the count and say it has no comparison yet. Do not call it rising.
- Cite the domaintoolbelt.com link that each result carries.
- Short sentences, no em dashes.
