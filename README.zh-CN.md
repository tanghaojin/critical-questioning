# Critical Questioning

[English](README.md) | [中文](README.zh-CN.md)

Critical Questioning 是一个用于审查观点论证的 Codex skill，适用于文章、演讲、报告、论文、评论和观点文本。它的设计灵感来自《学会提问》中的批判性提问方法。

这个 skill 可以帮助 agent 识别论证缺口、薄弱证据、隐藏假设、误导性语言、遗漏信息、替代解释，并给出可操作的补全建议。

## 适用场景

当用户提出以下需求时，适合使用这个 skill：

- 分析一篇文章或一段观点
- 判断一个论证是否有说服力
- 找出推理漏洞或缺失证据
- 审查演讲稿、报告、论文或评论
- 在不直接改写全文的前提下补强论证
- 使用批判性提问或批判性思维方法分析文本

普通总结、润色、改写或事实查询不应默认触发这个 skill，除非用户明确要求评估论证或说服力。

## 输出内容

默认报告结构保持紧凑，但内部会使用更深的审查清单：

- 核心主张
- 论证结构
- 主要问题
- 次要问题
- 补全清单
- 总体判断

对于中文请求或中文原文，skill 默认使用中文报告结构。对于英文请求，默认使用英文结构。

只有在必要时才会加入可选栏目：

- 分析边界
- 可继续追问的问题
- 更稳健的结论
- 强说服姿态提示

## Skill 结构

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

## 文件说明

- `skills/critical-questioning/SKILL.md`：触发描述、工作流、默认行为和输出规则。
- `skills/critical-questioning/references/question-chain.md`：基于批判性提问的内部审查清单。
- `skills/critical-questioning/references/report-template.md`：中英文报告模板和可选栏目规则。
- `skills/critical-questioning/agents/openai.yaml`：Codex skill 列表使用的界面元数据。

## 安装

使用开放 skills CLI 从 GitHub 安装：

```bash
npx skills add https://github.com/tanghaojin/critical-questioning --skill critical-questioning
```

全局安装到 Codex：

```bash
npx skills add https://github.com/tanghaojin/critical-questioning --skill critical-questioning -a codex -g
```

非交互式安装：

```bash
npx skills add https://github.com/tanghaojin/critical-questioning --skill critical-questioning -a codex -g -y
```

在本仓库中做本地验证：

```bash
npx skills add . --list
npx skills add . --skill critical-questioning -a codex -g
```

## 示例提示

```text
帮我分析这篇文章的观点，找出论证漏洞和需要补全的地方。
```

```text
分析这段演讲稿的论证结构、主要问题和补全清单。
```

```text
Use critical questioning to audit this speech before I publish it.
```

## 设计原则

- 评估文本自身的理由是否足以支持它自己的结论。
- 不替用户决定最终立场。
- 保留原论证中合理的部分。
- 区分主要问题和次要问题。
- 始终输出补全清单。
- 当论证依赖数据、新闻、专家说法或高风险领域时，建议核查关键事实。
