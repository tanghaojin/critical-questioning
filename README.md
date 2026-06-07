# Critical Questioning

[English](README.md) | [中文](README.zh-CN.md)

Critical Questioning is a Codex skill for auditing arguments in articles, speeches, reports, essays, comments, and viewpoints. It is inspired by the critical-questioning method in *Asking the Right Questions*.

The skill helps an agent identify reasoning gaps, weak evidence, hidden assumptions, misleading language, omitted information, alternative explanations, and concrete ways to strengthen an argument.

## When To Use

Use this skill when a user asks to:

- analyze a viewpoint or article
- evaluate whether an argument is persuasive
- find reasoning flaws or missing evidence
- audit a speech, report, essay, or commentary
- strengthen an argument without rewriting it from scratch
- apply critical-questioning or critical-thinking analysis

It should not trigger for ordinary summarization, polishing, rewriting, or fact lookup unless the user asks to evaluate the argument or persuasive strength.

## What It Produces

The default report is compact but based on a deeper internal checklist:

- Core claim
- Argument structure
- Major issues
- Minor issues
- Completion checklist
- Overall assessment

For Chinese requests or Chinese source text, the skill uses a Chinese report structure by default. For English requests, it uses the English structure.

Optional sections are added only when useful:

- Analysis boundary
- Follow-up questions
- More defensible conclusion
- Strong persuasive posture note

## Skill Structure

```text
critical-questioning/
  README.md
  README.zh-CN.md
  skills/
    critical-questioning/
      SKILL.md
      agents/
        openai.yaml
      references/
        question-chain.md
        report-template.md
```

## Files

- `skills/critical-questioning/SKILL.md`: trigger description, workflow, default behavior, and output rules.
- `skills/critical-questioning/references/question-chain.md`: internal audit checklist based on critical questioning.
- `skills/critical-questioning/references/report-template.md`: bilingual report templates and optional section rules.
- `skills/critical-questioning/agents/openai.yaml`: UI metadata for Codex skill listings.

## Installation

Install from GitHub with the open skills CLI:

```bash
npx skills add https://github.com/tanghaojin/critical-questioning --skill critical-questioning
```

Install globally for Codex:

```bash
npx skills add https://github.com/tanghaojin/critical-questioning --skill critical-questioning -a codex -g
```

Non-interactive install:

```bash
npx skills add https://github.com/tanghaojin/critical-questioning --skill critical-questioning -a codex -g -y
```

Local validation from this repository:

```bash
npx skills add . --list
npx skills add . --skill critical-questioning -a codex -g
```

## Example Prompts

```text
Analyze the argument in this article and identify its major issues.
```

```text
帮我分析这篇文章的观点，找出论证漏洞和需要补全的地方。
```

```text
Use critical questioning to audit this speech before I publish it.
```

## Design Principles

- Evaluate whether the provided text supports its own conclusion.
- Do not decide the user's final stance.
- Preserve reasonable parts of the original argument.
- Distinguish major issues from minor issues.
- Always include a completion checklist.
- Recommend fact verification when claims depend on data, news, expert statements, or high-stakes domains.
