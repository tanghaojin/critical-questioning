# Report Template

Choose the report language before writing:

- Use the Chinese structure for Chinese requests or Chinese source text unless the user asks for English.
- Use the English structure for English requests or when the user asks for English.
- Keep the analytical method identical across both structures.

## Chinese Structure

Default Chinese output uses this compact shape:

```markdown
## 核心主张

## 论证结构

## 主要问题

## 次要问题

## 补全清单

## 总体判断
```

Only include optional sections when applicable:

- `分析边界`: when claims depend on external facts, data, news, expert statements, or high-stakes domains.
- `可继续追问的问题`: when the user intends discussion, interview, debate, review, or author feedback.
- `更稳健的结论`: when the original conclusion is too broad, binary, causal, or under-supported.
- `强说服姿态提示`: when the text is emotional, promotional, ideological, or propagandistic.

Use these labels inside `论证结构`:

- 论题：
- 结论：
- 主要理由：
- 关键证据：
- 隐含前提：

Use conditional judgment in `总体判断`, for example:

- 在当前文本证据下，论证强 / 中等 / 弱。

## English Structure

Default English output uses this compact shape:

```markdown
## Core Claim

## Argument Structure

## Major Issues

## Minor Issues

## Completion Checklist

## Overall Assessment
```

## Section Guidance

### Core Claim

State the main claim in one or two sentences. If the text contains multiple claims, name the dominant one and mention secondary claims briefly.

### Argument Structure

Use concise bullets:

- Issue:
- Conclusion:
- Main reasons:
- Key evidence:
- Hidden assumptions:

### Major Issues

List issues that materially weaken the argument. Prefer 3-6 items. For each item, explain:

- What the problem is.
- Why it weakens the conclusion.
- What would be needed to repair it.

### Minor Issues

List issues that cause ambiguity, overstatement, incomplete framing, or local weakness but do not destroy the core argument.

### Completion Checklist

Always include. Make it actionable:

- Data or sources to add
- Keywords to define
- Hidden assumptions to explain
- Opposing views to address
- Alternative explanations to rule out
- Boundary conditions to add

### Overall Assessment

Use conditional strength:

- Based on the evidence in the provided text, the argument is strong / moderate / weak.
- The conclusion may become stronger if specific evidence, definitions, counterarguments, or boundary conditions are added.
- Do not tell the user what final stance they must take.

## Optional Sections

Add only when conditions are met:

```markdown
## Analysis Boundary
```

Use when claims depend on external facts, data, news, expert statements, or high-stakes domains. State that the report is based on the provided text and identify facts that need verification.

```markdown
## Follow-Up Questions
```

Use when the user intends discussion, interview, debate, review, or author feedback. Phrase questions neutrally and constructively.

```markdown
## More Defensible Conclusion
```

Use when the original conclusion is too broad, binary, causal, or under-supported. Offer a more conditional version without rewriting the whole text.

```markdown
## Strong Persuasive Posture Note
```

Use when the text is emotional, promotional, ideological, or propagandistic. Identify how rhetoric affects reasoning without dismissing the argument solely because it is emotional.
