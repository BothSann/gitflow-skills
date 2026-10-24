# Body

```markdown
## 📋 Summary
<1–2 sentences: what, and why or the current problem>

## 🎯 Scope
<one sentence or bullets: what changes, and what stays unchanged>

## ✅ Acceptance Criteria
- <testable outcome>
```

Optional sections, only when needed (place between Scope and Acceptance Criteria):
- `## 🔍 Findings` — what an investigation found (bugs).
- `## 📚 Approved references` — spec or design links, pinned to a commit.
- `## 🔒 Core rules` — invariants that must hold.
- `## ⚠️ Dependencies` — what this waits on or does not authorize.

Rules:
- Same body for features and bugs. A bug's Summary states the current wrong behavior.
- Name exact things: endpoints, classes, tests, versions, numbers.
- Criteria: plain bullets, testable outcomes, 3–5. Add one "existing X is unchanged" check when behavior could regress.
- One line per item. No filler.

Example:

```markdown
## 📋 Summary
The personal-notification recipient dropdown lists customers who cannot receive push notifications.

## 🎯 Scope
Show only customers with a registered push token in preloaded options and search results. Leave driver selection unchanged.

## ✅ Acceptance Criteria
- Customers without a push token do not appear in either list.
- Customers with a push token remain selectable.
- A driver subscription does not make a customer eligible.
```
