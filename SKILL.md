---
name: rapid-mastery
description: 用“10倍学习法”帮助用户快速掌握一个新技术、框架、工具、技能、领域或知识点，把学习过程收敛为高效率闭环：先搭框架，再做通俗讲解，再练习反馈，最后输出验证。Use when the user asks in forms such as "让我快速掌握X", "10倍学习法掌握X", "快速上手X",  "帮我学会X", "30分钟速成X", "60分钟速成X", "1天掌握X", "3天掌握X", "面试突击X", or asks for an AI-driven accelerated-learning plan.
---

# 10倍学习法

把模糊的学习目标压缩成可直接执行的学习闭环。优先让用户尽快形成可用理解、能做题、能输出，而不是追求面面俱到。

Default to a four-stage loop:
1. Build the map
2. Explain simply
3. Practice with feedback
4. Verify by teaching or producing something

## 工作流

When the request names a topic such as `Rust`, `Kubernetes`, `oh-my-codex`, or a concept such as `attention mechanism`, treat that topic as the learning target.

If the topic is broad, narrow to the 20 percent that unlocks 80 percent of practical use. If the topic is narrow, keep the loop compact and hands-on.

Do not ask many setup questions. Make reasonable assumptions and start teaching. Ask at most one short clarifying question only if the requested target is ambiguous.

## 模式选择

如果用户没有指定模式，默认根据目标自动选择最合理的一种。

使用以下五种模式：
- `30分钟速成`
  适合第一次接触某个主题，目标是在 30 分钟内建立框架、会说人话、能做最基础判断。
- `60分钟速成`
  适合主题比 `30分钟速成` 稍复杂、用户希望在 1 小时内从“知道是什么”推进到“能跑通最小链路”，目标是在 60 分钟内建立框架、吃透关键机制、完成一次最小演练。
- `1天掌握`
  适合需要在当天形成可用能力的主题，目标是在 1 天内完成从搭框架、理解关键链路到最小实战和输出验证的压缩闭环。
- `3天掌握`
  适合需要真正形成稳定能力、但希望更快完成闭环的主题，目标是在 3 天内完成从框架理解到小型实战的压缩训练。
- `面试突击`
  适合有明确考核场景，目标是在最短时间内掌握高频概念、经典问法、易错点和标准化表达。

模式判断规则：
- 用户明确写了 `30分钟速成`、`60分钟速成`、`1天掌握`、`3天掌握` 或 `面试突击`，直接采用对应模式。
- 如果主题偏窄、用户只想最快建立框架，优先 `30分钟速成`。
- 如果用户强调“1 小时内搞懂”“快速上手但别太浅”“希望带一个最小演练”，优先 `60分钟速成`。
- 如果用户强调“今天学会”“一天上手”“今晚就要能用”“明天前要产出最小成果”，优先 `1天掌握`。
- 如果主题需要系统掌握或真正上手，但用户仍然强调效率，优先 `3天掌握`。
- 如果用户提到面试、八股、问答、突击、背题、查漏补缺，优先 `面试突击`。

## 第一步：搭学习地图

Start with a top-down learning map.

Include:
- What the topic is
- Why it matters
- The core subtopics
- A recommended learning path
- Stage goals or milestones
- The minimum viable vocabulary the user must know

Prefer a short roadmap over a textbook outline. Name the critical concepts first.

## 第二步：通俗讲解

Explain the hardest or most central ideas in plain language.

Use:
- simple wording
- concrete analogies
- one or two vivid examples
- comparisons to familiar concepts

Avoid jargon unless you define it immediately.

## 第三步：练习反馈

Create practice that matches the target:
- For technical topics: commands, code reading, debugging, architecture questions, mini build tasks
- For conceptual topics: recall questions, scenario questions, explain-the-difference questions
- For skills: drills, case prompts, error spotting, mock exercises

Default to 5 exercises from easy to hard and provide concise reference answers. The goal is fast feedback, not busywork.

When useful, label each exercise with what it tests.

For `面试突击`, prefer:
- high-frequency interview questions
- concise standard answers
- comparisons, tradeoffs, and common pitfalls
- follow-up questions that interviewers often ask

## 第四步：输出验证

End with an output-based check, not a passive summary.

Use one of these:
- Feynman check: ask the user to explain it back and probe weak spots
- Build check: ask the user to make a tiny project or artifact
- Decision check: ask the user to choose between approaches and justify it
- Troubleshooting check: present a realistic failure and ask how to fix it

Keep asking follow-up questions until the explanation is operationally clear.

## 输出格式

Unless the user requests a different format, structure the response in this order:
1. `模式判断`
2. `学习地图`
3. `通俗讲解`
4. `练习题`
5. `费曼检验`
6. `下一步`

对于按时间展开的模式，可以在 `通俗讲解` 与 `练习题` 之间插入 `60分钟路径`、`阶段安排` 或 `每日安排`。

`模式判断` 必须说明为什么选这个模式。

在生成正文回答后，默认额外产出 1 份可复用的 Markdown 文档，除非用户明确说不要创建文件。

Markdown 文档默认要求：
- 将聊天回答中的核心内容完整落地为 `.md` 文件，而不是只写摘要。
- 默认保存到当前工作目录；如果用户指定了路径或文件名，优先遵从用户要求。
- 文档结构默认与回答保持一致，并补上一个清晰标题，例如 `# [主题] - [模式]学习方案`。
- 文件名优先使用 `<topic>-<mode>-rapid-mastery.md`；如果主题包含文件系统不安全字符，替换为短横线。
- 文档中保留学习地图、通俗讲解、练习题、费曼检验、下一步，以及按模式需要展开的时间路径或阶段安排。
- 如果回答里包含命令、代码、清单或练习参考答案，Markdown 文档中也要保留。
- 在最终对用户的回复里，用一句话告知 Markdown 文档的保存路径。
- 如果当前环境不能写文件，就改为输出一个完整的 ```md``` 代码块，并明确说明未实际落盘。

对于五种模式，默认输出要求如下：

### 30分钟速成

输出内容应压缩、直接、偏行动：
- 5 个核心概念
- 20 percent 关键知识
- 1 套最短上手路径
- 3 道快速练习+参考答案
- 1 个 15 到 30 分钟内能完成的小动作

### 60分钟速成

输出内容应比 `30分钟速成` 多一个“最小工作流”层，仍然保持高压缩、可立即执行：
- 5 到 7 个核心概念
- 20 percent 关键知识
- 1 条按分钟拆开的 60 分钟学习路径
- 1 个最小工作流、最小示例或最小判断链
- 4 道快速练习+参考答案
- 1 个 30 到 60 分钟内能完成的小动作

推荐默认采用以下压缩节奏，除非用户明确要求别的节奏：

- 第 0 到 10 分钟：搭地图
  目标是知道这个主题是什么、解决什么问题、最重要的 5 到 7 个概念是什么。
  时间切片可默认设计为：3 分钟看定义和价值，4 分钟看核心概念，3 分钟看学习顺序。
  小任务应偏识别和分类，例如术语配对、概念分组、流程排序。
  验收标准应是：用户能用 1 分钟说清主题定位，并能说出 3 个最重要概念。

- 第 11 到 25 分钟：吃透关键机制
  目标是理解最核心的原理、最容易混淆的点、以及它和相邻概念的区别。
  时间切片可默认设计为：10 分钟通俗讲解，5 分钟做对比，5 分钟看一个具体例子。
  小任务应偏解释和区分，例如“它和相邻概念有什么区别”“为什么要这样设计”。
  验收标准应是：用户能用类比把关键机制讲清，并指出至少 1 个常见误区。

- 第 26 到 45 分钟：跑通最小链路
  目标是把理解变成一次最小演练，形成“我已经用过一次”的感觉。
  时间切片可默认设计为：15 分钟跑通最小示例，5 分钟改一个最小输入、配置或条件。
  小任务应偏操作和应用，例如跑命令、读最小代码、补全流程、解释一次真实输出。
  验收标准应是：用户能独立复现一次最小链路，并解释每一步为什么存在。

- 第 46 到 60 分钟：练习与复述
  目标是快速暴露薄弱点，并用输出验证理解不是错觉。
  时间切片可默认设计为：10 分钟做 3 到 4 道练习，5 分钟纠错，最后 5 分钟做费曼复述。
  小任务应偏应用判断和迁移，例如场景题、选型题、错因分析题。
  验收标准应是：用户能答对大部分练习，并能用 2 分钟把这套最小工作流讲给别人听。

写 `60分钟速成` 输出时，优先遵守以下压缩原则：
- 只保留 1 个主目标，不要同时铺开多个分支主题。
- 学习内容尽量压在 5 到 7 个关键点内，不做百科式罗列。
- 如果主题偏工具或框架，必须包含 1 条端到端最小操作流。
- 如果主题偏概念或理论，必须包含 1 条从定义到场景判断的最小推理链。
- 练习题要优先暴露常见误区，而不是考冷知识。

### 1天掌握

输出内容应按 1 天压缩展开，重点是当天就形成“能用、能讲、能做一个最小产物”的能力：
- 1 天内的分段学习安排
- 每个阶段的目标
- 2 到 3 个高价值任务
- 当天的验收标准
- 当天的输出型验证

推荐默认采用以下压缩日程模板，除非用户明确要求别的节奏：

- 阶段 1：搭框架
  目标是建立整体地图，知道这个主题是什么、解决什么问题、核心概念有哪些、学习顺序是什么。
  时间切片可默认设计为：30 分钟看地图，30 分钟通俗讲解。
  小任务应偏识别和理解，例如术语配对、概念区分、流程复述、最小示例拆解。
  验收标准应是：用户能用自己的话在 3 分钟内讲清主题框架，并说出 3 到 5 个核心概念。

- 阶段 2：打通关键机制
  目标是理解最重要的原理、工作流或判断方法，形成“我知道为什么这样做”的认知。
  时间切片可默认设计为：60 分钟吃透核心机制，30 分钟做 1 轮基础练习。
  小任务应偏解释和判断，例如比较方案、解释报错、说明关键步骤的作用。
  验收标准应是：用户能解释核心机制，并能区分至少 2 个常见混淆点。

- 阶段 3：跑通最小实战
  目标是完成一个最小任务，把知识从理解推进到可执行。
  时间切片可默认设计为：90 分钟跑通最小示例或最小案例，30 分钟做一次改动或举一反三。
  小任务应偏应用和操作，例如安装或初始化、跑通一次最小流程、改一个最小配置、完成一个最小案例分析。
  验收标准应是：用户能独立完成一个最小任务，并能解释关键步骤和结果。

- 阶段 4：输出与复盘
  目标是证明自己不是“看懂了”，而是真的能讲清、能迁移、能处理小问题。
  时间切片可默认设计为：30 分钟做综合练习，20 分钟纠错总结，20 分钟做费曼讲解或决策题。
  小任务应偏综合输出，例如故障排查、场景判断、解释给别人、在两个方案中做选择。
  验收标准应是：用户能交付一个最小产物、完整讲解一个案例，或回答至少 2 个追问。

写 `1天掌握` 输出时，优先遵守以下压缩原则：
- 一天只保留 1 条主线，不要拆成多个平行专题。
- 任务控制在 2 到 3 个高价值动作内，避免材料堆砌。
- 必须包含 1 次最小实战或最小输出，不允许只停留在概念层。
- 如果主题偏工具或框架，必须出现实际命令、代码、配置或操作流。
- 如果主题偏概念或理论，最后阶段必须包含案例判断或讲给别人听的验证题。

### 3天掌握

输出内容应分天展开：
- 第 1 到第 3 天的学习安排
- 每天的目标
- 每天的练习或小任务
- 每天的验收标准
- 第 3 天的输出型验证

推荐默认采用以下压缩日程模板，除非用户明确要求别的节奏：

- 第 1 天：搭框架
  目标是建立整体地图，知道这个主题是什么、解决什么问题、核心概念有哪些、学习顺序是什么。
  时间切片可默认设计为：20 分钟看地图，30 分钟通俗讲解，30 分钟做基础练习，20 分钟做一次复述。
  小任务应偏识别和理解，例如术语配对、概念区分、流程复述、最小可运行示例。
  验收标准应是：用户能用自己的话在 3 分钟内讲清主题框架，并说出 3 到 5 个核心概念。

- 第 2 天：打通关键链路
  目标是理解最重要的原理、常见工作流和关键操作，形成“能用”的能力。
  时间切片可默认设计为：20 分钟回顾昨天内容，40 分钟吃透核心机制，40 分钟完成 1 到 2 个小实战，20 分钟纠错总结。
  小任务应偏应用和判断，例如读命令、读代码、解释报错、比较方案、补全流程。
  验收标准应是：用户能独立完成一个最小任务，并能解释为什么这样做，不只是照抄步骤。

- 第 3 天：输出与迁移
  目标是把理解转成输出，证明自己不只是会跟练，而是真的能迁移到新场景。
  时间切片可默认设计为：20 分钟总复盘，50 分钟完成一个小作品或案例，30 分钟做故障排查或决策题，20 分钟做费曼讲解。
  小任务应偏综合，例如从零搭一个微型项目、解决一个真实报错、在两个方案里做选择并说明理由。
  验收标准应是：用户能交付一个小产物，或完整讲解一个真实案例，并能回答至少 2 个追问。

写 `3天掌握` 输出时，优先遵守以下压缩原则：
- 每天只保留 1 个主目标，不要把一天拆成过多主题。
- 每天安排 1 到 2 个高价值任务，不要堆砌素材。
- 第 1 天偏认知，第 2 天偏应用，第 3 天偏输出。
- 如果主题偏工具或框架，第 2 天和第 3 天必须包含实际命令、代码、配置或操作流。
- 如果主题偏概念或理论，第 3 天必须包含“解释给别人”或“用案例做判断”的验证题。

可直接套用以下标准输出样板：

```md
## 模式判断

采用 `3天掌握`，因为[主题]需要形成稳定能力，但用户希望在较短时间内完成从理解到实战的闭环。

## 学习地图

- 这个主题是什么：[一句话定义]
- 为什么重要：[一句话价值]
- 3 个核心概念：[概念 A]、[概念 B]、[概念 C]
- 学习顺序：[先学什么] -> [再学什么] -> [最后做什么]
- 里程碑：
  - 第 1 天：[建立什么认知]
  - 第 2 天：[打通什么链路]
  - 第 3 天：[输出什么成果]
- 20 percent 关键知识：[真正决定能否上手的少数内容]

## 通俗讲解

把[核心机制]想成[类比]。
[用 1 到 2 段把最难点讲清楚，并给一个具体例子]

## 第 1 天：搭框架

- 今日目标：[建立地图和概念框架]
- 学习内容：[3 到 5 个最核心知识点]
- 今日任务：
  - [任务 1]
  - [任务 2]
- 验收标准：[能复述 / 能区分 / 能解释]

## 第 2 天：打通关键链路

- 今日目标：[掌握关键工作流或核心原理]
- 学习内容：[最重要的流程、命令、代码路径或判断方法]
- 今日任务：
  - [任务 1]
  - [任务 2]
- 验收标准：[能独立完成一个最小任务并解释原因]

## 第 3 天：输出与迁移

- 今日目标：[完成小作品 / 案例分析 / 故障排查]
- 学习内容：[综合应用所需的关键知识]
- 今日任务：
  - [任务 1]
  - [任务 2]
- 验收标准：[能交付产物或讲清完整案例]

## 练习题

1. [基础识别题]
   参考答案：[答案]
2. [应用判断题]
   参考答案：[答案]
3. [迁移输出题]
   参考答案：[答案]

## 费曼检验

请你用 3 分钟讲清：
- [主题] 是什么
- 它最重要的机制是什么
- 什么时候该用它，什么时候不该用它

## 下一步

接下来 15 到 60 分钟，先去做：[最小行动]
```

`60分钟速成` 可直接套用以下标准输出样板：

```md
## 模式判断

采用 `60分钟速成`，因为[主题]需要比 `30分钟速成` 更完整的理解，但用户希望在 1 小时内完成从框架到最小演练的闭环。

## 学习地图

- 这个主题是什么：[一句话定义]
- 为什么重要：[一句话价值]
- 5 到 7 个核心概念：[概念 A]、[概念 B]、[概念 C]……
- 学习顺序：[先看什么] -> [再吃透什么] -> [最后演练什么]
- 20 percent 关键知识：[真正决定能否上手的少数内容]

## 通俗讲解

把[核心机制]想成[类比]。
[用 1 到 2 段把最难点讲清楚，并给一个具体例子]

## 60分钟路径

- 第 0 到 10 分钟：[搭地图]
- 第 11 到 25 分钟：[吃透关键机制]
- 第 26 到 45 分钟：[跑通最小链路]
- 第 46 到 60 分钟：[练习与复述]

## 练习题

1. [基础识别题]
   参考答案：[答案]
2. [机制理解题]
   参考答案：[答案]
3. [应用判断题]
   参考答案：[答案]
4. [迁移题]
   参考答案：[答案]

## 费曼检验

请你用 2 分钟讲清：
- [主题] 是什么
- 它最重要的机制是什么
- 跑通一次最小链路需要哪些步骤

## 下一步

接下来 30 到 60 分钟，先去做：[最小行动]
```

`1天掌握` 可直接套用以下标准输出样板：

```md
## 模式判断

采用 `1天掌握`，因为[主题]需要在当天形成可用能力，而用户希望在 1 天内完成从理解到最小实战的闭环。

## 学习地图

- 这个主题是什么：[一句话定义]
- 为什么重要：[一句话价值]
- 3 到 5 个核心概念：[概念 A]、[概念 B]、[概念 C]
- 学习顺序：[先学什么] -> [再打通什么] -> [最后输出什么]
- 当天里程碑：
  - 阶段 1：[建立什么认知]
  - 阶段 2：[吃透什么机制]
  - 阶段 3：[完成什么最小实战]
  - 阶段 4：[输出什么成果]
- 20 percent 关键知识：[真正决定当天能否上手的少数内容]

## 通俗讲解

把[核心机制]想成[类比]。
[用 1 到 2 段把最难点讲清楚，并给一个具体例子]

## 阶段 1：搭框架

- 目标：[建立地图和概念框架]
- 学习内容：[3 到 5 个最核心知识点]
- 任务：[任务 1]、[任务 2]
- 验收标准：[能复述 / 能区分 / 能解释]

## 阶段 2：打通关键机制

- 目标：[掌握关键工作流或核心原理]
- 学习内容：[最重要的流程、命令、代码路径或判断方法]
- 任务：[任务 1]、[任务 2]
- 验收标准：[能解释为什么这样做]

## 阶段 3：跑通最小实战

- 目标：[完成一个最小任务或最小案例]
- 学习内容：[综合应用所需的关键知识]
- 任务：[任务 1]、[任务 2]
- 验收标准：[能独立完成最小任务并解释结果]

## 阶段 4：输出与复盘

- 目标：[完成讲解 / 复盘 / 决策题 / 故障排查]
- 学习内容：[迁移和纠错所需的关键知识]
- 任务：[任务 1]、[任务 2]
- 验收标准：[能交付一个最小产物或讲清完整案例]

## 练习题

1. [基础识别题]
   参考答案：[答案]
2. [应用判断题]
   参考答案：[答案]
3. [综合迁移题]
   参考答案：[答案]

## 费曼检验

请你用 3 分钟讲清：
- [主题] 是什么
- 它最重要的机制是什么
- 今天你已经能独立完成什么最小任务

## 下一步

接下来今天内，先去做：[最小行动]
```

如果主题偏工具、框架、工程实践，样板里的“任务”或“今日任务”默认优先填入：
- 安装或初始化
- 跑通最小示例
- 改一个最小配置或最小代码片段
- 解释一次真实报错或真实输出

如果主题偏概念、方法论、理论知识，样板里的“任务”或“今日任务”默认优先填入：
- 概念区分题
- 场景判断题
- 反例辨析题
- 复述或讲解题

### 面试突击

输出内容应偏高频问答和表达模板：
- 高频考点地图
- 10 个左右高频面试题
- 每题的参考答案
- 容易答错的点
- 一套 1 分钟、3 分钟、5 分钟表达模板

For `学习地图`, include:
- core concepts
- learning sequence
- milestone goals
- the 20 percent that matters most

For `通俗讲解`, explain the one or two most important ideas simply.

For `练习题`, include answers or reference answers unless the user explicitly asks to hide them.

For `费曼检验`, switch into interactive questioning if the user is ready to continue live.

For `下一步`, recommend the next concrete action the user should take in the next 15 to 60 minutes.

## 适配规则

Adjust the depth to the target:
- Beginner request: reduce jargon, emphasize intuition
- Intermediate request: connect concepts and tradeoffs
- Advanced request: focus on edge cases, failure modes, and design reasoning

Adjust the medium to the topic:
- Coding tool or framework: include commands, files, APIs, workflows
- Academic concept: include definitions, examples, and misconceptions
- Business or strategy topic: include frameworks, scenarios, and tradeoffs

If the user wants speed, bias toward action and recognition patterns. If the user wants rigor, add caveats and discriminating details.

## 触发示例

You may directly use or adapt these patterns in the response:

`我要快速掌握[主题]，给我核心知识点、学习路径、阶段性目标和每阶段的验收方式。`

`用10倍学习法帮我掌握[主题]。`

`30分钟速成[主题]。`

`60分钟速成[主题]。`

`1天掌握[主题]。`

`3天掌握[主题]。`

`面试突击[主题]。`

`用最简单的比喻，给零基础用户解释[知识点]。`

`我练习[技能]，请出5道从易到难的题，并提供参考答案。`

`你当小白，我来讲[主题]。你持续追问，直到确认我真的讲明白。`

## 质量要求

Do not produce generic motivation. Produce a compact system the user can execute immediately.

A strong result should let the user:
- know what to learn first
- understand the hard part in plain language
- test themselves immediately
- prove understanding by explaining or doing
- leave behind a reusable Markdown study note, not only a chat reply

