# Software requirements specification

You fill this file in stage 1 (see `README.md`). Replace every `{{FILL: ...}}` token, including the braces.

State what the system must do only in this file. Class names and the directory tree go in `architecture.md` and `structure.md`. Do not name prompt files here.

Fill the **Required** sections before any agent runs. **Optional** sections may say `none`. The topics follow ISO/IEC/IEEE 29148:2018.

## Required: Identity

{{FILL: project name}}

## Required: Purpose

Who this specification is for, and what the build must satisfy.

{{FILL: purpose}}

## Required: Scope

One paragraph: what the finished software does, who it is for, and the benefit.

{{FILL: scope}}

## Required: Product perspective

Its relation to users and to any larger system. Name the external systems. If it stands alone, say so.

{{FILL: product perspective}}

## Required: Users

One line for each kind of user. Include what they already know how to do.

- {{FILL: user kind}} — {{FILL: what they are trying to do}}

## Required: Product functions

A short overview. The testable statements go in the requirements table.

- {{FILL: function overview}}
- {{FILL: function overview}}

## Required: Assumptions and dependencies

Conditions that you treat as true, and items that this project needs but does not build.

- {{FILL: assumption or dependency}}

## Required: Out of scope

Behavior that the agent must not add.

- {{FILL: excluded behavior}}

## Required: Requirements

Write one testable statement in each row. Add rows until the table lists every must-have function and quality. Do not leave a row half filled.

- Function rows use `SRS-FR-001`, `SRS-FR-002`, and so on.
- Quality rows (speed, security, reliability, usability) use `SRS-NFR-001`, `SRS-NFR-002`, and so on.
- Priority is `must` or `should`.
- Verification is behavior that you can see or measure and that proves the row.

| ID | Statement | Priority | Verification |
| --- | --- | --- | --- |
| SRS-FR-001 | {{FILL: one testable statement}} | {{FILL: must or should}} | {{FILL: how you will observe this}} |
| SRS-NFR-001 | {{FILL: one testable quality statement}} | {{FILL: must or should}} | {{FILL: how you will observe this}} |

## Optional: External interfaces

Inputs and outputs that cross the software boundary, if the product perspective does not cover them.

{{FILL: interfaces, or none}}

## Optional: Logical data

Data that the software must store, in business terms.

{{FILL: data to remember, or none}}

## Optional: Performance

Response time, volume, or rate. For each number here, add a matching `SRS-NFR-` row.

{{FILL: performance numbers, or none}}

## Optional: Design constraints

Constraints from the requirements (a required protocol, a regulation, a platform that you cannot leave). Stack and architecture choices go in `architecture.md`.

{{FILL: constraints from requirements, or none}}

## Optional: Software attributes

Qualities that do not already have an `SRS-NFR-` row.

{{FILL: attributes, or none}}
