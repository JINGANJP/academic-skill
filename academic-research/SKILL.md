---
name: academic-research
description: Interactive academic research and writing workflow for scholarly tasks in English, Chinese, bilingual Chinese-English, or other languages. Use when Codex must align closely with the user's target output, learn the field, collect sufficient references, strengthen methods or empirical design, gather or clean data when needed, and draft papers, theses, proposals, literature reviews, or chapter-level outputs without rushing or fabricating evidence.
---

# Academic Research

## Overview

Use this skill as an interactive academic production workflow, not as a generic text generator.

The goal is not merely to produce something that looks like a paper. The goal is to help the user produce work that is better aligned with their real target:

- the right artifact
- the right language and style
- enough words for the assignment
- enough references for the scale of the task
- enough data, experiments, or empirical support to be convincing
- enough user feedback along the way that the final output does not drift

This skill should bias toward depth, sufficiency, and traceability. It should never rush to a polished-looking but under-supported result.

This skill is written for Codex, but the workflow is portable. When adapting it to another agent platform, use [references/universal-agent-spec.md](references/universal-agent-spec.md) as the platform-neutral contract, then use [references/agent-prompt-pack.md](references/agent-prompt-pack.md) for ready-to-paste prompts. Use [references/agent-portability.md](references/agent-portability.md) to adjust the workflow to the target agent's real tool limits.

## When To Use This Skill

Use this skill when the user asks for any of the following in a named scholarly field or academic context:

- thesis, dissertation, proposal, paper, literature review, related work, chapter draft
- topic selection, research idea generation, novelty checking, method planning
- experiment design, empirical design, dataset selection, benchmark review
- reference collection, annotated bibliography, evidence pack, citation-grounded writing
- Chinese academic writing, English academic writing, or bilingual academic outputs

If the user only wants light polishing of text they already wrote, this skill can still help, but it should stay lightweight and not force the full workflow.

## Core Principles

- Align with the user's real target before doing deep work.
- Increase user participation on important choices instead of silently making too many assumptions.
- Learn the field deeply enough to support the requested output volume and quality.
- Prefer fewer strong claims over many weak claims.
- Do not fabricate citations, data availability, methods, experiments, or novelty.
- Do not deliver thin writing just because the structure looks academic.
- If the task is large, split it into manageable modules and finish them one by one.
- If the evidence is thin, say so and strengthen the evidence instead of decorating the prose.
- Treat every execution as a serious attempt to satisfy the user's actual academic need, not as a quick content-generation task.

## Execution Modes

Choose the lightest mode that can still satisfy the user's request.

### Mode A: Light Support

Use this when the user wants polishing, one section, a short memo, a focused literature note, or quick structure help.

Default behavior:

- align scope briefly
- learn only the immediately relevant part of the field
- collect only the sources needed for the current section or task
- avoid unnecessary idea generation, thesis decomposition, or data collection
- finish the requested unit cleanly and stop

### Mode B: Standard Project

Use this when the user wants a proposal, literature review, chapter draft, topic design, method planning, or a medium-size paper workflow.

Default behavior:

- align scope
- build a sufficient literature base
- validate the direction if needed
- prepare an evidence pack
- draft in one or several modules depending on size

### Mode C: Long Thesis

Use this when the user wants a masters thesis, doctoral dissertation, or another clearly large manuscript.

Default behavior:

- align scope and target length
- build a broader literature and evidence base
- decompose the manuscript into modules
- draft and review one module at a time
- maintain continuity notes across turns

Do not use Mode C unless the task size actually requires it.

## Language Handling

- Match the user's working language by default unless the user asks for another output language.
- Search across languages when useful, especially when the user works in Chinese but the most authoritative literature is in English.
- Preserve bibliographic metadata in the source language. Do not translate author names, paper titles, journal titles, or dataset names inside citations unless the user explicitly asks.
- When drafting in Chinese, use natural Chinese academic discourse rather than English sentence order translated into Chinese.
- When the requested output language is Chinese, choose a style profile before drafting:
  - thesis profile for undergraduate, masters, doctoral, proposal, or long-form chapter writing
  - journal profile for CSSCI-style, core-journal-style, article submission, or compressed publishable prose

## Non-Negotiable Rules

- Browse for field learning, literature checking, dataset discovery, and citation verification whenever the task depends on real domain knowledge or current sources.
- Prefer primary and authoritative sources such as peer-reviewed papers, surveys, handbooks, textbooks, official datasets, technical documentation, clinical guidelines, government portals, and top-tier venues.
- Never fabricate citations, author lists, venues, years, datasets, repositories, metrics, experiments, or empirical claims.
- Separate source-backed statements from inference whenever the distinction matters.
- Do not use a single rigid template for every field. Adapt the structure to the discipline.
- Do not move ahead at full speed when the task contains hidden choices that materially affect the result.
- Do not present an idea, method, dataset, or experiment plan as convincing until it has passed a feasibility check.
- Do not pad weak work with empty wording to simulate depth.
- Do not stop at a superficially polished stage if the user asked for a deeper or larger deliverable.

## Default Workflow

Keep the workflow simple and interactive. Use the full version only when the task actually needs it.

### Step 1: Align The Target

Before deep research or drafting, confirm the real assignment and success criteria.

Clarify or infer:

- field and subfield
- target artifact
- target language
- target audience or venue
- expected word count or page count
- whether the user wants a full project or only one section
- whether the task needs theory, experiment, empirical analysis, case study, or mixed methods
- whether the user already has a topic, outline, data, references, or writing constraints

When the scope is large or ambiguous, pause and involve the user early instead of guessing too much.

### Step 2: Build A Sufficient Research Base

Learn the field before writing, but keep the process purposeful.

Actions:

1. Build a compact field memo from authoritative sources.
2. Identify canonical works and recent frontier work.
3. Filter out weak, duplicate, or low-value sources.
4. Keep collecting literature until the retained set is sufficient for the requested task size and depth.
5. Pay special attention to recent methods, current debates, benchmark practices, and evidence gaps so the final output is not outdated or generic.

For long or complex projects, maintain reusable working notes in the workspace when helpful, such as:

- field memo
- annotated bibliography
- citation ledger
- method notes
- chapter or section evidence maps

These notes should make later drafting easier and reduce repeated searching.

Do not create extra workspace notes by default for small one-off tasks. Create them only when they will clearly improve a longer or more complex project.

### Step 3: Validate The Research Direction

If the task involves topic selection, idea generation, method choice, experiment design, or empirical design, validate before drafting.

Check:

- literature overlap
- novelty shape
- data availability
- method fit
- execution cost
- evaluation clarity
- reproducibility
- academic value

When multiple viable directions remain, present the best options and involve the user in the choice instead of forcing a silent decision.

If the user already has a fixed topic or direction and is not asking for alternatives, keep this step minimal and validate the existing direction instead of generating extra options.

### Step 4: Strengthen Data And Evidence

When the output depends on experiments, empirical analysis, or data-driven claims, explicitly assess whether the available evidence is strong enough.

Actions:

1. Check whether existing data is sufficient in scale, coverage, and credibility.
2. If data is insufficient, ask the user what data volume or coverage is expected.
3. If appropriate and allowed, write collection scripts or crawlers to gather more data.
4. Clean, normalize, and document the collected data before using it for argumentation.
5. Report important limitations such as sampling bias, missing fields, access restrictions, licensing limits, or weak representativeness.

Do not pretend that a thin dataset supports a strong empirical conclusion.
Do not start writing crawlers or collection scripts unless the task genuinely needs more data and the user has indicated the expected scale or accepted the collection step.

### Step 5: Draft In Modules, Not In One Giant Leap

For large writing tasks, especially theses, do not attempt to generate the entire work in one pass.

Use modular drafting:

1. break the project into chapters, sections, or other manageable units
2. define the goal, evidence, and target length for each unit
3. draft one unit at a time
4. review and revise each unit before moving on
5. integrate the units and do a global consistency pass at the end

For masters theses or similarly large outputs:

- ask the user for the expected total word count or page count
- ask whether the user wants the whole thesis, selected chapters, or only a proposal-level version
- decompose the work into a practical sequence of smaller tasks
- expect each major unit to still be substantial when needed, often several thousand words
- keep a running outline and status tracker so the project can continue cleanly across turns

### Step 6: Review Against The Real Requirement

Before considering the task done, check the result against the user's actual quality bar.

Minimum questions:

- Is the word count or page count actually adequate?
- Are the references sufficient for the scale of the task?
- Are the methods, experiments, or empirical claims persuasive enough?
- Is the data base large and credible enough for the conclusions being made?
- Does the writing actually answer the user's assignment, not just the agent's preferred structure?
- Are the strongest limitations still visible rather than hidden by smooth prose?

If the answer is no, continue improving instead of pretending the job is finished.
If the answer is yes and the user asked for only a limited deliverable, stop cleanly instead of expanding the task unnecessarily.

## User Participation Checkpoints

Increase user participation when the decision would significantly change the outcome.

Default checkpoints:

1. after scope alignment
2. after topic or idea shortlist
3. before large-scale data collection, crawling, or code-heavy empirical work
4. after thesis decomposition or chapter plan
5. after each major module in a long-form writing project

Do not interrupt the user for trivial choices. Use checkpoints for high-impact decisions.

If the user's request is narrow and clear, reduce checkpoints and keep momentum.

## Long-Form Thesis Guidance

Use this section when the user wants a masters thesis, doctoral dissertation, or another large academic manuscript.

The default strategy is:

1. determine the target length and deliverable scope
2. build the thesis-level outline
3. decide the writing order
4. prepare chapter-level evidence packs
5. draft chapter by chapter or section by section
6. run cross-chapter checks for terminology, citations, argument consistency, and contribution framing
7. assemble and revise the full manuscript

Do not promise a strong large-scale thesis if the literature base, data base, or evidence plan is still thin.

## Data Collection And Cleaning Guidance

Use this section when the task requires more evidence than the user currently has.

- Ask what scale of data is needed before collecting blindly.
- Ask about source boundaries and compliance constraints when they matter.
- Prefer legitimate, stable, documented sources.
- If crawling is appropriate, write focused collection scripts rather than vague instructions.
- After collection, perform basic cleaning and explain what was removed, normalized, or merged.
- Keep a short data note covering source, date range, fields, size, and major limitations.

## Reference Depth Expectations

Reference sufficiency should scale with the task.

- For a short section or focused memo, a compact but high-quality set may be enough.
- For a literature review, proposal, thesis chapter, or full thesis, the literature base should be broader, deeper, and better organized.
- When the project is long-running, create reusable reference notes if that will improve consistency and recall.
- Learn not only the field's established literature but also recent frontier methods and debates, so the final output is not stale.

Do not stop the learning process too early when the user clearly needs a more substantial academic product.
Do not continue literature expansion once the source base is already sufficient for the current scoped deliverable.

## Quality Standard

This skill must resist three failure modes:

- under-length writing
- under-supported claims
- under-developed methods, experiments, or empirical design

The correct response to these failures is not prettier wording. The correct response is to strengthen the research base, data base, structure, and user alignment.

## Domain-Specific Expectations

- Economics and finance: check identification strategy, mechanism clarity, data provenance, robustness, endogeneity risk, and policy relevance.
- Computer science and AI: check benchmark fit, baseline choice, dataset access, code feasibility, compute cost, ablations, and reproducibility.
- Medicine and public health: check study design, endpoints, ethics, evidence level, data restrictions, and whether claims are observational or causal.
- Social sciences: check theory framing, construct validity, sampling, measurement quality, contextual boundaries, and causal overreach.

## Reference Files

- Read [references/domain-learning.md](references/domain-learning.md) for source-selection and field-learning guidance.
- Read [references/idea-validation.md](references/idea-validation.md) for feasibility screening and domain-specific idea checks.
- Read [references/review-workflows.md](references/review-workflows.md) for literature synthesis and research-gap writing.
- Read [references/citation-and-writing.md](references/citation-and-writing.md) for citation integrity and section discipline.
- Read [references/universal-agent-spec.md](references/universal-agent-spec.md) when the workflow must run outside Codex.
- Read [references/agent-prompt-pack.md](references/agent-prompt-pack.md) for ready-to-paste prompts for other agents.
- Read [references/agent-portability.md](references/agent-portability.md) when the target agent has different browsing, file, execution, or memory limits.
- Read [references/chinese-academic-writing.md](references/chinese-academic-writing.md) when the output language is Chinese or when the user wants more natural Chinese scholarly prose.
- Read [references/chinese-thesis-style.md](references/chinese-thesis-style.md) for Chinese undergraduate, masters, doctoral, proposal, or long-form thesis writing.
- Read [references/chinese-journal-style.md](references/chinese-journal-style.md) for Chinese CSSCI-style, core-journal-style, article-style, or compressed publishable prose.
- Read [references/output-templates.md](references/output-templates.md) for reusable templates covering planning, evidence packs, long-form decomposition, and drafting support.
