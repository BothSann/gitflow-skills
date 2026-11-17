# Body

```markdown
## Summary
<1–2 sentences, or 2–3 bullets for a multi-part change>

<optional sketch per rules/summary.md>

## Scope
- <what changed, with exact files or symbols>
- <what stays unchanged>

## Acceptance Criteria
- <criterion the diff meets>

## Verification
- `<exact command>` (<result, e.g. 13 passed>)

Closes #<number>
```

Rules:
- Plain headings, no emoji.
- Summary sketch: optional, per `rules/summary.md`.
- Scope: max 5 bullets. With a sketch, describe behavior without file paths; without one, name exact files or symbols.
- Criteria: from the linked issue, reworded to match what was built. Plain bullets. List only criteria actually met.
- Verification: exact commands with results, only what was actually run in this session or stated by the user. Never omit. Nothing ran: `Not run`.
- `## Known Gaps` only when a check was not run or a criterion was not met, e.g. "Full test suite not run. No deployment performed." Otherwise omit.
- `## Notes` only for ops steps outside the repo or unrelated failures.
- No linked issue: omit `Closes`.
- One line per item. No filler.

Example:

```markdown
## Summary
Hide customers without a push token from the personal-notification recipient dropdown.

```diff
 app/Filament/Resources/NotificationResource.php
   form()
     Select::make('recipient')
-      ->options(Customer::pluck('name', 'id'))
+      ->options(Customer::whereHas('pushSubscriptions')->pluck('name', 'id'))
+      ->getSearchResultsUsing(...)   # same filter on search
 tests/Feature/
+  NotificationResourceTest.php
```

## Scope
- Filter preloaded and searched recipients by customer push subscriptions.
- Leave driver selection unchanged.

## Acceptance Criteria
- Customers without a push token are absent from both dropdown paths.
- Driver subscriptions do not qualify customers.

## Verification
- `php artisan test --compact tests/Feature/NotificationResourceTest.php` (13 passed)
- `vendor/bin/pint --dirty`

Closes #152
```
