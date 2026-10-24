---
name: to-pr
description: Commit, rebase, run checks, push, and open a GitHub pull request in the standard format for the current branch. Use when the user says /to-pr, "open a PR", "ship this", or "create a pull request".
---

# to-pr

Commit, rebase to a clean linear history, run checks, push, and open the PR. No draft step.

Read first:
- `rules/branches.md`
- `rules/checks.md`
- `rules/title.md`
- `rules/body.md`

Run every git command through Bash (POSIX syntax), not PowerShell.

## Steps

1. **Base.** `git fetch origin`, then pick base per `rules/branches.md`.
2. **Branch.** If on a protected branch:
   - Stop if it has commits not on `origin`, or if nothing is uncommitted.
   - Otherwise `git switch -c <branch> origin/<base>`, naming it per `rules/branches.md`. Uncommitted changes move with it. If the switch is refused, stop.
3. **Commit.** If changes are uncommitted, check `git status`. Never stage secrets (`.env`, keys). Message follows `rules/title.md`.
4. **Rebase.**
   - `GIT_SEQUENCE_EDITOR=: git rebase -i --autosquash origin/<base>`
   - On conflict: `git rebase --abort`, list conflicting files, stop.
5. **Check.** Run checks per `rules/checks.md`. On failure: report the command and failing output, stop. Do not push.
6. **Push.** `git push --force-with-lease --force-if-includes -u origin HEAD`
7. **Issue.** Number from branch `<prefix>/<number>-<slug>`. If found, `gh issue view <number>` and reuse its title and criteria.
8. **Write.** Title and body per the rules. Verification lists the checks from step 5.
9. **Create.** Write body to a temp file. No labels.
   - PR exists for branch: `gh pr edit --title "<title>" --body-file <file>`
   - Otherwise: `gh pr create --base <base> --title "<title>" --body-file <file>`
10. **Reply.** PR URL.
