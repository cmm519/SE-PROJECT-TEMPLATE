# Software requirements specification

You fill this file. It is stage 1 of the workflow in `README.md`.

Replace every `{{FILL: ...}}` token, including the braces. This file is the only place you state what the system must do. Do not name classes, prompt filenames, or the directory tree here. Those belong in `architecture.template.md` and `structure.template.md`.

Sections marked **Required** must be filled before any agent runs. Sections marked **Optional** may say `none`.

The shape follows the software requirements topics in ISO/IEC/IEEE 29148:2018. It is a project template, not a copy of the standard. Agents cite requirement IDs from the table below. They do not paste this whole file into every prompt.

## Required: Identity

{{FILL: project name}}

## Required: Purpose

Who this specification is for, and what record it is (the requirements the build must satisfy).

{{FILL: purpose}}

## Required: Scope

What the finished software does, who it is for, and the benefit it provides. One paragraph.

{{FILL: scope}}

## Required: Product perspective

How this software sits next to its users and any larger system. Name the external systems it talks to. If it stands alone, say so.

{{FILL: product perspective}}

## Required: Users

Who uses it, and what they already know how to do. One line per kind of user.

- {{FILL: user kind}} — {{FILL: what they are trying to do}}

## Required: Product functions

A short overview of the major functions. The testable statements are in the table below, not here.

- {{FILL: function overview}}
- {{FILL: function overview}}

## Required: Assumptions and dependencies

Conditions you are treating as true, and things the software needs that this project does not build.

- {{FILL: assumption or dependency}}

## Required: Out of scope

Behavior the agent must not add.

- {{FILL: excluded behavior}}

## Required: Requirements

One row per requirement. One testable statement per row.

- Function rows use `SRS-FR-001`, `SRS-FR-002`, and so on.
- Quality rows (speed, security, reliability, usability) use `SRS-NFR-001`, `SRS-NFR-002`, and so on.
- Priority is `must` or `should`.
- Verification is the observation that proves the row. Describe behavior you can see or measure.

Add rows until every must-have function and quality is listed. Delete a sample row only by replacing it. Do not leave a row half filled.

| ID | Statement | Priority | Verification |
| --- | --- | --- | --- |
| SRS-FR-001 | {{FILL: one testable statement}} | {{FILL: must or should}} | {{FILL: how you will observe this}} |
| SRS-NFR-001 | {{FILL: one testable quality statement}} | {{FILL: must or should}} | {{FILL: how you will observe this}} |

## Optional: External interfaces

Inputs and outputs that cross the boundary of this software. Write `none` if the product perspective already covers this and there is no further contract.

{{FILL: interfaces, or none}}

## Optional: Logical data

Data the software must store or remember, in business terms. Write `none` if it stores nothing.

{{FILL: data to remember, or none}}

## Optional: Performance

Numbers: response time, volume, or rate. Write `none` if no number is required. If you write a number here, also add a matching `SRS-NFR-` row.

{{FILL: performance numbers, or none}}

## Optional: Design constraints

Constraints the requirements impose (a required protocol, a regulation, a platform you cannot leave). Stack and architecture choices you are making on purpose go in `architecture.template.md` instead. Write `none` if requirements add no further constraint.

{{FILL: constraints from requirements, or none}}

## Optional: Software attributes

Reliability, security, maintainability, or similar qualities that are not already a row above. Write `none` if the `SRS-NFR-` rows are enough.

{{FILL: attributes, or none}}
