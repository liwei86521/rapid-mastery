# Rapid Mastery

[![License](https://img.shields.io/badge/license-Apache--2.0-blue.svg)](LICENSE)
[![Skill Type](https://img.shields.io/badge/skill-Codex-blue.svg)](#)
[![Status](https://img.shields.io/badge/status-ready-brightgreen.svg)](#)

`Rapid Mastery` 是一个面向 Codex 的技能，用来把开放式学习需求压缩成高密度、高留存、可立刻执行的学习冲刺。

`Rapid Mastery` is a Codex skill that turns open-ended learning requests into high-density, high-retention, immediately actionable learning sprints.

它不追求泛泛而谈的“解释很多”，而是把学习过程收敛成一个紧凑闭环：

It does not aim to produce long generic explanations. Instead, it compresses learning into a compact loop:

1. Build the map
2. Explain simply
3. Practice with feedback
4. Verify by teaching or producing something

如果你想让用户从“我几乎不会”快速走到“我能解释、能回答问题、能开始上手”，这个仓库就是为这个目标设计的。

If you want users to move from “I barely know this topic” to “I can explain it, answer questions about it, and start using it” in a single focused session, this repository is built for that job.

## 概览 | Overview

`Rapid Mastery` 的核心目标是把学习从“信息堆积”变成“能力形成”。

The core goal of `Rapid Mastery` is to turn learning from information accumulation into usable capability.

它特别适合下面这些场景：

It is especially useful for:

- 快速上手一个新工具、新框架或新概念
- 面试前的高频知识突击
- 在 30 分钟或 60 分钟内建立可工作的认知框架
- 把复杂主题压缩成最关键的 20%
- fast ramp-up on a new tool, framework, or concept
- interview-focused review and cram sessions
- building a usable mental model in 30 or 60 minutes
- compressing complex topics into the most valuable 20%

## 为什么存在 | Why This Skill Exists

很多 AI 教学类回答会失败，通常是因为两个极端：

Most AI learning responses fail in one of two ways:

- 太浅，读完还是不会用
- 太长，读到一半就失去执行意愿
- too shallow to be useful
- too long to be actionable

`Rapid Mastery` 设计在这两者之间。它先帮用户搭建地图，再用通俗解释降低理解门槛，然后立刻通过练习和验证把知识转成可操作能力。

`Rapid Mastery` is designed to sit between those extremes. It builds a map first, explains the hard part simply, then quickly converts understanding into action through drills and verification.

## 核心能力 | What It Does

这个 skill 会让模型更像一个“结构化技术教练”，而不是一个只会展开说明的讲解器。

This skill makes the model behave more like a structured technical coach than a passive explainer.

- 先给主题地图，再进入细节
- 用类比、例子和低术语密度解释核心概念
- 提供从易到难的练习和参考答案
- 适配 `30 分钟 / 60 分钟 / 1 天 / 3 天 / 面试突击` 等不同模式
- 以输出型验证收尾，而不是停在总结
- build a top-down map before diving into details
- explain core ideas in plain language with analogies and examples
- provide short exercises with concise reference answers
- adapt to multiple modes such as `30-minute`, `60-minute`, `1-day`, `3-day`, and `interview-cram`
- finish with output-based verification instead of passive summary

## 适用主题 | Best For

它最适合下面几类内容：

It works especially well for topics like:

- 编程语言：Rust、Python、Go
- 框架与平台：Kubernetes、FastAPI、React
- AI 与 Agent 主题：attention mechanism、NemoClaw、memory systems
- 开发者工具与工程概念：Git、CI/CD、system design basics
- programming languages such as Rust, Python, and Go
- frameworks and platforms such as Kubernetes, FastAPI, and React
- AI and agent topics such as attention mechanisms, NemoClaw, and memory systems
- developer tooling and engineering concepts such as Git, CI/CD, and system design basics

## 快速开始 | Quick Start

把这个目录放到你的 Codex skills 目录下：

Place this folder in your Codex skills directory:

```text
$CODEX_HOME/skills/rapid-mastery
```

或者放到项目级的本地 `.codex` 目录里：

Or place it in a project-local `.codex` directory:

```text
.codex/skills/rapid-mastery
```

然后在提示词里直接调用：

Then invoke it directly in your prompt:

```text
Use $rapid-mastery to help me master Kubernetes in a 60-minute sprint.
```

## 示例提示词 | Prompt Examples

```text
让我快速掌握 NemoClaw，重点放在架构、关键命令和面试高频点。
```

```text
帮我 1 天上手 Rust。先给学习地图，再给练习和参考答案。
```

```text
用 rapid-mastery 帮我做一份 PostgreSQL 面试突击卡。
```

```text
Teach me attention mechanism with the 10x learning method. Keep it beginner-friendly.
```

```text
Use $rapid-mastery to help me learn system design basics in a 30-minute sprint.
```

## 工作方式 | How It Works

这个 skill 使用固定的四阶段学习闭环：

The skill follows a four-stage learning loop:

### 1. 搭地图 | Build the Map

先说明主题是什么、为什么重要、有哪些关键子主题，以及用户最少必须掌握哪些词汇。

It starts with what the topic is, why it matters, which subtopics matter most, and the minimum vocabulary the learner needs first.

### 2. 讲人话 | Explain Simply

把最难或最核心的概念翻译成通俗语言，用类比、短例子和低门槛表达帮助理解。

It translates the hardest or most central idea into plain language using analogies, short examples, and low-jargon explanations.

### 3. 立刻练 | Practice with Feedback

根据主题类型给练习题，并尽量附上简明参考答案，让用户能立即检验理解。

It creates topic-appropriate exercises and usually includes concise reference answers so the learner can test understanding immediately.

### 4. 用输出验证 | Verify by Output

最后不是“总结一下”，而是让用户通过复述、选择、排错或小任务来证明自己真的掌握了。

Instead of ending with a summary, it asks the learner to prove understanding through explanation, decision-making, troubleshooting, or a tiny build task.

## 学习模式 | Learning Modes

### 30 分钟冲刺 | 30-Minute Sprint

适合快速建立第一层认知框架。

Best for fast orientation and first-pass understanding.

- 核心心智模型
- 关键 20%
- 短路线图
- 3 到 5 个快测题
- essential mental model
- key 20 percent
- short roadmap
- 3 to 5 quick checks

### 60 分钟掌握 | 60-Minute Sprint

适合在短时间内做到“理解 + 练习 + 复述”。

Best for compact but practical mastery in a single sitting.

- 学习地图
- 通俗解释
- 结构化 60 分钟流程
- 4 到 5 个带答案练习
- 最终掌握检验
- learning map
- plain-language explanation
- structured 60-minute flow
- 4 to 5 practice prompts with answers
- final mastery check

### 1 天上手 | 1-Day Mastery

适合集中式技能起步。

Best for focused upskilling across a single day.

- 分阶段学习块
- 优先级练习
- 复盘检查点
- 一个输出型目标
- staged learning blocks
- prioritized practice
- review checkpoints
- one output-based goal

### 3 天计划 | 3-Day Plan

适合短期沉浸式强化。

Best for deeper short-term immersion.

- 按天拆分结构
- 累进式练习
- 里程碑输出
- 更强的巩固循环
- day-by-day structure
- compounding exercises
- milestone outputs
- stronger retention loops

### 面试突击 | Interview-Cram Mode

适合高频题、标准答法、对比和陷阱题。

Best for high-frequency questions, model answers, tradeoffs, and pitfalls.

- 高频问题
- 简洁标准答案
- 对比与取舍
- 常见误区与追问
- high-frequency questions
- concise standard answers
- comparisons and tradeoffs
- pitfalls and likely follow-up questions

## 输出结构 | Output Shape

如果用户没有指定别的格式，通常会按下面这个顺序输出：

Unless the user asks for another format, responses usually follow this structure:

1. 学习地图 / Learning map
2. 核心概念 / Core concepts
3. 通俗解释 / Plain-language explanation
4. 练习与答案 / Practice with answers
5. 掌握检验 / Mastery check
6. 下一步行动 / Next action

这种结构的重点不是“讲得全面”，而是“让用户能立刻继续学下去”。

The point of this structure is not exhaustive coverage. It is to keep the learner moving with immediate clarity and momentum.

## 仓库结构 | Repository Structure

```text
rapid-mastery/
├─ .gitignore
├─ LICENSE
├─ README.md
├─ SKILL.md
└─ agents/
   └─ openai.yaml
```

- `README.md`: GitHub 首页说明 / public GitHub-facing homepage
- `SKILL.md`: 核心技能定义 / core skill definition and behavior
- `agents/openai.yaml`: 展示元数据与默认 prompt / display metadata and default prompt
- `README_TEMPLATE.md`: 可复用仓库模板 / reusable repository template
- `LICENSE`: Apache 2.0 许可证 / Apache 2.0 license text

## 自定义方式 | Customization

你可以通过编辑下面这些文件来调整 skill：

You can customize the skill by editing:

- `SKILL.md`：调整流程、节奏、输出结构和支持模式
- `agents/openai.yaml`：调整展示名称、短描述和默认 prompt
- `README.md`：调整对外展示文案和示例
- `SKILL.md`: change workflow, pacing, output structure, and supported modes
- `agents/openai.yaml`: change display name, short description, and default prompt
- `README.md`: change public-facing documentation and examples

常见改法包括：

Common customizations include:

- 默认输出改成中文或英文
- 强化技术类练习部分
- 收紧面试模式的答案风格
- 增加特定领域的示例主题
- switching the default output language
- expanding the technical practice section
- tightening the answer style for interview mode
- adding domain-specific examples

## 适合谁用 | Who This Repository Is For

如果你希望一个 LLM 更像下面这些角色，这个仓库会很适合：

This repository is a strong fit if you want an LLM to behave more like:

- 技术教练
- 结构化导师
- 面试陪练
- 高密度入门向导
- a technical coach
- a structured tutor
- an interview prep partner
- a high-density onboarding guide

## 贡献说明 | Contributing

欢迎贡献。

Contributions are welcome.

建议优先保持这个 skill 的几个核心特征：

If you extend the skill, try to preserve its core strengths:

- 清晰胜过堆砌
- 可执行胜过泛泛鼓励
- 练习胜过被动总结
- 输出验证胜过模糊自信
- clarity over verbosity
- action over generic encouragement
- practice over passive summary
- output-based verification over vague confidence

## 许可证 | License

本仓库采用 Apache License 2.0。

This repository is licensed under the Apache License 2.0.

详情见 [LICENSE](LICENSE)。

See [LICENSE](LICENSE) for details.
