# gitflow-skills

Claude Code skills for everyday GitHub work.

| Skill | Does |
| --- | --- |
| `/to-issue` | Creates an issue: `type(scope): description`, Goal or Bug, Acceptance criteria |
| `/to-pr` | Commits, rebases onto base, force-pushes with lease, opens the PR linked to the issue |

## Install

```
/plugin marketplace add C:\Users\thann\Desktop\gitflow-skills
/plugin install gitflow-skills@gitflow-skills
```

Needs `git` and `gh` (logged in).

## Branches

Default: GitHub Flow, base `main`. Branch names: `feature/<issue>-<slug>`, `bugfix/<issue>-<slug>`.
For other branch roles, add `.github/gitflow.md` to the target repo (see `skills/to-pr/rules/branches.md`).

Each skill keeps its format rules in `skills/<skill>/rules/*.md`.
