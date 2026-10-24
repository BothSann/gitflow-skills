# gitflow-skills

Claude Code skills for everyday GitHub work, following the `bstnt/platform` conventions.

| Skill | Does |
| --- | --- |
| `/to-issue` | Creates an issue: `<emoji> type(scope): description`, 📋 Summary, 🎯 Scope, ✅ Acceptance Criteria |
| `/to-pr` | Creates the branch if needed, commits, rebases onto base, runs tests and lint, pushes, opens the PR: Summary, Scope, Acceptance Criteria, Verification, `Closes #N` |

No labels. PR titles drop the issue's emoji.

## Install

Claude Code plugin:

```
/plugin marketplace add BothSann/gitflow-skills
/plugin install gitflow-skills@gitflow-skills
```

Or with [`npx skills`](https://github.com/vercel-labs/skills) (Claude Code, Cursor, Codex, and other agents):

```
npx skills add BothSann/gitflow-skills                  # all skills
npx skills add BothSann/gitflow-skills --skill to-pr    # one skill
npx skills add BothSann/gitflow-skills -g               # global, all projects
```

Use one method per agent. Installing both in Claude Code gives duplicate skills.

Needs `git` and `gh` (logged in).

## Branches

Base is `next` when the repo has it, else `main`. `hotfix/*` targets `main`.
Branch names: `feature/<issue>-<slug>` for `feat`, `bugfix/<issue>-<slug>` for `fix`, `<type>/<issue>-<slug>` for other types.
A repo can override this with `.github/gitflow.md`.

Each skill keeps its format rules in `skills/<skill>/rules/*.md`.
