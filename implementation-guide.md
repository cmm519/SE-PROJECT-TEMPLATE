# Implementation guide

You implement the project that the user files and the generated files in `prompts/` describe.

## Before you start

Read these files before you change the project:

1. `prompts/00-master-context.md`
2. `srs.md`
3. `architecture.md`
4. `structure.md`
5. `prompts/tracking.md`
6. `Module of Thought_instr.md`

If `srs.md`, `architecture.md`, or `structure.md` contains `{{FILL:`, stop. Do not write application code.

If `prompts/00-master-context.md` or `prompts/tracking.md` is missing, stop. Tell the user to run `prompt-generator.md` first.

If `architecture.md` names a primary design rule path, read that one `.mini.md` file. Apply it while you write code. If the value is `none`, do not load a book rule. Do not open a second book. Do not paste the book file into the prompts.

## Start of each session

Reload `prompts/00-master-context.md`. Read `prompts/tracking.md`. Continue from the first row whose status is not `green`.

## Run order

Run every `prompts/NN-*.md` file after `00-master-context.md`, in sort order.

Follow each increment as written. Do not change a path, a cited SRS statement, or a signature that the increment specified. You may change a `derived` signature only when the verification of the increment cannot pass without the change. Record that change in `prompts/tracking.md`.

Do not add a requirement, part, screen, or folder that the user files and the increment do not name. Do not invent features to fill gaps. If a prompt contradicts the SRS, stop and report the contradiction.

## Checks after each increment

1. Fix the errors from this increment before you start the next file.
2. Check that new files are on paths that the increment named and that exist in `structure.md`.
3. Check that the imports and references from this increment resolve.
4. Compare the result to the Green, Yellow, and Red text for this row in `prompts/tracking.md`.
5. Set the status of the row to `green`, `yellow`, or `red`.

## Red zone

If a row is `red`, stop the sequence. Use these steps, which come from the degradation steps in `Module of Thought_instr.md`:

1. Isolate: run this increment without the later work.
2. Compare the failing behavior with the verification on the cited SRS IDs.
3. Check the intermediate results at the boundary that the increment names.
4. Check the computation or transformation that this increment added.
5. Apply the mitigation from a `CRITICAL` increment. Otherwise, roll back to the previous increment and set the status to `rolled back`.

Do not start the next increment until this row is `green` or the user changes the increment file.

## Final check

After the last increment is `green`:

1. Run the build, run, and extra-check commands from `structure.md`. If the build or run fails, use the failure checks in that file before you try a different fix.
2. Check every `must` row in `srs.md`. Its verification must hold.
3. Check that the tree matches `structure.md`.
4. Check that each part in `architecture.md` still has the job written there and that the decisions are intact.

The project is complete when every tracking row is `green`, the build command succeeds, every `must` verification holds, and the layout matches the tree.
