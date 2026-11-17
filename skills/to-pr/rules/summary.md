# Summary sketch

Optional visual under the Summary sentence. Skip it when the change fits in one sentence.

## Default: diff sketch

A ` ```diff ` block that shows where the change lands. GitHub colors `+` green and `-` red.

```diff
 CLAUDE.md
   ## Agent skills
     ### Triage labels
+    ### Animatic
+      pointer -> docs/agents/animatic.md
 docs/agents/
   triage-labels.md
+  animatic.md   # voice: edge-tts · renderer: kit · stitcher: ffmpeg
```

Rules:
- One tree: files, then what's inside them (markdown headings, classes, methods, functions).
- `+` added, `-` removed, leading space for unchanged lines.
- Unchanged lines: parent levels always. Siblings only when they help someone find their way.
- `# note` at the end of the line: only on `+`/`-` lines, at most one per line, short.
- Max 15 lines. Over that, fold levels (`src/sessions/` instead of each file).

## Fallbacks

Use one only when the change has no meaningful "before" to diff against:
- File tree: brand-new folders or files.
- Call tree: a new runtime flow.
- Pseudocode: new logic or an algorithm.
- Mermaid `sequenceDiagram`: back-and-forth between services.

Same 15-line cap.

Credit: adapted from Dex Horthy's [`show-me`](https://github.com/humanlayer/skills/blob/main/plugins/show-me/skills/show-me/SKILL.md) skill (HumanLayer).
