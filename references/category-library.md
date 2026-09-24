# Negative Category Library

Category prompts and industry notes for `negative-library-starter`. Every entry here is a question to answer against the actual offer, not a term to paste. For reviewing real search terms once data exists, see [search-term-scorer](https://github.com/treboutat/google-ads-search-term-scorer).

## Category prompts

| Category | Words that often appear | Check before excluding |
|---|---|---|
| Employment | jobs, careers, salary, hiring, intern, glassdoor, indeed, "job description" | Does the campaign serve anyone looking for work or salary data? Hiring, recruiting, HR and payroll-compliance products may need these words. |
| Education or DIY | tutorial, course, "what is", definition, examples, template, pdf, "how to" | Is this learning intent outside the goal, or part of how buyers research? Templates and how-to searches often precede a purchase. |
| Support or troubleshooting | login, support, "not working", error, fix, "customer service" | Is the searcher an existing user of someone else's product, or a buyer? Support software, repair and replacement businesses sell through problem searches. Brand campaigns may need login and support traffic handled deliberately. |
| Free, discounts, piracy | free, cheap, coupon, "promo code", crack, torrent, nulled, "open source" | Does the business offer a trial, free plan, consultation, coupon or free shipping? Separate an unwanted free substitute or pirated product from a real offer. |
| Wrong product or audience | industry-specific | What does the business actually not sell, and which use cases can't it serve? Confirm the limitation instead of assuming it. |
| Fraud, privacy, compliance | fraud, spam, scam, hack, gdpr, tcpa, hipaa, regulations | Could this be the product category? Fraud-prevention, security and compliance products sell on these words. Never infer that a concerning word means a bad customer. |
| Other platforms | competing or adjacent platform names | Does the business integrate with, migrate from, or compete against it? Record the competitor strategy first. |

## Industry notes

### B2B SaaS
Check before excluding "free" (trials, freemium), "open source" and "self hosted" (may be a real alternative you compete with), "for students" and "for nonprofits" (confirm they're out of ICP), "api documentation" (can be a technical buyer), "alternative to" and "vs" (competitor strategy decides). "Pricing" and "reviews" are usually buyer intent.

### Healthcare and regulated services
Verify the actual service, eligibility and payer rules before excluding condition, symptom, cost, insurance or place terms. A research-looking search can come from someone seeking care. Employment terms ("travel nurse", "jobs") are common here; check that none of them describe a service you offer. Get a compliance review before shipping.

### Legal
Check "free legal", "consultation", "cost" and "near me" against the actual intake model; free consultations make "free" a buyer word. "Law school", "salary" and "jobs" are usually employment or education intent.

### E-commerce
Check "used", "refurbished", "wholesale" and "replica" against what you actually sell. "Reviews", "free shipping", coupons and competitor product names can all be buyer intent; decide competitor routing deliberately.

### Local services
Check "diy", "rental", "parts" and "repair" against the services offered. Exclude locations you don't serve through location settings or specific negatives, and confirm service areas first. "Cost", "how much" and "near me" are usually buyer intent.

### Messaging software (example)
Candidates such as "phone plan", "sim card", "ringtone", "prank text" and "anonymous text" usually describe consumer products. Check "whatsapp api", "telegram bot" and "discord bot" against whether the platform supports those channels. Keep compliance words like "tcpa compliant" eligible; for an SMS platform they're a buying criterion. Never negate the platform word itself (`sms`, `text`).

## Match-type guidance

- **Exact** for an isolated unwanted query.
- **Phrase** when the whole phrase represents unwanted intent across the affected campaigns.
- **Broad** when the combination is unwanted in any word order.
- Negatives don't match synonyms or singular/plural forms, so check each form you mean to cover.
- A one-word phrase negative blocks as much as the same one-word broad negative.
- Brand: an exact `[brandname]` negative blocks only the bare brand query. Broader brand separation needs brand lists or a scoped negative set.

## The over-blocking traps (read before shipping)

1. **A negative swallows a target keyword.** Phrase `"sms"` blocks "sms marketing software"; phrase `"text"` blocks "text message marketing". Narrow to the specific irrelevant phrase ("prank text", "free sms app").
2. **A negative blocks the offer.** Phrase `"free"` blocks "free trial sms marketing software" when the business advertises a trial.
3. **A negative blocks a buyer search that isn't in the keyword plan.** A fraud-prevention product whose keywords say "payment risk platform" passes a keyword-overlap check against a generic `fraud` negative, but `fraud detection software` is valuable demand. Test against the protected-query list, not just the keywords.
4. **Two reasonable lists combine into a bad one.** Check the combined effect of account, shared-list, campaign and ad-group negatives together.
