---
name: negative-library-starter
description: Build a starter negative keyword library for a new Google Ads Search campaign or market from the business itself, before any search-term data exists. Use when a user says "build negatives", "negative keyword list", "starter negatives", "negative library", "new account negatives", or is launching a new account or market with no search-term history. Starts from the searches worth protecting, proposes specific exclusions with deliberate match types and scope, shows a blocked and a protected search for every candidate, and delivers an annotated review table, a watch list and a clean import file.
---

# Negative Library Starter

Block searches the business already knows it doesn't want. Protect the searches that could produce the customers the campaign is meant to acquire.

You don't need to buy irrelevant clicks to prove they're irrelevant. You do need to know what the business sells, which intent it wants and exactly what each negative will exclude.

Use this before launching a new Search campaign or entering a new market. Once real query data arrives, [`search-term-scorer`](https://github.com/treboutat/google-ads-search-term-scorer) maintains the library. Display and Video content exclusions are a separate job.

## Step 1: Establish the offer and the searches worth protecting

Collect:

- What the business sells, who it's for, the price model, service geography and acquisition objective.
- Anything that changes who can become a customer: free trial, free plan, consultations, templates, integrations, supported use cases.
- The intended search themes or keyword plan.
- The brand and competitor strategy for each campaign: exclude that demand, buy it in another campaign, or allow it here. The existence of a separate campaign doesn't decide this on its own.

Ask for missing facts together. If the offer or themes are still unresolved, produce a provisional draft, name the gap, and don't call it ready to apply.

Then write a **protected-query list**: realistic searches the business wants to stay eligible for, including valuable ones that aren't in the keyword plan. For an SMS platform with a free trial, that might include `free trial sms marketing software`, `sms platform reviews`, `tcpa compliant sms marketing` and `sms marketing for shopify`.

A small budget can justify tighter campaign priorities or bounded tests. It doesn't make an ambiguous query irrelevant. If the business deliberately excludes potentially relevant demand to focus spend, record that tradeoff and its scope.

## Step 2: Build candidates from specific intent mismatches

Categories organize the work. They're prompts for investigation, not lists to paste into every account. `references/category-library.md` has the prompts and industry notes.

| Category | What must be established before excluding |
|---|---|
| Employment | The search seeks a job, salary or career information this campaign doesn't serve. Hiring and recruitment products may need those words. |
| Education or DIY | The particular learning or build-it-yourself intent is outside the campaign's goal. Tutorials, templates and documentation can also support a buying journey. |
| Support or troubleshooting | The search is outside the offer. Support software, repair services and replacement products acquire customers through problem searches. |
| Free, discounts or piracy | Separate an unwanted free substitute or pirated product from a relevant trial, consultation, coupon or free-shipping offer. |
| Wrong product or audience | The search asks for something the business doesn't sell or a use case it can't serve. Confirm the actual limitation. |
| Fraud, privacy or compliance | These can be the product category itself. Never infer that a concerning word means the searcher is a bad customer. |

For healthcare, legal and local services, verify the actual service and eligibility before excluding condition, cost, insurance or place terms. A search that looks like research can come from someone seeking the service.

For each candidate, record the unwanted intent, the business evidence, the proposed negative, match type, intended scope, confidence and the buyer searches that need protecting.

Don't invent search volume, conversion rates, savings or a target library size. At launch these are decisions from business context. Performance evidence comes later, through search-term review.

## Step 3: Choose the match type deliberately

Use the narrowest exclusion that achieves the intended coverage. Exact works for an isolated unwanted query. Phrase fits when the whole phrase represents unwanted intent across the affected campaigns. Broad fits when the word combination is unwanted in any order.

These rows explain matching only; they aren't a recommended employment list:

| Negative | Match | Blocks | Doesn't block |
|---|---|---|---|
| `remote jobs` | [Broad](https://support.google.com/google-ads/answer/7302703?hl=en) | jobs for remote accountants | remote accountant |
| `remote jobs` | [Phrase](https://support.google.com/google-ads/answer/7302992/negative-phrase-match-definition) | entry level remote jobs | jobs for remote accountants |
| `remote jobs` | [Exact](https://support.google.com/google-ads/answer/7302926?hl=en) | remote jobs | entry level remote jobs |

- Negatives don't cover synonyms or singular/plural forms. None of the rows above blocks "remote job". Google says casing and misspellings are handled automatically; that isn't general semantic expansion. [Matching guidance](https://support.google.com/google-ads/answer/2453972?hl=en)
- A one-word phrase negative such as `free` is no narrower than the same one-word broad negative. Choose from the searches actually excluded, not the apparent safety of the match-type label.
- A list's category name doesn't participate in matching. An "Education" list only blocks what its actual negatives match. Google also documents a limit when the negative term appears after the sixteenth word of a long query.
- "Doesn't block" means the negative doesn't prevent eligibility. It doesn't promise an ad will serve.

## Step 4: Put each exclusion at the intended level

Read existing account negatives, shared lists and their attachments, campaign and ad-group negatives, brand controls and relevant Search automation settings. Missing access is a coverage gap. An export supports drafting but can't prove current attachments.

- **Account-level negatives:** only for intent the business wants excluded across every affected campaign. They apply to eligible Search and Shopping inventory in supported campaign types, including future campaigns. [Account scope](https://support.google.com/google-ads/answer/11396330?hl=en)
- **Shared list attached to named campaigns:** when those campaigns share the same exclusions. Creating a list doesn't apply it. Editing an existing list affects every campaign using it, including ones outside the task. [Shared lists](https://support.google.com/google-ads/answer/2453983?hl=en)
- **Campaign or ad-group negatives:** for local exclusions. If a manager-account list is involved, identify its owner and every affected account and campaign before editing it.

Don't make own-brand, competitor or offer-specific exclusions account-wide just because several campaigns need them. List capacity isn't a target to fill.

**Performance Max** negative keywords cover Search and Shopping inventory, not every channel. **Demand Gen**'s current setup documentation says negative keywords and brand exclusions aren't eligible, so don't promise a copied Search library controls Demand Gen delivery. [PMax negative scope](https://support.google.com/google-ads/answer/15726455?hl=en), [Demand Gen limitations](https://support.google.com/google-ads/answer/17122651?hl=en)

**Brand separation is its own decision.** An exact negative `[northstarcrm]` excludes the bare brand query, not `northstarcrm pricing`. For broader brand exclusion, evaluate brand lists or an explicitly scoped negative set and test the variants you mean to cover. Before changing an existing brand list, identify every campaign using it and whether each uses it to include or exclude. New Search brand exclusions can require AI Max; inspect its matching, text and URL settings rather than switching on a broader automation package to finish a negatives task. [Brand settings](https://support.google.com/google-ads/answer/13721847?hl=en)

If the plan routes demand to another campaign, verify that campaign is active, eligible and set up to capture it. An exclusion in one campaign doesn't make another one win the search.

## Step 5: Check what's blocked and what's protected

- Test each proposed negative against the target keywords **and** the protected-query list. A keyword-overlap check alone misses valuable searches that aren't in the plan.
- Apply the combined effect of existing and proposed exclusions at every inherited level. Two individually reasonable lists can create an unwanted combined restriction. A protected-query list is a review tool; it doesn't override an active negative.
- For every candidate, show one search it blocks and at least one relevant nearby search that must stay eligible. For shared or account-level exclusions, check each materially different offer they affect.
- Resolve conflicts by narrowing the text, changing the match type, limiting the scope, or leaving the candidate out.
- Deduplicate by text, match type and scope. Don't delete an existing duplicate just to tidy up; it may serve a different attachment.
- Put ambiguous terms on a watch list with the unresolved question and the evidence that would decide it. Lack of evidence isn't evidence of poor customer quality.

## Output

1. **Annotated review table:** Negative | Match | Category | Scope (account, list + attached campaigns, campaign, ad group) | Reason | Blocks | Must not block | Confidence | Decision (propose, reject, watch)
2. **Watch list:** term, unresolved question, and what evidence would decide it.
3. **Conflicts and gaps:** existing negatives that collide with protected searches, missing access, proposed attachment changes.
4. **Clean import file:** separate from the review table, with the match type and destination set explicitly. Notes, categories and explanatory punctuation must not become keyword text. Google Ads Editor can default an unspecified negative to broad. [Editor import formats](https://support.google.com/google-ads/editor/answer/47635?hl=en-GB)
5. **Summary:** counts by decision, what was deliberately left out and why, how to remove a term or detach the list if it blocks wanted demand, and when to run the first search-term review based on spend pace.

Nothing is written to the account without a human approving the exact rows, match types and scope.

## Worked example (hypothetical)

**Business:** "SMS marketing software for e-commerce brands, $99-499/mo, 14-day free trial, US only."
**Target themes:** sms marketing software, text message marketing, sms for shopify, ecommerce sms platform, klaviyo alternative.
**Brand/competitor:** no brand campaign yet. "klaviyo alternative" is a deliberate target in Non-Brand, so competitor searches are allowed there.
**Protected searches:** free trial sms marketing software, sms platform reviews, tcpa compliant sms marketing, sms marketing for shopify, klaviyo alternative for sms.

Scope for proposed rows: shared list "SMS starter negatives", attached to NB-Search only.

| Negative | Match | Category | Blocks | Must not block | Decision |
|---|---|---|---|---|---|
| `jobs` | Phrase | Employment | sms marketing jobs remote | sms marketing software | Propose |
| `salary` | Phrase | Employment | sms marketing manager salary | sms marketing for shopify | Propose |
| `free sms app` | Phrase | Free (consumer) | free sms app for iphone | free trial sms marketing software | Propose |
| `prank text` | Phrase | Wrong audience | prank text messages | text message marketing | Propose |
| `ringtone` | Phrase | Wrong product | sms ringtone download | sms platform for shopify | Propose |
| `sim card` | Phrase | Wrong product | prepaid sim card | ecommerce sms platform | Propose |
| `free` | Phrase | Free | free sms app | **free trial sms marketing software** | Reject: blocks the advertised trial |
| `tcpa` | Phrase | Compliance | tcpa rules for texting | **tcpa compliant sms marketing** | Reject: compliance is a buying criterion |
| `sms`, `text` | Phrase | n/a | everything | **every target theme** | Reject |
| `whatsapp api` | Phrase | Other platform | whatsapp api pricing | n/a | Watch: confirm the platform doesn't offer WhatsApp messaging |
| `what is sms marketing` | Exact | Education | what is sms marketing | sms marketing software | Watch: research that can lead to a trial; decide from search-term data |

`klaviyo` isn't a negative here: the competitor strategy allows it in Non-Brand. When a brand campaign launches, decide brand separation then. An exact `[brandname]` negative in Non-Brand would only block the bare brand search.

**Summary:** 6 proposed, 3 rejected, 2 on the watch list. First search-term review after the first week at planned spend.

## Hard rules

- **Start from what to protect**, including buyer searches that aren't in the keyword plan.
- **Categories are prompts, not lists.** `free`, `jobs`, `support`, `template` and `fraud` aren't universal negatives.
- **Narrowest exclusion that works.** Pick match type from the searches it actually blocks.
- **Every candidate shows a blocked and a protected search**, and the combined effect with existing negatives is checked.
- **Scope deliberately.** Account-level only when the business wants the exclusion everywhere.
- **No invented volume, savings or library size.** More negatives and fewer impressions aren't success measures on their own.
- **A human approves before anything is written**, and a candidate from another workflow doesn't inherit that approval.

## Related skills

- **[`search-term-scorer`](https://github.com/treboutat/google-ads-search-term-scorer):** once real search-term data exists, review actual queries and maintain the library.
- **[`ads-audit`](https://github.com/treboutat/google-ads-account-audit):** checks 21-23 review negative ownership, unwanted intent and buyer language.

## Tone

Operational. The output is a reviewable library with its reasoning, not an essay. Be specific on clearly unwanted intent and careful with anything a buyer might search.
