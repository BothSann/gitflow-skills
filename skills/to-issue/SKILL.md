---
name: to-issue
description: Create a GitHub issue in the standard format from the user's request and the current conversation. Use when the user says /to-issue, "open an issue", "make a ticket", "file a bug", or "turn this into a task".
---

# to-issue

Write one GitHub issue and create it with `gh`. No draft step.

Read first:
- `rules/title.md`
- `rules/body.md`

## Steps

1. **Gather.** Use text after `/to-issue` plus this session's discussion. Work out type, scope, goal, criteria. Ask one short question only if type or scope is unclear.
2. **Write.** Title and body per the rules.
3. **Label.** `gh label create <type>` (ignore "already exists").
4. **Create.** Write body to a temp file, then:
   `gh issue create --title "<title>" --body-file <file> --label <type>`
5. **Reply.** Issue URL and branch name: `feature/<number>-<slug>` (`bugfix/` for `fix`).
