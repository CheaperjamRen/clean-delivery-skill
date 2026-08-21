# 为什么 Agent 会把修改痕迹带进成品

## 先看现象

你让 Agent 做一份报告、一个文件或一个小功能。它先顺手加了几块内容，随后按反馈删掉。交付时，标题变成“精简修订版”，正文出现“根据用户要求”，文件名带上“删除竞品风险图表”，回报又复述一遍删改过程。

代码场景里，额外校验、抽象、错误处理和测试也会悄悄进入 diff。每一项单独看都很合理，合在一起就把小任务推成了另一件事。

## 五个相互叠加的原因

### 1. 完成任务和解释清楚同时得到奖励

模型长期接触到的好答案往往详细、周到、带理由。它把“多解释一些”当成可靠信号。最终文件的读者需要的是成品，模型却把工作台上的解释一起带了出来。

### 2. 旧候选会留在上下文里

Agent 的循环会把工具结果、修正意见和前几轮输出继续送回模型。OpenAI 对 Codex agent loop 的公开说明也描述了这种累积过程：模型反复读取上下文，直到停止调用工具并交回结果。旧方案因此容易变成回声。

### 3. “看起来更完整”会推高范围

模型可以迅速补充边界、抽象和未来弹性。Anthropic 的提示词文档把这类表现直接归为 overengineering，并建议把范围、注释和临时文件写成明确约束。

### 4. 过程面和交付面混在同一个出口

草稿适合容纳候选、失败和争论；最终报告、PR、PPT 和导出文件承担阅读与使用。两个出口共用一套文字时，工作留痕就会进入成品。

### 5. Agent 会先执行，再逐步修正

Anthropic 对 Agent 的定义包含“规划、行动、观察、调整”的循环。Plan-Then-Execute 研究（N=248）把计划和行动拆开后观察用户信任与任务表现，也提醒人们：结构完整的计划可能依然“看起来很对”。停下来检查目标和副作用，价值在这里。

## 把问题说清楚

这套 Skill 关注的是“交付污染”：最终读者需要的内容，被历史修订、未采用方案、无关扩展和自我证明占据了位置。

干净交付保留四类信息：

1. 当前请求要求的成果。
2. 读者判断成果所需的验证结果。
3. 事实性限制、风险、权限和未完成项。
4. 可点击的文件、链接和后续动作。

候选路径、失败尝试、删改原因和完整审计记录放到单独的过程记录里。用户明确索要它们时，再按记录格式提供。

## 实用的摩擦点

[分享链接](https://chatgpt.com/share/6a871a9c-f978-83ea-8810-e4dbaa967c5b)中的讨论把这种推进过快的倾向称作“仓促性”，给出的普通用户做法很朴素：先看计划，重大动作前停一下，完成后检查目标之外的代价。这套 Skill 把同样的停顿放在交付出口：检查标题、范围、残留痕迹、事实限制和链接。

## 参考

- [OpenAI：Unrolling the Codex agent loop](https://openai.com/index/unrolling-the-codex-agent-loop/)
- [Anthropic：Prompting best practices](https://platform.claude.com/docs/en/build-with-claude/prompt-engineering/claude-prompting-best-practices)
- [Anthropic：Trustworthy agents in practice](https://www.anthropic.com/research/trustworthy-agents)
- [Plan-Then-Execute 研究概览](https://www.alphaxiv.org/abs/2502.01390)
