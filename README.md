# Negative Library Starter

Build a categorized starter negative keyword library for a Google Ads account from the **business and industry** — before you have any search-term data. It's what you set up on day one of a new account so it doesn't burn its first month learning what you already know.

Pairs with [search-term-scorer](https://github.com/treboutat/google-ads-search-term-scorer): this one *seeds* the negative library from first principles; that one *tunes* it from real search-term data once it accrues.

## Who it's for
Anyone launching a new Google Ads account (or inheriting one with no negatives) who wants a comprehensive starting block-list without waiting a month for the search terms report to fill up.

## Install

```bash
mkdir -p ~/.claude/skills/negative-library-starter
cp SKILL.md ~/.claude/skills/negative-library-starter/SKILL.md
cp -r references ~/.claude/skills/negative-library-starter/
```
Then say "build a starter negative library" and give it your business description + the keyword themes you *do* want to rank for.

## What you provide
- What the business sells and who it's for.
- Your target keyword themes (so the QA step can make sure no negative blocks them).
- Optional: industry, brand/competitor handling, existing negatives.

## Files
- `SKILL.md` — the skill
- `references/category-library.md` — full category tables + industry packs (SaaS, healthcare, legal, e-com, local) + the over-blocking trap
- `tests/` — worked example + the "negative blocks a target keyword" edge case

---
From [TNT Growth](https://tntgrowth.com/skills?utm_source=github&utm_campaign=treboutat). Want the full account build run for you? Start at the link.
