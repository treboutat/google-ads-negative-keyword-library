# Negative Category Library

The full category tables and industry packs for `negative-library-starter`. This is the *generation* lens (build a library from the business). For the *negation* lens (score an existing search terms report), see `search-term-scorer/references/negative-keyword-starter-library.md`.

## Universal categories (almost every account)

| Category | Purpose | Example terms | Default match |
|---|---|---|---|
| Job / Career | Block job seekers | job, jobs, career, salary, hiring, intern, glassdoor, indeed, "job description" | Phrase |
| Education / Info | Block students/researchers | tutorial, course, "what is", definition, meaning, wiki, pdf, ebook, examples | Phrase |
| Support / Troubleshoot | Block help-seekers | "not working", error, bug, fix, troubleshoot, complaint, "customer service" | Phrase |
| Personal / Consumer | Block non-B2B intent | prank, anonymous, spy, "parental control", personal, free | Phrase |
| Negative intent / Spam | Block bad-faith searches | scam, spam, fraud, hack, phishing, unsubscribe, block | Phrase |
| Free / Piracy | Block piracy + extreme bargain hunters | free, "open source", cracked, pirated, torrent, "coupon code", nulled | Phrase |
| Regulatory / Compliance | Block regulation researchers | gdpr, "ftc complaint", tcpa, regulations (tune by industry) | Phrase |

## Industry packs

### B2B SaaS
Block: "free", "open source", "self hosted", "for students", "for nonprofits" (if out of ICP), "api documentation", "alternative to" (route to a competitor campaign, don't just negate). Keep: "pricing", "reviews", "vs" (comparison intent usually converts).

### Healthcare / regulated
Block: "home remedy", "natural cure", "free clinic", "jobs"/"travel nurse" (heavy job-seeking), symptom-only research with no service intent. **Caution:** never block terms that would stop legitimate care-seekers from a service you actually offer. Compliance review before shipping.

### Legal
Block: "diy", "do it yourself", "free legal", "law school", "salary", "jobs", "templates". Keep: "near me", "cost", "consultation".

### E-commerce
Block: "used", "refurbished" (if you sell new), "replica", "knock off", "wholesale" (if D2C), piracy/coupon terms. Keep: "reviews", "free shipping" hunters (usually convert), competitor SKUs only in non-competitor campaigns.

### Local services
Block: "diy", "rental", "used", "parts", neighboring cities/states you don't serve, "salary"/"jobs". Keep: "near me", "cost", "how much" (price intent converts).

### Communications / messaging software (example)
Block: "phone plan", "carrier", "sim card", "phone repair" (hardware), "ringtone", "emoji", "sticker" (wrong product), "whatsapp api", "telegram bot", "discord bot" (unrelated platforms), "prank text", "anonymous text", "spy" (consumer). **Trap:** never negate the platform word itself (`sms`, `text`) — it's in your target keywords.

## Match-type guidance

- **Phrase** — default for category-level blocks ("free template", "jobs"). Catches variants.
- **Exact** — brand-protection ([yourbrand] as a negative in non-brand) and surgical single-query blocks.
- **Broad** — rare; only to block any query containing all those words in any order.

## The over-blocking trap (read before shipping)

The most common starter-library mistake is a negative that swallows a target keyword. Always test each proposed negative against the target themes:
- Phrase negative `"sms"` blocks target `"sms marketing software"` → **don't add it**; use specific phrases.
- Phrase negative `"text"` blocks target `"text message marketing"` → same.
- Phrase negative `"free"` blocks target `"free trial crm"` if you run a freemium funnel → judge per business.

When a category term overlaps a target theme, narrow to the specific irrelevant phrase rather than the broad token.
