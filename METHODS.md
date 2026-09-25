# Methods considered

This note is the research behind the template. The agent prompt reads it so a session does not reopen the choice of process unless you change `method.template.md`.

## What holds up for agents

Writing the intended behavior down before coding is useful. Freezing that writing for the whole project is not. Current writing on spec-driven development (ThoughtWorks has it in Assess, with a warning against heavy up-front specs and big-bang releases) separates those two moves: a spec is a map the agent can run for a while, and it stays editable when implementation teaches you something. Marc Brooker’s account of the same idea: the spec is upstream of the code, scoped to the change, and updated in the same loop. Karl’s write-up adds the agent-specific reason: a bounded spec is how you keep the context window on the work instead of on the whole product.

That is the default this template uses. You keep one file per concern. The agent implements one verifiable slice, then you and the agent update the file that was wrong. Nothing is copied into a second prompt.

## How the named techniques differ

The difference that matters is when a fact is allowed to change, and what “done” means for a slice.

| Technique | When goals and architecture change | What a slice must do | Best fit |
| --- | --- | --- | --- |
| Spec-driven increments (default) | After a slice, if the code or a review shows the file is wrong. Edit the source file. Do not keep a second copy. | One demonstrable change, checked against the acceptance line on the goal it cites | Most agent projects. Requirements are real but not finished. |
| Waterfall | Only through a deliberate change to the goal or architecture file before the next phase. Do not quietly revise them while coding. | A phase: all of requirements, then all of architecture, then all of structure, then implementation, then verification | The requirements and the architecture are already stable, or a contract says they are. |
| Agile | The backlog order can change after each slice’s review. Architecture decisions are recorded when made, not all on day one. | A vertical slice a user could be shown. Working behavior beats a finished document. | You need feedback on a usable slice before the rest of the goals are firm. |
| Extreme programming | Same as agile, plus the tests for the slice exist and fail before the behavior exists. Design stays the smallest one that makes those tests pass. Refactor only while behavior stays the same. | A story whose acceptance checks are executable, then the code that turns them green | You want the agent’s drift caught by tests, not by another prose review. |

Module of Thought, in `Module of Thought_instr.md`, is a session protocol: reload a master context, add one capability, track a metric, stop when it fails. It is not a software lifecycle. Those session habits are already in `AGENT-PROMPT.md` (reload context, one slice, update progress, stop on red). You do not need a second method file to get them.

## What the book folder is

`user resources/agent-rules-books/` is a set of decision rules distilled from design books (clean architecture, refactoring, and the rest). Load at most one `*.mini.md` during implementation, and only if `architecture.template.md` names it. Those files do not name your users, your goals, or your tree. They are not the architecture plan.

## Sources

- ThoughtWorks and Augment on spec-driven development versus waterfall: a spec written first is not a spec frozen for the project. Mutability during implementation is the split. Heavy up-front specification and big-bang releases are the failure mode.
- Marc Brooker, “Spec Driven Development isn’t Waterfall” (2026): specs raise the level from code to an explicit map, stay upstream, and are iterated with the implementation. They are how an agent can run without a human in every edit.
- Karl, “Spec-Driven Development Might Be the Process Reset AI Needs” (2026): short spec-to-feedback loops, feature-sized specs, and a backlog that bounds context. Working software still outranks a large document.
- Counterweight, kept on purpose: treating a generated spec as if it were the system repeats the waterfall mistake. Slices need a check you can run (a command, a test, or an observation), not only a paragraph.
