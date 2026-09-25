# Development technique

You fill this file. It selects how slices are cut and when other files are allowed to change. It does not restate context, goals, architecture, or the tree. Read `METHODS.md` before you choose.

Replace the single token below with one of these words:

- `spec-driven` — default. One verifiable slice. After the slice, edit the source file if it was wrong.
- `waterfall` — lock context, goals, and architecture, then implement all `now` goals, then verify. Do not revise those files during implementation unless you explicitly reopen a phase.
- `agile` — deliver `now` goals in the order column, one vertical slice at a time. After each slice, you may reorder later goals.
- `xp` — agile, plus a failing acceptance check before the behavior, the smallest design that passes, and refactoring only when behavior stays the same.

{{FILL: spec-driven or waterfall or agile or xp}}

## Slice size

How small a slice should be for this project. One sentence.

{{FILL: one sentence on slice size}}

## Review rule

Who looks at a slice before the next one starts.

{{FILL: for example, you review the diff, or the acceptance check is enough}}
