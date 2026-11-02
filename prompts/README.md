# prompts

The generator writes the Module of Thought files in this folder. The folder starts with this README only.

| File | Role |
| --- | --- |
| `00-master-context.md` | Prompt 0. Reload it at the start of each implementation session. It is not an implementation step |
| `01-....md` onward | One capability each. Filename order is execution order. The generator selects the names, for example `01-project-setup.md` |
| `tracking.md` | The status matrix. The implementation agent updates it after each increment |

The status values are `not started`, `green`, `yellow`, `red`, and `rolled back`.

Do not put application code or old notes from an earlier product in this folder.
