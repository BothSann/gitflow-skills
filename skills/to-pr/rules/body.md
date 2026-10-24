# Body

```markdown
## Summary
<one sentence>

## Changes
- <what a reviewer needs to know>

## Acceptance criteria
- [x] <criterion met>
- [ ] <criterion not met yet>

Closes #<number>
```

Rules:
- One line per item. No filler. Max 5 changes.
- Criteria come from the linked issue. Tick only what the diff actually meets.
- No linked issue: omit `Closes`, write criteria from the change.
- Omit any section with nothing to say.

Example:

```markdown
## Summary
Add ABA PayWay online payment for orders.

## Changes
- Add PayWay service and config
- Add payment request endpoint and callback handler

## Acceptance criteria
- [x] Customer can pay with PayWay
- [x] Successful payment marks order `paid`
- [x] Failed or cancelled payment keeps order `pending`

Closes #42
```
