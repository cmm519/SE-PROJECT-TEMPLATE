# Goals

You fill this file. These are the outcomes the project exists to hit. One goal per row. The agent cites IDs. It does not paste this whole file into every slice.

Replace every `{{FILL: ...}}` token, including the braces. Add rows until the outcomes you care about are listed. Do not put directories, class names, or sprint ceremony here.

## How to write a row

- IDs are `G-001`, `G-002`, and so on.
- The outcome is one testable statement.
- Acceptance is what you can observe or run. If you chose extreme programming in `method.template.md`, this cell should be able to become a failing test.
- Order is delivery order for agile and extreme programming. For waterfall, order is irrelevant until implementation, and every `now` goal is in scope together.
- Rank is `now` or `later`. The agent does not start a `later` goal unless you change it to `now`.

| ID | Outcome | Acceptance | Order | Rank |
| --- | --- | --- | --- | --- |
| G-001 | {{FILL: one testable outcome}} | {{FILL: how you will observe it}} | 1 | now |
| G-002 | {{FILL: one testable outcome}} | {{FILL: how you will observe it}} | 2 | {{FILL: now or later}} |

## Done for the project

The project is done when every `now` goal meets its acceptance check and the build command in `structure.template.md` succeeds.

{{FILL: any extra project-level done rule, or none}}
