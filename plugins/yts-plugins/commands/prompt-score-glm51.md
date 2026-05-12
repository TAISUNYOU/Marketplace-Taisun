---
description: Score Prompt for GLM-5.1
---

# GLM-5.1 Prompt Quality Check

Use this rubric to score whether a prompt is optimized for GLM-5.1 with both high performance and low total token usage across the full execution. Score each category, then total to 100.

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
| English-only output | 7 | The prompt is fully English while preserving the meaning of Korean, English, or mixed source input. |
| Intent preservation | 8 | The user's true goal, deliverable, scope, constraints, and audience are preserved without distortion. |
| Token efficiency | 14 | The prompt removes redundancy while adding only instructions that reduce total execution tokens, retries, and unnecessary output. |
| Clear task framing | 8 | The prompt states one clear objective, the expected deliverable, and the task boundary near the top. |
| Output contract | 10 | The required format, length, schema, sections, or final answer shape is explicit enough to avoid correction turns. |
| Reasoning control | 10 | The prompt tells GLM-5.1 when to think internally, when to answer directly, and not to reveal hidden reasoning by default. |
| GLM-5.1 fit | 10 | The prompt uses GLM-5.1 strengths: long-horizon execution, agentic coding, tool use, structured output, context caching, and long-context handling where relevant. |
| Tool-use discipline | 8 | Tool calls are bounded, necessary, and outcome-driven; repeated or low-value tool calls are discouraged. |
| Context discipline | 7 | Long context is prioritized, deduplicated, and scoped so the model does not process irrelevant material equally. |
| Ambiguity handling | 6 | The prompt asks for at most essential clarification; otherwise it makes conservative assumptions and proceeds. |
| Verification efficiency | 7 | The prompt includes targeted validation that catches likely errors without demanding excessive analysis or reporting. |
| Stop condition | 5 | The prompt tells the model when to stop and prevents extra summaries, alternatives, or process narration unless requested. |

## Score Interpretation

- 90-100: Excellent. Strongly optimized for GLM-5.1 quality and total-token efficiency.
- 80-89: Good. Likely efficient and reliable, with minor gaps.
- 70-79: Usable. Needs stronger output constraints, reasoning control, or token discipline.
- 60-69: Weak. The model may overthink, overuse tools, or require follow-up corrections.
- Below 60: Poor. Rewrite before using with GLM-5.1.

## Diagnostic Checklist

Answer yes or no:

- Is the prompt entirely in English?
- Is the deliverable stated in one clear sentence?
- Are repeated instructions removed?
- Are constraints expressed as compact bullets?
- Does it define the exact output format?
- Does it specify output length or brevity expectations?
- Does it prevent prompt restatement and process narration?
- Does it tell the model to think internally without exposing hidden reasoning?
- Does it disable or minimize deep reasoning for simple tasks?
- Does it limit tool use to cases where tools change the answer?
- For coding tasks, does it require relevant inspection, minimal implementation, targeted checks, and concise reporting?
- For research tasks, does it require only necessary evidence and current/primary sources?
- For long-context tasks, does it rank or filter context by relevance?
- Does it include a clear stop condition?

## Common Failure Patterns

- The prompt is short but ambiguous, causing follow-up turns.
- The prompt is long because it repeats the same priority in different words.
- It asks for full reasoning traces, causing unnecessary output tokens.
- It gives no output length or format, leading to bloated answers.
- It encourages excessive tool calls.
- It includes large context without relevance ranking.
- It asks many clarifying questions when a conservative assumption would work.
- It optimizes the initial prompt length but increases total task tokens.
- It omits verification, causing correction turns later.

## Pass Criteria

A prompt is GLM-5.1-ready when it scores at least 85 and has no zero-score category. For production coding, research, financial, legal, medical, or other high-stakes tasks, require at least 90 plus explicit verification and source/assumption rules.
