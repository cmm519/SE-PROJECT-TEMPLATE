# Structure

You fill this file. It is stage 3 of the workflow in `README.md`.

Replace every `{{FILL: ...}}` token, including the braces. This file is the directory tree, which architecture part owns each folder, and the commands that build and run that tree.

Fill this only after `architecture.template.md` has no remaining `{{FILL:` tokens. Every part name below must already appear in that file. Do not add a part here.

## Required: Directory tree

The tree the finished project must match. Include the files the build tool needs.

```
{{FILL: directory tree}}
```

## Required: Ownership

One row per top-level folder or important file in the tree. The architecture part must be a name from `architecture.template.md`.

| Path | Architecture part | What it holds |
| --- | --- | --- |
| {{FILL: path}} | {{FILL: part name}} | {{FILL: what this path holds}} |
| {{FILL: path}} | {{FILL: part name}} | {{FILL: what this path holds}} |

## Required: Build and run

Commands to run after the last increment. The first command is the one that must succeed.

1. {{FILL: build command}}
2. {{FILL: run command}}
3. {{FILL: extra checks, or none}}

## Required: If the build fails

Checks that match this stack. The implementation agent uses this list before inventing a fix.

1. {{FILL: failure check}}
2. {{FILL: failure check}}
3. {{FILL: failure check}}
