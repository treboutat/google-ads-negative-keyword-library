---
name: negative-library-starter
description: Build a comprehensive, categorized starter negative keyword library for a Google Ads account from the business and industry — before there's any search-term data. Use when a user says "build negatives", "negative keyword list", "starter negatives", "negative library", "new account negatives", or is launching a brand-new account with no search-term history yet. Outputs categorized negatives with match types, split into a shared library and campaign-specific negatives, QA'd against the target keywords so nothing relevant gets blocked.
---

# Negative Library Starter

Generate a categorized negative keyword library from what the business sells and who it serves — no search-term data required. This is what you build on day one of a new account, before there's a search terms report to mine. Once real query data accrues, switch to `/search-term-scorer` to refine the library from actual searches.

## The principle

Negatives prevent wasted spend by blocking irrelevant searches before they ever cost you. A starter library catches the universally-bad terms (jobs, free, DIY, support) and the industry-specific traps, so a new account doesn't burn its first month learning what you already know.

But every negative is a potential customer you'll never reach. Be comprehensive on clearly-irrelevant terms and conservative on anything borderline. When in doubt, leave it out and let the search term report tell you later.

## Inputs

Required:
- **Business name + product/service description** — what it sells, who it's for
- **Target keyword themes** — the terms you *do* want to rank for, so negatives don't block them. (Without these you can't QA against over-blocking; ask for them.)

Strongly recommended:
- Industry vertical (healthcare, SaaS, e-commerce, local services, etc.)
- Whether **brand** terms should be negative in non-brand campaigns
- Whether **competitor** terms should be negative in non-brand campaigns

Optional:
- Existing negative lists to build on
- Budget level (tighter budgets need more aggressive negatives)

## Workflow

1. **Collect inputs.** If target keyword themes are missing, ask — you can't QA against blocking without them.
2. **Generate negatives by category.** Work through the standard categories below; expand per industry using `references/category-library.md`.
3. **Assign match types.** Phrase by default; exact for brand-protection; broad only in rare deliberate cases.
4. **Separate shared-library from campaign-specific** negatives (brand-in-non-brand, competitor-in-non-brand).
5. **QA against the target keywords.** No negative may block a target term.
6. **Output** the categorized library + a summary.

## Categories (core)

| Category | Purpose | Examples |
|----------|---------|----------|
| Job / Career | Block job seekers | job, jobs, career, salary, hiring, intern, glassdoor |
| Education / Info | Block students and researchers | tutorial, course, what is, definition, wiki, pdf, ebook |
| Support / Troubleshoot | Block help-seekers, not buyers | not working, error, bug, fix, troubleshoot, complaint |
| Personal / Consumer | Block non-B2B / consumer intent | prank, anonymous, spy, parental control, personal |
| Negative intent / Spam | Block bad-faith searches | scam, spam, fraud, hack, phishing, unsubscribe |
| Free / Piracy | Block piracy and extreme bargain hunters | free, open source, cracked, pirated, torrent, coupon code |
| Irrelevant services | Block adjacent-but-unrelated services | (industry-specific — see references) |
| Wrong product / device | Block unrelated product searches | (industry-specific — see references) |
| Unrelated platforms | Block competing platforms not in scope | (industry-specific — see references) |
| Regulatory / Compliance | Block info-seekers researching regulations | gdpr, ftc complaint, regulations (adjust by industry) |

Industry-specific category packs (B2B SaaS, healthcare, legal, e-commerce, local services) live in `references/category-library.md`.

## Match types

| Match type | When to use |
|------------|-------------|
| Phrase | Default for most negatives. Blocks the phrase and close variants. |
| Exact | Brand-protection (block the exact brand term in a non-brand campaign). |
| Broad | Rarely. Only to block any query containing all those words in any order. |

Default to phrase match for the shared library.

## Separate campaign-specific negatives

Some negatives apply only to specific campaigns — flag these separately:
- **Brand terms negative in Non-Brand** — stops non-brand from cannibalizing brand traffic.
- **Competitor terms negative in Non-Brand** — only if a separate Competitors campaign exists.

## QA check (before delivery)

- [ ] No negative blocks a term in the target keyword themes
- [ ] Every negative has a match type assigned
- [ ] Categories organized logically
- [ ] Campaign-specific negatives clearly separated from the shared library
- [ ] Comprehensive but not over-aggressive (no borderline-relevant terms negated)
- [ ] No duplicates

## Output

Format: a table — **Keyword | Match type | Category | Notes** — in two sections:
- **Shared library negatives** (apply to all campaigns)
- **Campaign-specific negatives** (with the campaign noted)

Always close with a summary: total negatives by category, any campaign-specific negatives and where they apply, and any borderline terms you deliberately left out (and why).

## Worked example

**Business:** "SMS marketing software for e-commerce brands, $99-499/mo."
**Target themes:** sms marketing software, text message marketing, sms for shopify, ecommerce sms platform.

**Generated (excerpt):**

| Keyword | Match | Category | Notes |
|---|---|---|---|
| jobs | Phrase | Job/Career | Block job seekers |
| salary | Phrase | Job/Career | |
| "what is sms marketing" | Phrase | Education/Info | Researcher intent |
| "free sms" | Phrase | Free/Piracy | Bargain/non-buyer |
| "prank text" | Phrase | Personal/Consumer | Consumer, not B2B |
| "whatsapp api" | Phrase | Unrelated platforms | Different platform |
| ringtone | Phrase | Wrong product | Unrelated to the offer |

**QA flag (the trap):** do **not** add bare `sms` or `text` as a phrase/broad negative — it would block "sms marketing software" and "text message marketing", both target themes. Use the specific phrases instead.

**Summary:** 7 shared-library negatives across 6 categories; 0 campaign-specific (no brand/competitor campaign yet). Borderline left out: "cheap" (price-sensitive but could still convert at $99 entry).

## Hard rules

- **Don't over-block.** When in doubt, leave it out; the search term report will catch it later (`/search-term-scorer`).
- **Cross-check every negative against the target keywords.** A negative like phrase-match "sms" blocks "sms marketing software" — a target term. This is the single most common starter-library mistake.
- **Shared library first, campaign-specific second.** Most negatives apply universally; only use campaign-specific for cross-campaign traffic steering.
- **Default phrase match** for the shared library.

## Related skills

- **`/search-term-scorer`** — Once the account has real search-term data, refine the library from actual queries (this skill seeds it; that skill tunes it).
- **`/ads-audit`** — Checks 21-23 cover negative-list coverage; this skill builds what those checks look for.

## Tone

Operational, accountant-who-runs-Google-Ads. The output is a paste-ready library, not an essay. Comprehensive on clearly-bad terms, conservative on borderline ones.
