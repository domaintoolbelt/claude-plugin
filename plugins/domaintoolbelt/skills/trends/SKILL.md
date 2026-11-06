---
name: trends
description: Find rising keywords in new domain registrations and names to register with them this week. Use when someone asks what is trending in domains, what words are hot, what to register now, or says /domaintoolbelt:trends.
---

# Trend scout

Which words are rising, and names with them the user can register now.

Input: optional ending (default .com) and window (default 7 days).

## Steps

1. **get_trending_keywords** with window_days (default 7).
2. Pick the 5 strongest words: real words a business would use, not brand names or one-off spam bursts.
3. **get_keyword_trend** on each of the 5: new registrations last 90 days vs the 90 before, and sales.
4. For the top 3 by trend: **find_available_names** with query = the word and the ending.
   For a short word that works as an affix (e.g. "ai", "bot", "pay"), **build_names** with it as affix instead.
5. Pick the best 10 names across the 3 words and run **check_availability** once with all 10.

About 20 credits a run.

## Answer

A table of the 5 words: word, new registrations (90 days, % change), sales in 12 months (count, median price), rising or falling.

Then **Register this week**: the available names from step 5, best first, with the price to register and the word they ride on.

Say it in plain words when a trend is small or noisy.

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
