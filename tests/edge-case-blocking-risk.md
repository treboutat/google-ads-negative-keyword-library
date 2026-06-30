# Test — Edge case: negative would block a target keyword

**Scenario:** The obvious category negative collides with a target keyword. The skill's QA step must catch it and narrow the negative instead of shipping a library that blocks the account's own traffic.

## Input

- **Business:** "Text-message marketing platform for retail."
- **Target themes:** text message marketing, text marketing platform, sms text campaigns.

## The trap

A naive build would add `text` (Job/Consumer-adjacent: "free text", "prank text") and `sms` as phrase negatives. Both would block the target themes "text message marketing" and "sms text campaigns" — the account would stop serving on its best keywords.

## Expected behavior

- The QA step flags `text` and `sms` as **collisions with target themes** and refuses to add the bare tokens.
- It substitutes the **specific irrelevant phrases** instead: `"prank text"`, `"free text app"`, `"anonymous text"`, `"text to speech"` — none of which catch the target themes.
- The output explicitly notes the collision and the narrower substitutes chosen.

## Pass criteria
- Bare `text` and `sms` do **not** appear as phrase/broad negatives.
- The specific consumer-intent phrases are added instead.
- The skill surfaces the collision in its summary ("did not add `text`/`sms` — would block target themes; used specific phrases").
