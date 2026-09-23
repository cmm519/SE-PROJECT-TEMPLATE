# Project brief

Copy this file, fill every `{{FILL: ...}}` spot, and keep it next to the prompt generator. The generator and the implementation guide both read from this brief. Leave a field blank only if it does not apply, and say `none`.

## Name

{{FILL: project name}}

## Goal

One paragraph. Say what the finished project does and who it is for.

{{FILL: one-paragraph goal}}

## Stack

Language, runtime, frameworks, and build tool.

{{FILL: stack}}

## Hard constraints

Rules the agent must not break. Examples: supported operations, what is out of scope, required libraries, file formats.

{{FILL: hard constraints}}

## Ordered components

One line per prompt. The first items should create the project skeleton and dependencies. Later items should be one component each. Use the filename you want written into `prompts/`.

1. {{FILL: 01-filename.md}} — {{FILL: what this step creates}}
2. {{FILL: 02-filename.md}} — {{FILL: what this step creates}}
3. {{FILL: add more numbered lines, one component per prompt}}

## Directory layout

The tree the finished project must match.

```
{{FILL: directory tree}}
```

## Build and test commands

Commands to run after the last prompt. Include the command that must succeed and how to start the app.

1. {{FILL: build command}}
2. {{FILL: run command}}
3. {{FILL: extra checks}}

## Done criteria

Observable results. Describe behavior, not class names copied from an old example.

- {{FILL: done criterion}}
- {{FILL: done criterion}}
- {{FILL: done criterion}}

## Architecture check

How the main parts relate. Name each part and its job.

- **{{FILL: part name}}**: {{FILL: responsibility}}
- **{{FILL: part name}}**: {{FILL: responsibility}}

## If the build fails

Checks that match this stack.

1. {{FILL: failure check}}
2. {{FILL: failure check}}
3. {{FILL: failure check}}
