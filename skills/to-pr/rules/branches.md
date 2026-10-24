# Branches

If the repo has `.github/gitflow.md`, it overrides this file.

Default (GitHub Flow):
- Base for every PR: `main`.
- Names: `feature/<issue>-<slug>`, `bugfix/<issue>-<slug>`.

Protected (never run on, never force-push): `main`, `next`, `release/*`.

Extended roles (copy into a repo's `.github/gitflow.md` when needed):
- `main` = production truth
- `next` = integration branch for upcoming work
- `release/<version>` = UAT/freeze branch cut from `next`
- `feature/<issue>-<description>` = feature work from `next`
- `bugfix/<issue>-<description>` = normal fixes from `next`
- `hotfix/<issue>-<description>` = production fixes from `main`
- `release-fix/<issue>-<description>` = release-only fixes from the active `release/<version>` branch

PRs target the branch each type was cut from.
