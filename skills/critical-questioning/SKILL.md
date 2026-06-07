---
name: critical-questioning
description: Use when the user asks to analyze, audit, diagnose, or strengthen arguments in articles, speeches, comments, reports, essays, or viewpoints; identify reasoning gaps, weak evidence, hidden assumptions, misleading language, omitted information, alternative explanations, or ways to complete the argument. Do not trigger for ordinary summarization, polishing, rewriting, or fact lookup unless the user asks to evaluate the argument or persuasive strength.
---

# Critical Questioning

Use this skill to produce a constructive argument-audit report inspired by the critical-questioning method in *Asking the Right Questions*. The goal is to evaluate whether the provided text's own reasoning supports its conclusion, not to decide the user's final stance.

## Defaults

- Scope: support short viewpoints, long articles, speeches, comments, reports, and essays.
- Default target: medium-to-long text.
- Default depth: deep internal analysis using the question chain, with concise external reporting.
- Tone: constructive. Preserve reasonable parts of the original argument while identifying gaps.
- Severity: use only `Major Issues` and `Minor Issues`.
- Fact checking: analyze the internal argument by default. Suggest verification when key facts, data, quotes, expert claims, news events, or high-stakes domains matter.
- Output language: match the user's language by default. Use the Chinese report structure for Chinese requests or Chinese source text unless the user asks for English. Use the English report structure for English requests or when explicitly requested.
- Saving: do not save outputs unless the user explicitly asks to save a note or file.

## Workflow

1. Identify the core claim, conclusion, and scope.
2. Map the argument: issue, conclusion, reasons, evidence, key terms, assumptions.
3. Run the deep question chain from `references/question-chain.md`.
4. Check the strongest opposing view as a fixed step:
   - What would a reasonable critic challenge first?
   - Has the author addressed the strongest counterargument?
   - Are there alternative explanations?
   - Is the evidence one-sided or selectively chosen?
5. For long inputs, use layered analysis:
   - Extract the whole-text thesis.
   - Segment by section, paragraph group, or major claim.
   - Audit each segment for local problems.
   - Merge repeated issues into a concise final report.
6. Output the compact report template from `references/report-template.md`, choosing the Chinese or English structure according to the output language rule.

## Conditional Behavior

- If the text is strongly emotional, ideological, promotional, or propagandistic, first note that it has a strong persuasive posture, then identify how loaded words, labels, fear, anger, identity appeals, or moral pressure affect the reasoning.
- If the user says the result is for discussion, interview, debate, review, feedback, or asking the author, add `Follow-Up Questions`.
- If the original conclusion is clearly overgeneralized, binary, causally overstated, or under-supported, add `More Defensible Conclusion`.
- If the text relies on facts, data, news, expert claims, medical, legal, financial, or other high-stakes content, add `Analysis Boundary` and recommend specific items to verify.

## Output Rules

- Do not merely list flaws; include what would complete or strengthen the argument.
- Do not substitute your own final stance for the user's judgment.
- Use conditional language for the overall judgment: "Based on the evidence in the provided text..."
- Avoid turning every issue into a formal fallacy label. Explain the practical reasoning problem.
- Keep the report scannable. If the input is short, keep the output proportionally short.
- Do not browse or fact-check unless the user explicitly asks or the governing environment requires verification for high-stakes or current claims.

## References

- For the internal audit checklist, read `references/question-chain.md`.
- For the default report shape and optional sections, read `references/report-template.md`.
