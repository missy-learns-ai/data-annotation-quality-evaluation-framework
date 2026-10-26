# LLM Evaluation and Data Quality

**A portfolio case study in response evaluation, function-calling quality, enterprise task design, and annotation consistency.**

**Research question:** How can we evaluate language-model responses and tool-calling workflows consistently, ensuring that models follow user instructions, produce accurate outputs, and complete tasks reliably?

**[Read the full portfolio report (PDF)](Portfolio_Report.pdf)**

## Why this project matters

A response can sound convincing yet answer the wrong question. A tool call can be valid yet fail to complete the user's task. And two reviewers can reach different conclusions if requirements or scoring rules are ambiguous.

This case study examines how to make evaluations **evidence-based, repeatable, and actionable**. It focuses on observable behavior: what the task required, what the model or workflow did, which requirements were met, and what should change.

## What's included

| Workstream | Scope |
| --- | --- |
| **A/B response evaluation** | Three model-response pairs, scored independently and then compared. |
| **Function-calling review** | Two supplied recipe workflows evaluated for structural validity and workflow quality. |
| **Workflow design** | Two author-designed recipe workflows illustrating parallel checks and conditional fallback. |
| **Enterprise task review** | Incident response, calendar booking, and headcount reporting tasks examined for clarity and verifiable outcomes. |
| **Annotation guidance** | Reference tasks and customer-contract grading rules designed to reduce reviewer ambiguity. |

## Evaluation approach

For response quality, I extracted **atomic, observable requirements** from the task and assessed each model independently before comparing the pair. Criteria were weighted by importance (**5 = critical, 3 = important, 1 = minor**) and scored for fulfilment on a **0–4 scale**. A weighted percentage provided a preliminary rating; **critical-failure gates** limited ratings when the model missed the core task, entity, or time period.

For tool use, I distinguished **structural validity** (enabled tools, correct contracts, available inputs) from **workflow quality** (tool fit, dependencies, completeness, efficiency, and auditability). I also checked whether a workflow correctly *avoided* actions when conditions were not met.

These weights, rating thresholds, and gates are **project-specific evaluation choices**, not a universal benchmark standard.

## A/B evaluation: key results

| Reviewed task | Model A | Model B | Finding |
| --- | --- | --- | --- |
| **Paris weather prediction** | 45% — Pretty bad | 75% — Pretty good | **B much better.** A used forecast evidence primarily for Paris, Texas rather than Paris, France. |
| **20 pros and 20 cons of owning a cat** | 81% — Pretty good | 88% — Pretty good | **B better.** A gave 19 items on each side; B better satisfied the quantity requirement. |
| **Environmental policy newsletter** | 82% — Pretty good | 68% — Okay | **A better.** B added France-specific detail but missed language, length, and deliverable requirements; both had factual issues. |

**What this illustrates:** Presentation, extra detail, or apparent thoroughness cannot compensate for failing an explicit user requirement. The detailed task questions in the PDF are **paraphrases**, not verbatim recovered prompts.

## Function-calling findings

| Supplied workflow | Structural check | Quality score | Assessment |
| --- | --- | --- | --- |
| Four servings within time and budget constraints | **Fail** | **3/10** | Requires redesign: a disabled scaling function and missing recipe/cost inputs made the plan unreliable. |
| Pancakes for six with gluten-free flour substitution | **Pass** | **7/10** | Requires revision: the scaling tool did not update quantities, limiting accurate grocery planning. |

I also designed reference workflows to test **independent/parallel checks** and **conditional fallback**: try a preferred recipe first, and only evaluate the alternative if the first is not feasible. These designs illustrate evaluation logic; they are not deployed integrations.

## Enterprise tasks and grading design

Three enterprise workflows exposed different specification problems:

- **HTTP 503 incident response:** resolve owner identity, timing, and existing incident state before creating or grading follow-up actions.
- **Calendar booking:** fix meeting duration and date interpretation; define what to do if no common slot exists.
- **Headcount reporting:** distinguish year-over-year growth from cumulative growth before checking charts or conclusions.

The report also includes author-designed lead-prioritization and incident-summary tasks, plus a customer-contract annotation guideline. Across these examples, effective grading requires a defined target population, evidence sources, ranking and tie-break rules, expected outputs, and **correct non-action**.

## Main takeaways

- Judge the **core task**, not just fluency or presentation.
- Confirm that tools **exist and behave as assumed** before trusting a workflow.
- Make dates, business rules, and metrics **unambiguous**.
- Tie every material rating to **a requirement and observable evidence**.
- Grade both **what the system does and what it deliberately does not do**.

## Scope and transparency

This repository contains a **portfolio analysis**, not executable evaluation software or a large-scale model benchmark. Reported scores concern the reviewed samples. Full original prompts, model transcripts, and item-level score sheets are not included; reconstructed questions and illustrative calculations are labeled in the PDF. References and detailed recommendations appear in the report.

## Author

**Pratistha Thapa**
