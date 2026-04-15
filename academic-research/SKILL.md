---
name: academic-research
description: Multilingual, domain-triggered academic research and paper-writing workflow for requests in English, Chinese, bilingual Chinese-English, or other languages about economics, finance, econometrics, computer science, AI, machine learning, systems, medicine, clinical research, public health, psychology, sociology, management, law, education, or other scholarly fields. Use when Codex must research a field before writing, study canonical and frontier literature, filter low-value sources, generate and validate research ideas, collect real references, summarize each cited work, plan data and experiments, and draft thesis or paper sections with real citations and academic structure.
---

# Academic Research

## Overview

Use this skill as a staged research agent, not as a generic writing assistant. The skill should activate when the user asks for topic design, idea generation, literature review, proposal writing, paper drafting, experiment planning, dataset selection, reference collection, or citation-grounded scholarly writing in a specific discipline, regardless of whether the request is written in English, Chinese, or another language.

The core rule is: learn the field first, narrow the evidence second, generate and validate ideas third, and only then write. Do not skip field learning, do not invent citations, and do not present an idea as viable until it has passed a feasibility screen.

This skill is written for Codex, but the research protocol is portable. When adapting the workflow to another agent platform, use [references/universal-agent-spec.md](references/universal-agent-spec.md) as the platform-neutral operating contract, then use [references/agent-prompt-pack.md](references/agent-prompt-pack.md) to paste the workflow into that agent's system, developer, or task prompt. Use [references/agent-portability.md](references/agent-portability.md) to map the workflow onto the agent's real tool limits.

## Triggering Guidance

Treat requests as high-confidence matches when they combine an academic artifact with a domain keyword or subfield keyword. This applies to direct English terminology, translated terminology, and bilingual phrasing. Examples include:

- disciplines such as economics, finance, econometrics, accounting, computer science, machine learning, NLP, systems, cybersecurity, medicine, oncology, radiology, epidemiology, public health, psychology, sociology, education, management, political science, or law
- translated or localized discipline terms, such as Chinese-language subject names and task names that refer to the same scholarly fields
- artifacts such as paper, thesis, dissertation, proposal, related work, literature review, experiment design, dataset, benchmark, hypothesis, identification strategy, robustness, ablation, peer review, or citations
- translated artifact names, such as paper-writing, topic selection, literature review, reference collection, experiment design, or method comparison expressed in another language
- intents such as find a topic, propose ideas, verify novelty, read papers, summarize literature, collect references, or draft an academic section

If the request is about a scholarly deliverable in a named field, use this skill even if the user does not explicitly say "academic writing".

## Language Handling

- Match the user's working language by default for explanations, idea menus, outlines, and drafts, unless the user requests another output language.
- Search across languages when useful. For example, pair the user's language with canonical English discipline terms because many primary sources, datasets, and benchmarks are indexed in English even when the request is in Chinese.
- Preserve original bibliographic metadata in the language used by the source. Do not translate author names, paper titles, journal titles, or dataset names inside citations unless the user explicitly asks for translated references.
- When drafting in Chinese or another non-English language, keep the original technical term in parentheses at first mention if translation ambiguity could confuse the reader.
- When sources exist in multiple languages, prefer the version that is most authoritative, most complete, and most citable.
- If a user asks for bilingual output, keep the research logic shared but separate the final writing cleanly by language instead of mixing sentence by sentence.
- When the requested output language is Chinese, use Chinese academic discourse conventions rather than literal translation from English argument structure.
- For Chinese drafting, prefer compact but formal sentence flow, explicit paragraph topic sentences, and evidence-linked transitions equivalent to "existing studies show", "furthermore", "by contrast", "it is worth noting that", and "in sum".
- For Chinese drafting, avoid awkward hybrid phrasing, direct English word order, inflated claims, and repetitive connectors.
- For Chinese drafting, choose a Chinese style profile before writing: use the thesis profile for undergraduate, masters, doctoral, proposal, or long-form dissertation writing; use the journal profile for CSSCI-style, core-journal-style, article submission, or compressed publishable prose.

## Non-Negotiable Rules

- Always browse for field learning, source verification, literature discovery, and citation checking when the user asks for domain knowledge, current literature, data sources, experiments, or references.
- Prefer primary and authoritative sources: peer-reviewed papers, survey papers, handbooks, textbooks, official datasets, technical documentation, clinical guidelines, government or institutional data portals, and top-tier conference or journal pages.
- Exclude noisy sources unless they are the only lead to a primary source. Low-value sources include SEO blogs, generic content farms, thin news rewrites, unattributed summaries, and papers with weak relevance or unclear credibility.
- Never fabricate citations, author lists, venues, years, datasets, code repositories, metrics, trial registrations, or empirical claims.
- Separate source-grounded statements from your synthesis. Use labels such as `Source-backed`, `Inference`, `Open question`, and `Needs verification` when the distinction matters.
- Do not move from ideation to writing until the user has chosen one of the surviving ideas, unless the user explicitly asks for a fully autonomous choice.
- When a field is high-stakes, especially medicine or public health, increase caution, prefer higher levels of evidence, and surface ethical, regulatory, or clinical limitations.
- Do not confuse translation convenience with source verification. A translated summary is not a substitute for checking the underlying source.

## End-to-End Workflow

Follow these stages in order unless the user requests only one stage.

### Stage 1: Field Learning

Identify the exact discipline and subfield first. Build a compact field map before generating any ideas.

Actions:

1. Infer the subfield, research object, typical methods, common datasets, and expected paper structure.
2. Browse authoritative sources to learn foundational knowledge and current frontiers, using multilingual queries when needed.
3. Read classic or canonical works to understand the field's baseline assumptions.
4. Read influential recent work to understand what the frontier is actually debating now.
5. Build a short evidence memo covering:
   - key questions in the field
   - dominant methods
   - common datasets or evidence sources
   - recurring limitations
   - writing norms in that discipline
   - important cross-language terminology needed for later searches and drafting

Use [references/domain-learning.md](references/domain-learning.md) for source selection and browsing rules.

### Stage 2: Noise Filtering

Do not read everything. Curate.

Actions:

1. Remove irrelevant, weak, duplicate, off-topic, or low-credibility materials.
2. Keep sources that are canonical, methodologically influential, highly cited, top-venue, systematic, or directly aligned with the user's target problem.
3. Explain why each retained source matters: theory, method, dataset, benchmark, critique, or frontier direction.
4. Prefer a smaller clean set over a large noisy set.

### Stage 3: Idea Generation and Validation

Generate more ideas than you need, then screen aggressively. The final deliverable for this stage is exactly 3 viable ideas unless the user requests a different number.

Actions:

1. Propose a broad candidate set.
2. Score each candidate for:
   - novelty relative to visible literature
   - data availability
   - methodological feasibility
   - experimental or empirical tractability
   - code or implementation feasibility where relevant
   - evaluation clarity
   - academic value
3. Kill weak ideas early.
4. Keep only ideas that plausibly survive literature overlap and practical execution checks.
5. Present 3 viable ideas, each with:
   - title
   - core question
   - why it matters
   - likely method
   - likely data
   - main risk
   - why it appears viable

Use [references/idea-validation.md](references/idea-validation.md) for the scoring rubric and domain-specific feasibility checks.

Pause after presenting the 3 ideas and wait for the user's choice unless the user explicitly authorizes autonomous continuation.

### Stage 4: Evidence Pack After Idea Selection

Once the user selects an idea, collect the materials needed to support real writing.

Actions:

1. Find relevant datasets, repositories, benchmarks, archives, or document corpora.
2. Find real references that directly support the chosen problem, method, and positioning.
3. Read each retained reference closely enough to summarize:
   - the problem it studies
   - the method or design it uses
   - the main finding or claim
   - its limitation
   - why it matters for the chosen idea
4. Build a citation ledger so every planned citation is traceable to a real source.
5. Remove references that you could not verify or that turn out to be only weakly related.

Use [references/review-workflows.md](references/review-workflows.md) to compare sources and [references/citation-and-writing.md](references/citation-and-writing.md) for citation integrity.

### Stage 5: Outline From Evidence

Before full drafting, convert evidence into a paper plan.

Actions:

1. Infer the discipline-appropriate paper structure from the literature you reviewed.
2. Build a section outline that matches the field. Examples:
   - economics: question, theory or mechanism, identification, data, empirical strategy, results, robustness, conclusion
   - computer science: problem, related work, method, experimental setup, results, ablations, limitations
   - medicine: background, objective, methods, results, discussion, limitations, ethics, conclusion
3. Assign evidence to sections so each major claim has support.
4. Note which claims are established, which are proposed, and which remain speculative.

### Stage 6: Academic Drafting

Draft only after the outline and evidence pack are ready.

Requirements:

- Follow academic paper conventions for the target discipline rather than using one universal template.
- Keep the final draft in the user-requested language, while preserving citation metadata in verified source form.
- Use real references only.
- Cite sources only when you have actually examined enough of the source to know what it says.
- Prefer synthesis over stitched summaries.
- Keep academic tone precise, sober, and evidence-driven.
- Preserve uncertainty where the evidence is incomplete.

Use [references/output-templates.md](references/output-templates.md) for output shapes and [references/citation-and-writing.md](references/citation-and-writing.md) for section and citation discipline.

If the final draft is in Chinese, read [references/chinese-academic-writing.md](references/chinese-academic-writing.md) first, then choose one of these:

- [references/chinese-thesis-style.md](references/chinese-thesis-style.md) for undergraduate, masters, doctoral, proposal, or chapter-style writing
- [references/chinese-journal-style.md](references/chinese-journal-style.md) for CSSCI-style, core-journal-style, or article-submission writing

## Domain-Specific Expectations

Adjust validation and writing to the field instead of forcing one template onto every problem.

- Economics and finance: look for identification strategy, theoretical mechanism, data provenance, robustness checks, endogeneity concerns, and policy relevance.
- Computer science and AI: look for benchmark fit, baseline choice, ablations, compute cost, code reproducibility, dataset licensing, and whether implementation is realistically runnable.
- Medicine and public health: look for study design, inclusion criteria, endpoints, ethics, evidence level, guideline alignment, and whether the claim is observational or causal.
- Social sciences: look for theory framing, construct validity, sampling, measurement quality, causal claims, and contextual limits.

## Required Deliverables By Stage

When the user asks for a full project, the skill should usually emit these deliverables in sequence:

1. field memo
2. filtered literature set
3. 3 validated ideas
4. evidence pack for the selected idea
5. section outline
6. draft with real citations

If the user asks for only one stage, complete that stage cleanly and stop.

## Reference Files

- Read [references/domain-learning.md](references/domain-learning.md) for authoritative-source selection, canonical-vs-frontier balancing, and field-mapping workflow.
- Read [references/idea-validation.md](references/idea-validation.md) for novelty screening, feasibility checks, and domain-specific validation criteria.
- Read [references/review-workflows.md](references/review-workflows.md) for literature synthesis, comparison matrices, and research-gap derivation.
- Read [references/citation-and-writing.md](references/citation-and-writing.md) for real-citation discipline, evidence traceability, and section-structure rules.
- Read [references/universal-agent-spec.md](references/universal-agent-spec.md) when the workflow needs to run outside Codex, or when another agent needs a platform-neutral research contract.
- Read [references/agent-prompt-pack.md](references/agent-prompt-pack.md) when you need ready-to-paste prompts for Claude Code, chat-based agents, or other general-purpose assistants.
- Read [references/agent-portability.md](references/agent-portability.md) when the target agent has different browsing, file, code-execution, or memory capabilities.
- Read [references/chinese-academic-writing.md](references/chinese-academic-writing.md) when the output language is Chinese or when the user wants more natural Chinese scholarly prose.
- Read [references/chinese-thesis-style.md](references/chinese-thesis-style.md) when the user is writing a Chinese undergraduate thesis, masters thesis, doctoral dissertation, proposal, or long-form chapter.
- Read [references/chinese-journal-style.md](references/chinese-journal-style.md) when the user wants Chinese CSSCI-style, Chinese core-journal-style, article-style, or more compressed publishable prose.
- Read [references/output-templates.md](references/output-templates.md) for reusable output shapes covering idea menus, evidence packs, summaries, and draft sections.
