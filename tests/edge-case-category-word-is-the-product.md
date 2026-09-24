# Test: Edge case, the category word is the product

**Scenario:** A generic exclusion pack contains a word that looks like bad-faith intent, but it describes what the business sells. A keyword-overlap check passes, so the skill has to catch it through the protected-query list.

## Input

- **Business:** "Fraud-prevention software for online retailers. Scores card-not-present transactions and blocks chargebacks."
- **Target themes:** payment risk platform, chargeback prevention software, ecommerce transaction screening.
- **Proposed from a generic pack:** `fraud`, `scam`, `hack` (phrase).

## The trap

None of the target themes contains "fraud", so `fraud` passes a simple keyword-overlap check. But `fraud detection software` and `ecommerce fraud prevention` are high-value buyer searches.

## Expected behavior

- The protected-query list includes buyer searches outside the keyword plan: `fraud detection software`, `ecommerce fraud prevention`, `card fraud prevention for shopify`.
- `fraud` (phrase) is **rejected**: it blocks `fraud detection software`.
- `scam` goes on the **watch list**: "is this store a scam" is consumer intent, but "scam prevention for online stores" may be a buyer. Decide from real search-term data instead of a bare launch-day negative.
- `hack` is **narrowed** to the actual unwanted intent, e.g. phrase `how to hack` (blocks "how to hack a credit card"), after checking it doesn't block a buyer search like "prevent account takeover attacks".
- The output explains that a concerning word isn't evidence of a bad customer when it describes the product category.

## Pass criteria
- `fraud` isn't proposed as a negative.
- The rejection cites a protected buyer search that isn't in the keyword plan.
- Remaining candidates are narrowed to specific phrases or held on the watch list, each proposed one with a blocked and a protected example.
