# Body

Feature or task:

```markdown
## Goal
<one sentence: what and why>

## Acceptance criteria
- [ ] <testable outcome>

## Notes
<optional: links, out of scope>
```

Bug (`fix`): replace `## Goal` with `## Bug` — one or two sentences on what happens and why it is wrong.

Rules:
- One line per item. No filler, no restating the title.
- Criteria are testable outcomes, not implementation steps. Max 5.
- Omit `## Notes` when empty.

Example:

```markdown
## Goal
Customers pay orders online with ABA PayWay.

## Acceptance criteria
- [ ] Customer can pay with PayWay
- [ ] Successful payment marks order `paid`
- [ ] Failed or cancelled payment keeps order `pending`

## Notes
Out of scope: refunds.
```
