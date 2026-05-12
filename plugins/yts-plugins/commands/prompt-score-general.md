---
description: Score Prompt for General Models
---

# General Model Prompt Quality Check

Use this rubric to evaluate whether a prompt follows the standards of the Professional Prompt Builder for general-purpose models. The goal is to measure whether the prompt is clear, complete, maintainable, tool-aware, and ready for reliable AI execution.

Score each category, then total to 100.

## Scoring Scale

- 0: Missing or harmful
- 1: Very weak
- 2: Partial but unreliable
- 3: Adequate
- 4: Strong
- 5: Excellent

For weighted categories, convert the 0-5 score proportionally to the listed points.

## Core Priorities

A high-quality general-model prompt should emphasize:

- Clear identity: filename, purpose, category, and concise description.
- Specific persona: role, expertise level, domain knowledge, tools, and qualifications.
- Measurable task definition: primary task, optional tasks, inputs, constraints, and success conditions.
- Explicit context handling: selected text, current file, workspace variables, input variables, dependencies, and referenced files.
- Step-by-step execution: a practical process the model can follow without guessing.
- Standards and constraints: coding conventions, frameworks, best practices, avoid-list, and instruction-file alignment.
- Precise output contract: format, file creation/modification rules, naming conventions, examples, and structure.
- Tool awareness: correct tools selected for file operations, search, execution, testing, browser work, repositories, or analysis.
- Technical configuration: suitable mode, model requirements only when necessary, and special constraints.
- Validation and recovery: success criteria, checks, error handling, and common failure modes.
- Maintainability: organized sections, consistent formatting, and easy future extension.
- AI consumption efficiency: concise but complete instructions that reduce ambiguity and follow-up turns.

## Rubric

| Category | Weight | What to Check |
|---|---:|---|
| Prompt identity and purpose | 8 | The prompt defines a clear filename or title, one-sentence description, category, and intended use. |
| Persona specificity | 8 | The model role is concrete, with expertise level, domain knowledge, tools, frameworks, and qualifications when relevant. |
| Task clarity | 10 | The primary task is explicit, measurable, and separated from secondary or optional tasks. |
| Input and context definition | 10 | Required user inputs, selections, files, variables, workspace references, and dependencies are clearly specified. |
| Step-by-step instructions | 10 | The prompt gives an actionable process the model can follow from discovery to final output. |
| Standards and constraints | 8 | Coding standards, frameworks, best practices, avoid-list items, and project instruction files are accounted for. |
| Output contract | 12 | The expected output format, file paths, naming conventions, modification rules, and structure are unambiguous. |
| Tool and capability fit | 10 | Required tools are listed and matched to the task without unnecessary or missing capabilities. |
| Technical configuration | 6 | Agent/ask/edit mode, model requirements, and special configuration are included only when useful. |
| Validation criteria | 8 | Success metrics, verification steps, common failure modes, and recovery behavior are defined. |
| Structure and maintainability | 5 | Sections are well organized, consistently formatted, and easy to update. |
| AI consumption efficiency | 5 | The prompt is concise, non-redundant, and structured to reduce ambiguity, retries, and unnecessary output. |

## Score Interpretation

- 90-100: Excellent. Production-ready for general-model use.
- 80-89: Good. Reliable, with minor gaps or refinements needed.
- 70-79: Usable. Works, but likely needs stronger structure, output rules, or validation.
- 60-69: Weak. Ambiguity or missing requirements may cause inconsistent results.
- Below 60: Poor. Rewrite before using.

## Diagnostic Checklist

Answer yes or no:

- Does the prompt have a concise description?
- Does it define the prompt's category or task type?
- Does it specify the model persona clearly?
- Does it state the primary task in measurable terms?
- Does it distinguish required work from optional work?
- Does it define what the user must provide?
- Does it specify whether `${selection}`, `${file}`, `${workspaceFolder}`, or `${input:*}` variables are used?
- Does it identify any dependency files, prompt files, or instruction files?
- Does it provide a step-by-step execution process?
- Does it include relevant standards, frameworks, libraries, or best practices?
- Does it include things to avoid?
- Does it define the exact output format?
- Does it say whether files should be created or modified?
- Does it define file naming and destination rules when file output is required?
- Does it include examples or few-shot guidance when useful?
- Does it list appropriate tools for the task?
- Does it avoid unnecessary tools?
- Does it specify `agent`, `ask`, or `edit` mode when relevant?
- Does it include validation or success criteria?
- Does it address common failure modes or recovery steps?
- Is the prompt easy to maintain and extend?

## Common Failure Patterns

- The prompt has a broad persona but no measurable task.
- The prompt asks for a deliverable but does not define the output format.
- Required inputs are implied instead of specified.
- Variables such as `${selection}` or `${file}` are used without explaining their role.
- Tool lists are copied generically instead of matched to the actual task.
- The prompt includes too many tools, causing unnecessary execution paths.
- The prompt lacks validation steps, causing follow-up correction turns.
- File creation or modification rules are missing.
- It includes examples that conflict with the stated requirements.
- It has long explanatory prose but few actionable instructions.
- It omits edge cases, error handling, or recovery behavior.

## Pass Criteria

A prompt is general-model ready when it scores at least 85 and has no zero-score category. For prompts that create or modify code, files, workflows, tests, or repository assets, require at least 90 plus explicit tool, validation, and file-output rules.
