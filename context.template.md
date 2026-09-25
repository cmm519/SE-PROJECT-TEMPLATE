# Context

You fill this file. It is the persistent context every agent session reloads. It is not a second copy of the goals, the architecture, or the tree.

Replace every `{{FILL: ...}}` token, including the braces. Write `none` only where a line says you may.

## Identity

{{FILL: project name}}

## What this is

One paragraph. Who it is for and what problem it solves. Do not list requirements here; those are goals.

{{FILL: one-paragraph context}}

## Users

- {{FILL: user kind}} — {{FILL: what they already know and what they are trying to get done}}

## Domain facts the agent must not rediscover

Facts that are true for this product and easy to get wrong. Leave out anything already stated as a goal or an architecture decision.

- {{FILL: domain fact}}

## Constraints that apply to every slice

- {{FILL: constraint}}

## Glossary

Words the agent must use as written. One line each.

| Term | Meaning |
| --- | --- |
| {{FILL: term}} | {{FILL: meaning}} |

## Out of bounds

Work this project will not do, even if a later slice could be read that way.

- {{FILL: excluded work}}
