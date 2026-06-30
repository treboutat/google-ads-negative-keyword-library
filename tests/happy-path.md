# Test — Happy path

**Scenario:** A brand-new account (no search-term data) wants a starter negative library. The skill should generate categorized negatives, assign match types, QA against the target themes, and split shared vs campaign-specific.

## Input

- **Business:** "SMS marketing software for e-commerce brands, $99-499/mo. B2B, US."
- **Target themes:** sms marketing software, text message marketing, sms for shopify, ecommerce sms platform, klaviyo alternative.
- No brand or competitor campaign yet.

## Expected output (shape)

### Shared library negatives (excerpt)
| Keyword | Match | Category | Notes |
|---|---|---|---|
| jobs | Phrase | Job/Career | |
| salary | Phrase | Job/Career | |
| "what is sms marketing" | Phrase | Education/Info | Researcher |
| "free sms" | Phrase | Free/Piracy | Non-buyer |
| "bulk sms free" | Phrase | Free/Piracy | |
| "prank text" | Phrase | Personal/Consumer | Consumer intent |
| "anonymous text" | Phrase | Personal/Consumer | |
| "whatsapp api" | Phrase | Unrelated platforms | Different platform |
| "telegram bot" | Phrase | Unrelated platforms | |
| ringtone | Phrase | Wrong product | |
| "sim card" | Phrase | Carrier/Hardware | Consumer device |

### Campaign-specific
- None yet (no brand/competitor campaign). Note: when a brand campaign launches, add the brand term as an exact negative in non-brand.

### QA flags
- **Did NOT add** bare `sms` or `text` (phrase) — both would block target themes ("sms marketing software", "text message marketing").
- **Did NOT negate** "klaviyo" — it's a competitor in a target theme ("klaviyo alternative"); route to a competitor campaign, don't blanket-negate.

### Summary
- ~11 shared-library negatives across 6 categories.
- 0 campaign-specific.
- Borderline left out: "cheap" (could still convert at a $99 entry price).

## Pass criteria
- Negatives are categorized and have match types.
- No negative blocks any of the 5 target themes (the `sms`/`text` trap is caught).
- "klaviyo" is handled as a competitor opportunity, not a blanket negative.
- Borderline terms deliberately omitted are listed with a reason.
