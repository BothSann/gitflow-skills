# Branches

If the repo has `.github/gitflow.md`, it overrides this file.

Base:
- `hotfix/*` targets `main`.
- `release-fix/*` targets the active `release/<version>`.
- Everything else targets `next` if `origin/next` exists, else `main`.

Names: `<prefix>/<issue>-<slug>`, e.g. `bugfix/152-portal-notification-push-recipients`.

| Prefix | For | Cut from |
| --- | --- | --- |
| `feature/` | New work | base |
| `bugfix/` | Normal fixes | base |
| `hotfix/` | Production fixes | `main` |
| `release-fix/` | Release-only fixes | `release/<version>` |

Roles:
- `main` = production truth
- `next` = integration branch for upcoming work
- `release/<version>` = UAT/freeze branch cut from `next`

Protected (never run on, never force-push): `main`, `next`, `release/*`.

History stays linear: rebase, never merge the base into the branch.
