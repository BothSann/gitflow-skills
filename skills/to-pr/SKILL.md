---
name: to-pr
description: Commit, rebase, push, and open a GitHub pull request in the standard format for the current branch. Use when the user says /to-pr, "open a PR", "ship this", or "create a pull request".
---

# to-pr

Commit, rebase to a clean linear history, push, and open the PR. No draft step.

Read first:
- `rules/branches.md`
- `rules/title.md`
- `rules/body.md`

## Steps

1. **Base.** Pick base per `rules/branches.md`. Stop if on a protected branch.
2. **Commit.** If changes are uncommitted, check `git status`. Never stage secrets (`.env`, keys). Message follows `rules/title.md`.
3. **Rebase.**
   - `git fetch origin`
   - `GIT_SEQUENCE_EDITOR=: git rebase -i --autosquash origin/<base>`
   - On conflict: `git rebase --abort`, list conflicting files, stop.
4. **Push.** `git push --force-with-lease -u origin HEAD`
5. **Issue.** Number from branch `<prefix>/<number>-<slug>`. If found, `gh issue view <number>` and reuse its title, type, criteria.
6. **Write.** Title and body per the rules.
7. **Label.** `gh label create <type>` (ignore "already exists").
8. **Create.** Write body to a temp file.
   - PR exists for branch: `gh pr edit --title "<title>" --body-file <file>`
   - Otherwise: `gh pr create --base <base> --title "<title>" --body-file <file> --label <type>`
9. **Reply.** PR URL.
