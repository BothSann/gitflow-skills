# Title

Format: `<emoji> type(scope): description`

| Type | Emoji | Use for |
| --- | --- | --- |
| `feat` | ✨ (or a domain emoji below) | New feature |
| `fix` | 🐛 | Bug fix |
| `refactor` | ♻️ | Structure change, same behavior |
| `perf` | ⚡ | Performance |
| `chore` | 🔧 | Maintenance, config, dependencies |
| `style` | 🎨 | Formatting only |
| `build` | 🏗️ | Build system, images |
| `ci` | 👷 | CI pipelines |
| `docs` | 📝 | Documentation |
| `test` | 🧪 | Tests |

Domain emojis for `feat` (use when the scope fits, else ✨):
💳 payments · 🔐 auth · 📦 parcel · 🚚 delivery · 🚌 bus · 📊 data, reporting · 📣 marketing, notifications · 🔎 search, tracking

Rules:
- `scope` = affected module, e.g. `payments`, `portal`, `auth`. Omit only for repo-wide work.
- Description starts with a lowercase verb: `add`, `fix`, `implement`, `integrate`, `allow`.
- Keep proper nouns, acronyms, and code names as written: `ABA PayWay`, `PHP`, `UUID`, `FCM`.
- No trailing period. One title per issue.

Examples:
- `💳 feat(payments): implement shared online payments with ABA PayWay`
- `🐛 fix(portal): hide customers without push tokens from notification recipients`
