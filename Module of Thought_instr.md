# Module of Thought: A Domain-Independent Prompt Generation Framework

Module of Thought (MoT) is a method for complex system development with LLMs. It generates a master prompt and a sequence of incremental prompts. Chain of Thought reasons about one problem in one prompt. MoT controls development across many sessions, with persistent context and quantitative tracking.

**Use MoT for**: Software development, data pipelines, system integration, ML models, algorithm implementation, complex configuration, multi-part systems.

**Do not use MoT for**: Simple queries, single-step tasks, purely creative work without measurable outputs, problems that you cannot divide into parts.

## Master prompt (Prompt 0)

Each development session loads this reference document at the start. It prevents context drift between sessions. It contains:

1. Domain background and theory
2. System architecture: all parts, their relationships, and their dependencies
3. Part specifications: algorithms, data structures, and constraints
4. Success metrics with quantitative thresholds
5. Baseline requirements that must stay in effect during all development
6. Dependencies and prerequisites

## Incremental prompts

Each increment adds ONE capability and includes an explicit verification.

### Step 1: Divide the system into atomic capabilities

- Divide the system into 10-20 discrete capabilities that you can test independently.
- Put them in order from simple to complex. State the dependencies explicitly.
- Build each increment only on previous increments that passed verification.

### Step 2: Identify critical checkpoints before execution

Mark 20-40% of the increments as critical. For each one, write the reason, the specific technical risk, the expected failure mode, and the prepared mitigation strategy.

Indicators of a critical checkpoint:

- The first use of a complex operation
- Architectural transitions (for example, supervised → unsupervised)
- Conflicts between objectives
- Increases in computational complexity
- Integration of multiple parts

### Step 3: Define the quantitative tracking matrix

Create a performance tracking table: [Variants] × [Increments]. Specify the metrics to track for each increment. Define these zones:

- **Green**: Acceptable performance (specify the threshold)
- **Yellow**: Warning (specify the range)
- **Red**: Failure that requires intervention (specify the threshold)

### Step 4: Generate each increment prompt

Each increment prompt includes:

**a) Header**:

```
INCREMENT [N]: [Capability Name]
Status: [Standard/CRITICAL]
Dependencies: [List of required prior increments]
```

**b) Capability**: The ONE capability to add, what should change from the previous increment, and what must stay the same.

**c) Implementation**: The specific code or configuration changes, the integration points, and the expected behavior.

**d) Verification**: Quantitative success criteria (for example, "metric > threshold"), the test cases to run, and the expected outputs with tolerance ranges.

**e) For CRITICAL checkpoints only**:

- **Risk**: The specific technical challenge
- **Failure indicators**: How to recognize a failure of this checkpoint
- **Isolation test**: Test with a simplified configuration. Test each part separately. Identify interaction effects.
- **Rollback**: How to return to the last stable increment

### Step 5: Define the degradation steps

Use these steps when performance drops below the threshold:

1. **Isolate**: Run the current increment in isolation from the rest of the system.
2. **Test variants**: Compare all tracked variants. Find out if the failure occurs in one variant or in all variants.
3. **Analyze part outputs**: Check the intermediate results of each part.
4. **Check computational correctness**: Check gradients, derivatives, or equivalent operations.
5. **Apply the mitigation**: Use the strategy that you wrote for the critical checkpoint.

## Session flow

```
SESSION START
├── Load: Master Prompt (Prompt 0)
├── Run: Increment 1 [Simple baseline]
│   └── Check: Quantitative metrics in green zone
├── Run: Increment 2 [Add capability A]
│   └── Check: Metrics maintained
├── Run: Increment 3 [CRITICAL: Complex operation]
│   ├── Check: Metrics maintained
│   └── If failure: Run isolation test
├── Continue through Increment N
└── SESSION END: Record all metrics in tracking matrix

NEXT SESSION START
├── Load: Master Prompt (Prompt 0) - Same document
├── Review: Tracking matrix from previous session
└── Continue from last successful increment
```

Source: Novelty-Assessment-Report_-Module-of-Thought-for-S-3.pdf
