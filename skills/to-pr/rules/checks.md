# Checks

Run before every push, on the rebased code.

Find the commands, in order:
1. `CLAUDE.md` or `AGENTS.md` in the repo.
2. Scripts in `composer.json`, `package.json`, `Makefile`, or CI workflows in `.github/workflows/`.

Run:
- Tests for changed files, e.g. `php artisan test --compact <test files>`, `npm test -- <files>`.
- Lint or format in check mode, e.g. `vendor/bin/pint --test --diff=origin/<base>`, `npm run lint`.
- Static analysis if the repo has it, e.g. `composer analyse`.

Rules:
- Narrow tests to changed areas. Run the full suite only when changes are broad or no narrower target exists.
- Never run commands that deploy, migrate shared databases, or call paid or production services.
- Record each command and its result, e.g. `(13 passed)`, for Verification.
- No checks found or none runnable: write `Not run` under Verification and give the reason in Verification Limits.
- A failure caused by the local environment, not the change (e.g. missing credentials): note it under Notes and continue.
