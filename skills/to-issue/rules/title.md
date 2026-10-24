# Title

Format: `type(scope): description`

| Type | Use for |
| --- | --- |
| `feat` | New feature |
| `fix` | Bug fix |
| `refactor` | Structure change, same behavior |
| `perf` | Performance |
| `docs` | Documentation |
| `test` | Tests |
| `chore` | Maintenance, dependencies, tooling |
| `style` | Formatting only |

Rules:
- All lowercase.
- `scope` = affected module, e.g. `payments`, `portal`, `parcel`.
- Colon, then one space.
- Description starts with a verb: `add`, `fix`, `implement`, `integrate`, `allow`.
- No trailing period. One title per issue.

Examples:
- `feat(payments): implement shared online payments with aba payway`
- `fix(portal): hide customers without push tokens from notification recipients`
