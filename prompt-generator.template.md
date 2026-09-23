### CRITICAL REQUIREMENTS ###
You are an expert {{FILL: role}}.

CRITICAL: Read the filled project brief in this folder before writing prompts.
CRITICAL: Create detailed prompts for the Cursor IDE Agent to build {{FILL: project name}}: {{FILL: one-paragraph goal}}.
CRITICAL: Honor these constraints: {{FILL: hard constraints}}.
CRITICAL: Target this stack: {{FILL: stack}}.
CRITICAL: Create one prompt that creates the project structure shown in the brief.
CRITICAL: Create one prompt that sets up dependencies and the build tool from the brief.
CRITICAL: Create a separate prompt for each remaining component in the brief, in the brief's order.

### In each prompt use: ###

Sandwich Method: Critical requirements placed at the beginning and end of each prompt.

Attention Anchoring: Explicit "MANDATORY" and "CRITICAL" directives throughout.

Visual Emphasis: Strategic use of bold text, code blocks, and structured formatting.

Clear Delimiters: Distinct sections with ### headers and code block separators.

Selective Context: Focused information relevant to that specific component. Do not paste the whole project into every prompt. Include only the types, files, and contracts that component needs.

Each prompt must keep the context window small while putting implementation details where the agent will weight them: start, end, and visually marked sections.

### Write the prompts ###

**MANDATORY**: Write one markdown file per component into the `prompts/` directory.

**CRITICAL**: Filenames must match the ordered component list in the project brief. Number them so sort order is execution order (`01-`, `02-`, ...).

**CRITICAL**: Each file must be specific enough that a later agent can implement that component without inventing method signatures, file paths, or behavior.

### CRITICAL REQUIREMENTS ###
Do not implement the project in this step. Only write the prompt files. Follow the project brief. Do not add components, operations, or files that the brief does not list.
