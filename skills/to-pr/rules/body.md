# Body

```markdown
## Summary
<one sentence>

## Changes
- <what a reviewer needs to know>

## Acceptance criteria
- [x] <criterion met>
- [ ] <criterion not met yet>

## Verification
- <command run or manual check done>

Closes #<number>
```

Rules:
- One line per item. No filler. Max 5 changes.
- Criteria come from the linked issue. Tick only what the diff actually meets.
- Verification: max 3 lines. Exact command or manual check. Only what was actually done in this session or stated by the user. Nothing done: `Not verified`. Never omit.
- No linked issue: omit `Closes`, write criteria from the change.
- Omit any other section with nothing to say.

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

## Verification
- `php artisan test --filter=PayWay` passes
- Paid and cancelled a sandbox order by hand

Closes #42
```
