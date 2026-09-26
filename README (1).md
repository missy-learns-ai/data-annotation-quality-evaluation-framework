# LLM Evaluation and Data Quality

A portfolio case study on evaluating language-model responses, reviewing function-calling workflows, and designing enterprise tasks that can be graded consistently.

## Read the report

**[Portfolio Report (PDF)](Portfolio_Report.pdf)**

The report includes use-case context, evaluation methods, findings, and recommendations. This repository contains only the portfolio report and this README.

## What the project covers

| Area | Focus |
| --- | --- |
| A/B response evaluation | Independent scoring of three response pairs using atomic requirements, weighted criteria, critical-failure gates, and relative preferences. |
| Function calling | Tool availability, input provenance, dependency order, task completeness, efficiency, and conditional fallback. |
| Enterprise task design | Incident response, calendar booking, and headcount reporting, with attention to clear requirements and verifiable outcomes. |
| Annotation guidance | Reference tasks and a customer-contract guideline for evidence-based, deterministic grading. |

## Approach

1. Extract the requirements before evaluating responses.
2. Ground each judgment in observable evidence.
3. Distinguish structural failures from quality limitations.
4. Evaluate responses independently before comparing them.
5. Align prompts, tool capabilities, environment data, and grading criteria.
6. Check both correct action and correct non-action.

## Key findings

- Strong presentation cannot compensate for answering the wrong entity or task.
- Valid tool calls do not guarantee that the complete user request is achievable.
- More detail, sources, or tool calls do not independently establish better quality.
- Ambiguous dates, missing constraints, and inconsistent metric definitions undermine reliable grading.

## Scope

This is an analytical portfolio case study, not a software package or an aggregate model benchmark. Scores reflect the reviewed samples. The weighting and rating rules are project-specific calibration choices. Workflow code in the report is illustrative pseudocode.

References supporting the evaluation approach and tool-use concepts are included in the PDF. Company references and personal contact details are omitted from the portfolio version.

## Author

Pratistha Thapa
