# Test: Edge case, negative would block a target keyword

**Scenario:** The obvious category negative collides with a target keyword. The QA step must catch it and narrow the negative instead of shipping a library that blocks the account's own traffic.

## Input

- **Business:** "Text-message marketing platform for retail."
- **Target themes:** text message marketing, text marketing platform, sms text campaigns.

## The trap

A naive build adds `text` and `sms` as phrase negatives to catch "free text", "prank text" and similar consumer searches. Both would block "text message marketing" and "sms text campaigns", so the account would stop serving on its best keywords.

## Expected behavior

- The QA step flags `text` and `sms` as **collisions with target themes** and rejects the bare tokens.
- It substitutes specific irrelevant phrases instead, each with a blocked and a protected example:

| Negative | Match | Blocks | Must not block |
|---|---|---|---|
| `prank text` | Phrase | prank text messages | text message marketing |
| `free text app` | Phrase | free text app for android | text marketing platform |
| `anonymous text` | Phrase | send anonymous text | sms text campaigns |
| `text to speech` | Phrase | text to speech online | text message marketing |

- It checks the whole proposed set together, since two narrow negatives can still combine to block a wanted search.
- The summary notes the collision and the narrower substitutes.

## Pass criteria
- Bare `text` and `sms` don't appear as phrase or broad negatives.
- Each substitute has a blocked and a protected example.
- The summary says why the bare tokens were rejected.
