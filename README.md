# Negative Library Starter

Build a starter negative keyword library for a new Google Ads Search campaign or market from the **business itself**, before you have any search-term data. It starts from the searches you want to keep, proposes specific exclusions for intent you already know you don't want, and shows a blocked and a protected search for every candidate so nothing valuable gets caught by accident.

Pairs with [search-term-scorer](https://github.com/treboutat/google-ads-search-term-scorer): this one *seeds* the library from the business; that one *maintains* it from real search-term data once it arrives.

## Who it's for
Anyone launching a new Google Ads account or market (or inheriting one with no negatives) who doesn't want to pay for clicks they already know are irrelevant.

## Install

```bash
mkdir -p ~/.claude/skills/negative-library-starter
cp SKILL.md ~/.claude/skills/negative-library-starter/SKILL.md
cp -r references ~/.claude/skills/negative-library-starter/
```
Then say "build a starter negative library" and give it your business description, your target keyword themes and the searches you most want to stay eligible for.

## What you provide
- What the business sells, who it's for, and any free trial, free plan, consultation or template you offer.
- Your target keyword themes, plus a few buyer searches you'd hate to block.
- Brand and competitor strategy per campaign, and any existing negatives or shared lists.

## Files
- `SKILL.md`: the skill
- `references/category-library.md`: category prompts, industry notes, match-type guidance and the over-blocking traps
- `tests/`: worked example and edge cases (a negative that blocks a target keyword; a category word that is the product)

## What changed in September 2026
Categories are now prompts to check against the offer instead of universal block lists, so terms like `free`, `support`, `template`, `fraud` and `tcpa` are no longer excluded by default. Phrase match is no longer the default; each negative gets the narrowest match type that covers the intended searches. Every candidate now shows a search it blocks and a buyer search it must not block, and QA checks a protected-query list, not just the target keywords. Account-level and shared-list scope, brand separation, and PMax/Demand Gen limits are handled explicitly.

---
From [TNT Growth](https://tntgrowth.com/skills?utm_source=github&utm_campaign=treboutat). Want the full account build run for you? Start at the link.
