# Academic Skill

An academic research and paper-writing skill for Codex and other prompt-driven agents.

This project is built for a simple goal: help an agent produce academic work that is actually useful, not just polished-looking text. Instead of jumping straight into drafting, it emphasizes task alignment, sufficient evidence, real references, and lightweight execution by default.

## What It Does

- Supports academic tasks in English, Chinese, and bilingual workflows
- Works across fields such as economics, finance, computer science, AI, medicine, public health, and social science
- Learns the field before drafting when the task requires real domain grounding
- Filters weak or noisy sources instead of padding outputs with low-value material
- Validates research directions, methods, and data paths when needed
- Supports long-form writing by splitting large projects into manageable modules
- Strengthens empirical work with data collection and cleaning when the task truly needs it
- Keeps citation use grounded in checked sources rather than fabricated references

## Why This Skill Is Different

Many writing-oriented prompts are good at generating academic-looking prose. They are much less reliable at deciding:

- whether the literature base is deep enough
- whether the references are strong enough for the task size
- whether the method or empirical design is convincing
- whether the data is sufficient to support the claim
- whether the user actually wanted a short section, a chapter, or a thesis-scale workflow

This skill is designed to handle those decisions more deliberately.

Its working principles are:

- align with the user's real assignment first
- choose the lightest workflow that can still satisfy the task
- deepen the research only when the task size or quality bar requires it
- keep the user involved at high-impact decision points
- avoid fake citations, shallow idea inflation, and evidence-poor drafting

## Execution Modes

The skill intentionally does not treat every request as a full thesis project.

- `Light Support`: for polishing, a single section, a short memo, or a narrow research question
- `Standard Project`: for proposals, literature reviews, chapter drafts, and medium-size paper workflows
- `Long Thesis`: for masters theses, dissertations, or other clearly large manuscripts that need modular drafting

This keeps small tasks fast and large tasks manageable.

## Repository Structure

- `academic-research/SKILL.md`
  The main skill file for Codex
- `academic-research/agents/openai.yaml`
  Display metadata for the skill
- `academic-research/references/`
  Supporting references for field learning, idea validation, citation discipline, writing patterns, portability, and templates
- `academic-skill-README.md`
  Chinese overview README
- `academic-skill-README-portable.md`
  Chinese portable / cross-agent overview

## Best Fit

This repository is especially useful for:

- students preparing thesis topics, proposals, literature reviews, and chapter drafts
- researchers who want a better evidence-grounded workflow before drafting
- users who want agent assistance without letting the agent bluff its way through citations or methods
- teams adapting one academic workflow across Codex, Claude Code, or other custom-prompt agents

## Quick Start

Example prompt:

```text
Use $academic-research to align the task, choose the lightest suitable workflow, learn the literature on digital finance, validate feasible directions, and draft a Chinese thesis-style literature review.
```

Another example:

```text
Use the academic research workflow. First align the task, choose the lightest suitable mode, build a field memo on healthcare LLM evaluation, then filter the literature, validate feasible directions, and stop for my selection before drafting.
```

## Cross-Agent Use

Although the main entry point is written for Codex, the workflow is also portable.

Useful files:

- `academic-research/references/universal-agent-spec.md`
  Platform-neutral operating contract
- `academic-research/references/agent-prompt-pack.md`
  Ready-to-paste prompts for other agents
- `academic-research/references/agent-portability.md`
  Guidance for adapting the workflow to agents with different browsing, file, and execution capabilities

## Writing Support

The repository includes dedicated support for Chinese academic writing, including:

- shared Chinese academic writing guidance
- Chinese thesis-style guidance
- Chinese journal-style guidance

These are meant to improve naturalness and fit, not to force every task into one template.

## Caution

This skill can improve rigor and structure, but it does not replace the researcher's responsibility for the final argument, evidence base, citation accuracy, ethics, or field-specific standards.

That matters especially in high-stakes areas such as medicine, public health, and policy research.
