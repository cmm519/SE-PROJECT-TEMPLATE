# Structure

You fill this file in stage 3 (see `README.md`), after `architecture.md` has no remaining `{{FILL:` tokens. Replace every `{{FILL: ...}}` token, including the braces. Do not add a part here.

## Required: Directory tree

The tree that the finished project must match. Include the files that the build tool needs.

```
{{FILL: directory tree}}
```

## Required: Ownership

One row for each top-level folder or important file. The part must be a name from `architecture.md`.

| Path | Architecture part | What it holds |
| --- | --- | --- |
| {{FILL: path}} | {{FILL: part name}} | {{FILL: what this path holds}} |
| {{FILL: path}} | {{FILL: part name}} | {{FILL: what this path holds}} |

## Required: Build and run

The commands to run after the last increment. The first command must succeed.

1. {{FILL: build command}}
2. {{FILL: run command}}
3. {{FILL: extra checks, or none}}

## Required: If the build fails

Checks for this stack. The implementation agent uses this list before it invents a fix.

1. {{FILL: failure check}}
2. {{FILL: failure check}}
3. {{FILL: failure check}}
