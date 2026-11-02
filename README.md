# MoT project

This folder holds a Cursor workflow that builds a project from a sequence of prompts. [Module of Thought_instr.md](Module%20of%20Thought_instr.md) defines the method. This folder does not contain an application.

## Stages

In stages 1 to 3, replace each `{{FILL: ...}}` token, including the braces. To leave a field blank, write `none`. Do this only in a section that allows it.

A stage is ready only when its check passes. An agent prompt must stop if an earlier file still contains `{{FILL:`. Do not start stage 6 until you finish the review in stage 5.

| Stage | Who | File | Contents or action | Ready when |
| --- | --- | --- | --- | --- |
| 1 | You | [srs.md](srs.md) | What the system must do, for whom, and how you will know. No class names, prompt filenames, or directory tree | Every must-have requirement has an ID, one testable statement, and a verification |
| 2 | You | [architecture.md](architecture.md) | Users, external systems, main parts and their jobs, stack, hard constraints, and one to three decisions. Optional: one book rule path | Context, containers, and decisions are filled. The design-rule path is a single `.mini.md` file or `none` |
| 3 | You | [structure.md](structure.md) | Directory tree, the part that owns each path, and the build, run, and failure commands | The tree and the ownership table match the architecture parts. Build and run commands are filled |
| 4 | Agent | [prompt-generator.md](prompt-generator.md) | Open a Cursor Agent chat and point it at this file | It writes `prompts/00-master-context.md`, numbered increments, and `prompts/tracking.md`. It does not write application code |
| 5 | You | [prompts/](prompts/README.md) | Read the master context and the increment filenames. If something is wrong, edit the prompt files | The increments cover every SRS ID and add no part that you did not name |
| 6 | Agent | [implementation-guide.md](implementation-guide.md) | Open a new Agent chat. Point it at this file and `prompts/` | It runs the increments in filename order, updates `prompts/tracking.md`, and cites SRS IDs |

Do not copy facts from the three user files into the agent prompts. The agents read the files. The agent must not invent a requirement, a part, or a folder that these files do not name.

If a row becomes red, the agent stops and follows the degradation steps in `Module of Thought_instr.md`. If a later prompt contradicts an earlier prompt, fix the prompt file. Then run again from that increment.

## Design rules from books

`user resources/agent-rules-books/` holds optional rules from books. These rules bias the implementation. They are not the architecture plan. See [ARCHITECTURE-NOTES.md](user%20resources/ARCHITECTURE-NOTES.md) and [HOW-TO-agent-rules-books.md](user%20resources/HOW-TO-agent-rules-books.md).

## Optional setup: Git Bash as the default terminal

Cursor on Windows often uses PowerShell. PowerShell may not report that a terminal command finished, so the agent continues to wait. To use Git Bash (Git for Windows provides it), press `Ctrl-Shift-P`, run **Terminal: Select Default Profile**, and select **Git Bash**.

## Before reuse

1. Delete the generated files in `prompts/`. Keep `prompts/README.md`.
2. Overwrite the three user files so that they describe only the next project.
