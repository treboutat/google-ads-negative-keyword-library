# Test: Happy path

**Scenario:** A brand-new account with no search-term data wants a starter negative library. The skill should build a protected-query list first, propose specific exclusions with deliberate match types and scope, show a blocked and a protected search for each, and separate the watch list and rejections.

## Input

- **Business:** "SMS marketing software for e-commerce brands, $99-499/mo, 14-day free trial. B2B, US."
- **Target themes:** sms marketing software, text message marketing, sms for shopify, ecommerce sms platform, klaviyo alternative.
- **Campaigns:** one Non-Brand Search campaign. No brand campaign yet. Competitor searches like "klaviyo alternative" are wanted in Non-Brand.
- No existing negatives or shared lists.

## Expected output (shape)

### Protected searches
free trial sms marketing software, sms platform reviews, tcpa compliant sms marketing, sms marketing for shopify, klaviyo alternative for sms.

### Review table (excerpt)
| Negative | Match | Scope | Blocks | Must not block | Decision |
|---|---|---|---|---|---|
| `jobs` | Phrase | Shared list → NB-Search | sms marketing jobs remote | sms marketing software | Propose |
| `salary` | Phrase | Shared list → NB-Search | sms marketing manager salary | sms marketing for shopify | Propose |
| `free sms app` | Phrase | Shared list → NB-Search | free sms app for iphone | free trial sms marketing software | Propose |
| `prank text` | Phrase | Shared list → NB-Search | prank text messages | text message marketing | Propose |
| `ringtone` | Phrase | Shared list → NB-Search | sms ringtone download | sms platform for shopify | Propose |
| `sim card` | Phrase | Shared list → NB-Search | prepaid sim card | ecommerce sms platform | Propose |
| `free` | Phrase | n/a | | free trial sms marketing software | Reject |
| `tcpa` | Phrase | n/a | | tcpa compliant sms marketing | Reject |
| `whatsapp api` | Phrase | n/a | | | Watch: does the platform offer WhatsApp? |
| `what is sms marketing` | Exact | n/a | | | Watch: research that may lead to trials |

### Competitor and brand
- "klaviyo" is not a negative: the strategy allows competitor searches in Non-Brand.
- Brand separation is deferred until a brand campaign exists, with the note that an exact `[brandname]` negative only blocks the bare brand search.

### Clean import file
Shared list name, attachment to NB-Search, six rows with explicit match types, no notes in keyword text.

### Summary
6 proposed, 3 rejected (`free`, `tcpa`, bare `sms`/`text`), 2 watch. First search-term review after the first week at planned spend.

## Pass criteria
- A protected-query list exists before any candidate is proposed, and includes buyer searches outside the keyword plan.
- Every proposed negative has a match type, a scope, a blocked search and a protected search.
- `free` and `tcpa` are rejected because they block protected searches.
- Match types are chosen per candidate; there's no blanket "phrase by default".
- No search volumes, savings estimates or target library size.
- "klaviyo" is handled by the competitor strategy, not a blanket negative.
