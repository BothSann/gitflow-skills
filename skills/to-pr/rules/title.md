# Title

Format: `type(scope): description` — no emoji.

Types: `feat`, `fix`, `refactor`, `perf`, `chore`, `style`, `build`, `ci`, `docs`, `test`.

Rules:
- Linked issue: reuse its title without the emoji. Shorten or rescope it if the code landed elsewhere.
- Breaking change: add `!` after the scope, e.g. `feat(api)!: use UUID banner IDs`.
- Description starts with a lowercase verb. Keep proper nouns, acronyms, and code names as written.
- No trailing period.
- Commit messages use the same format.

Examples:
- `fix(portal): hide customers without push tokens from recipients`
- `fix(docker): upgrade PHP images to v5.0.2`
