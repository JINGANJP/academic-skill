# Idea Validation

## Goal

Use this reference after initial field learning. The purpose is to prevent weak or unexecutable ideas from surviving just because they sound interesting.

## Validation Dimensions

Score each candidate idea on these dimensions:

| Dimension | What to check |
| --- | --- |
| Literature overlap | Is the same idea already heavily explored? |
| Novelty shape | Is the contribution new question, new data, new method, new setting, or new synthesis? |
| Data access | Can the data be obtained legally and realistically? |
| Method fit | Does the chosen method match the question and evidence type? |
| Execution cost | Are compute, time, tools, and implementation burden manageable? |
| Evaluation path | Can success or failure be measured clearly? |
| Reproducibility | Can the analysis or experiment actually be rerun? |
| Contribution value | Would the result matter even if it is negative? |

## Kill Criteria

Discard an idea when one or more of these hold:

- the literature already contains many near-identical papers with little room for differentiation
- the key data appears inaccessible, proprietary, unethical, or too expensive
- the experiment depends on tools, code, or infrastructure that the user is unlikely to run
- the contribution is only cosmetic, such as swapping a dataset or renaming an existing method
- the evaluation metric is vague or the result would be hard to interpret
- the idea requires causal claims but only weak correlational evidence is realistically available

## Domain Checks

### Economics and Finance

Check:

- identification strategy
- endogeneity risk
- data provenance and coverage
- policy or theoretical significance
- robustness and falsification opportunities

### Computer Science and AI

Check:

- dataset and benchmark access
- baseline availability
- code dependency complexity
- compute requirements
- reproducibility path
- ablation feasibility

### Medicine and Public Health

Check:

- study design appropriateness
- ethics and patient-data constraints
- endpoint clarity
- evidence hierarchy
- sample availability
- feasibility without clinical infrastructure

## Survivor Format

Each surviving idea should be reported as:

```text
Idea title:
Research question:
Contribution type:
Why now:
Likely data:
Likely method:
Closest related work:
Main novelty:
Main implementation risk:
Why it remains viable:
```

## Ranking Heuristic

Prefer ideas that satisfy all of the following:

- clearly different from the most obvious existing papers
- realistic data path
- realistic execution path
- clear evaluation logic
- academically meaningful even if results are mixed
