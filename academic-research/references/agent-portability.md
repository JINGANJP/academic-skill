# Agent Portability

## Purpose

Use this file to adapt the academic-research workflow to agents with different tool and memory limits.

The workflow stays the same. What changes is how much of it can be executed directly inside the target agent.

The portability rule is simple: choose the lightest viable execution mode for the target agent and the current task.

## Capability Mapping

### Full Agent: web plus files plus code execution

Examples: coding agents with browsing, repository access, and terminal execution.

Use the light, standard, or long-thesis workflow as needed:

- browse for literature and datasets
- inspect repository or benchmark code when relevant
- test data access or code feasibility where possible
- maintain a citation ledger and evidence pack during drafting

### Research Agent: web plus long context, but limited file or code execution

Examples: chat agents that can browse and read long documents but cannot run code.

Use the full literature and idea workflow, but treat implementation feasibility more cautiously:

- verify whether code exists
- inspect repository documentation when possible
- label runnable-status claims as `Needs execution check` if they cannot be tested

### Chat Agent: no browsing, no files, prompt-only

Use only for:

- idea framing from user-provided materials
- structure planning
- rewriting or polishing text the user already supplied

Do not claim to verify:

- current literature coverage
- novelty
- dataset availability
- code reproducibility
- citation authenticity beyond what the user provides

If browsing is unavailable, state the limitation explicitly and downgrade the task from verified research to assisted drafting.

## Adaptation Rules

- If the task is small, do not imitate a thesis-scale workflow.
- If the agent cannot browse, remove any promise of literature verification.
- If the agent cannot inspect files or repositories, treat code feasibility as provisional.
- If the agent cannot maintain persistent memory, restate the active citation ledger and idea shortlist in every major continuation prompt.
- If the agent has a short context window, keep the field memo compact and summarize references in a consistent short schema.
- If the user already has a fixed topic, validate that topic instead of forcing a fresh ideation stage.
- If the task does not need new data, do not introduce crawler or data-collection steps.

## Minimal Continuation State

When moving between prompts or platforms, carry forward only:

- chosen discipline and subfield
- target artifact, language, and scope
- selected mode: light support, standard project, or long thesis
- surviving idea shortlist or the selected idea
- field memo
- retained literature set
- citation ledger
- current outline

This is usually enough to continue without reloading everything.

## Safe Claims By Capability

### Safe to claim only after real verification

- "this paper exists"
- "this dataset is available"
- "this repository is runnable"
- "this idea appears underexplored"
- "this metric is standard in the field"

### Safe to claim as informed synthesis

- "this topic appears promising based on the visible evidence"
- "this method likely fits the research question"
- "the literature suggests a gap around this combination"

### Mark as open questions when unverified

- hidden data-access restrictions
- undocumented preprocessing burden
- missing benchmark details
- unclear licensing
- ambiguous replication cost

## Recommended Packaging Outside Codex

If another platform supports a system prompt and task prompt:

1. paste `universal-agent-spec.md` into the system or developer layer
2. use the kickoff and stage prompts from `agent-prompt-pack.md`

If another platform supports only one prompt:

1. use the `Lightweight Single-Prompt Variant`
2. append the current task details and any user-provided sources

If another platform supports custom project instructions:

1. store the global rules there
2. keep stage-specific prompts in reusable snippets
