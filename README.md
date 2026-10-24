# gitflow-skills

Claude Code skills for everyday GitHub work, following the `bstnt/platform` conventions.

| Skill | Does |
| --- | --- |
| `/to-issue` | Creates an issue: `<emoji> type(scope): description`, 📋 Summary, 🎯 Scope, ✅ Acceptance Criteria |
| `/to-pr` | Commits, rebases onto base, force-pushes with lease, opens the PR: Summary, Scope, Acceptance Criteria, Verification, `Closes #N` |

No labels. PR titles drop the issue's emoji.

## Install

```
/plugin marketplace add BothSann/gitflow-skills
/plugin install gitflow-skills@gitflow-skills
```

Needs `git` and `gh` (logged in).

## Branches

Base is `next` when the repo has it, else `main`. `hotfix/*` targets `main`.
Branch names: `feature/<issue>-<slug>`, `bugfix/<issue>-<slug>`.
A repo can override this with `.github/gitflow.md`.

Each skill keeps its format rules in `skills/<skill>/rules/*.md`.
