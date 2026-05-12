---
description: Score Prompt for Qwen3.6-35B-A3B
---

# Qwen3.6-35B-A3B Prompt Quality Check

Use this rubric to score whether a prompt is well optimized for Qwen3.6-35B-A3B when quality matters more than token usage. Score each category, then total to 100.

## Scoring Scale

- 0: Missing or harmful
- 1: Very weak
- 2: Partial but unreliable
- 3: Adequate
- 4: Strong
- 5: Excellent

For weighted categories, convert the 0-5 score proportionally to the listed points.

## Rubric

| Category | Weight | What to Check |
|---|---:|---|
| English-only output | 8 | The prompt is fully English, while preserving Korean source meaning, nuance, and constraints. |
| Intent preservation | 8 | The transformed prompt keeps the user's real goal, deliverable, scope, audience, and constraints without distortion. |
| Clear objective | 8 | The task goal is concrete, measurable, and placed near the top of the prompt. |
| Context organization | 8 | Background, inputs, examples, and constraints are structured so the model can use long context without confusion. |
| Qwen3.6 fit | 12 | The prompt leverages Qwen3.6 strengths: agentic coding, long context, multimodal reasoning, structured output, and tool-use clarity when relevant. |
| Reasoning control | 10 | It asks for deep internal reasoning, decomposition, and verification without requesting hidden chain-of-thought disclosure. |
| Output contract | 10 | The final answer format is explicit: headings, schema, table, code block, file list, or exact deliverable rules. |
| One-pass completeness | 10 | The prompt includes enough detail, edge cases, assumptions, and acceptance criteria to get a usable result in one attempt. |
| Constraints and priorities | 8 | Hard requirements, soft preferences, exclusions, and priority order are explicit. |
| Verification requirements | 8 | The prompt tells the model how to check its own result, run tests, cite evidence, or validate correctness. |
| Ambiguity handling | 5 | The prompt tells the model when to make conservative assumptions, when to ask questions, and how to state assumptions. |
| Safety and factuality | 5 | The prompt discourages unsupported claims, fake citations, fabricated tool results, and overconfident answers. |

## Score Interpretation

- 90-100: Excellent. Strongly optimized for high-quality Qwen3.6 execution.
- 80-89: Good. Likely reliable, with minor gaps.
- 70-79: Usable. Needs more structure, verification, or task-specific detail.
- 60-69: Weak. May work, but one-pass quality is not dependable.
- Below 60: Poor. Rewrite before using with Qwen3.6-35B-A3B.

## Diagnostic Checklist

Answer yes or no:

- Is the prompt entirely in English?
- Does it state the exact role or expertise expected from the model?
- Does it define the final deliverable clearly?
- Does it include all relevant user constraints?
- Does it tell the model how to handle ambiguity?
- Does it include a validation or self-check step?
- Does it specify the output format?
- For coding tasks, does it require codebase inspection, implementation, tests, and changed-file reporting?
- For research tasks, does it require current/primary sources and explicit uncertainty handling?
- For multimodal tasks, does it require grounding claims in visible evidence?
- For long-context tasks, does it rank context by importance?

## Common Failure Patterns

- The prompt is only translated, not optimized.
- Korean nuance is lost during translation.
- The prompt asks for "best quality" but gives no acceptance criteria.
- The output format is vague.
- The model is asked to reveal full chain-of-thought instead of a concise rationale.
- Long context is pasted without hierarchy or retrieval cues.
- Tool use is mentioned but not bounded by rules.
- The prompt does not include verification steps.
- It underuses tokens even though quality is the priority.

## Pass Criteria

A prompt is considered Qwen3.6-ready when it scores at least 85 and has no zero-score category. For high-stakes coding, research, legal, medical, financial, or production tasks, require at least 90 and explicit verification criteria.
