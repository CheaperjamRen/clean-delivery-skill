# 研究与公开讨论

“交付污染”是一个可观察的工作流问题。资料集中在范围控制、交付分层和人类检查点；它们没有被包装成单一的模型心理学结论。

## 一手与机构资料

| 资料 | 可用启发 |
| --- | --- |
| [Anthropic Prompting best practices](https://platform.claude.com/docs/en/build-with-claude/prompt-engineering/claude-prompting-best-practices) | 文档直接讨论 overengineering、额外文件、临时 scratchpad 和范围约束。 |
| [Anthropic Trustworthy agents in practice](https://www.anthropic.com/research/trustworthy-agents) | Agent 会规划、行动、观察、调整；Plan Mode 把检查点放到整体策略。 |
| [OpenAI：Unrolling the Codex agent loop](https://openai.com/index/unrolling-the-codex-agent-loop/) | 工具结果和前几轮上下文会持续参与后续生成；交付出口需要单独整理。 |
| [AWS：A control framework for AI coding agents](https://aws.amazon.com/blogs/security/balancing-speed-and-safety-a-control-framework-for-ai-coding-agents/) | scope-creep detection、specification checks、风险分级的人类审查和最小权限。 |
| [OWASP LLM06: Excessive Agency](https://genai.owasp.org/llmrisk/llm062025-excessive-agency/) | 功能、权限和自主性都应保持在任务所需范围；高影响动作需要用户批准。 |
| [Plan-Then-Execute 研究](https://arxiv.org/abs/2502.01390) | 248 名参与者、日常任务、计划与执行的不同介入程度；结构完整的计划仍可能让人高估可靠性。 |

## 社区里的相似抱怨

- [r/codex：How do you stop Codex/Claude from overengineering small coding tasks?](https://www.reddit.com/r/codex/comments/1vf5elq/how_do_you_stop_codexclaude_from_overengineering/)：每一项改动都能找到理由，最后的结果却明显超出 ticket。
- [r/codex：Why does Codex constantly over-engineer code and ignore rules in agents.md?](https://www.reddit.com/r/codex/comments/1ve9nxe/why_does_codex_constantly_overengineer_code_and/)：讨论拆小计划、阶段审查、机器可执行约束与负面限制的局限。
- [r/ClaudeCode：Why AI coding agents spiral](https://www.reddit.com/r/ClaudeCode/comments/1sbxna2/why-ai-coding-agents-spiral-and-how-i-fixed-it/)：把范围护栏、检查点、独立审查和 slop 清理作为长期工作流。

这些讨论主要围绕 coding agent；仓库把同一类现象延展到报告、PPT、办公文件和通用 Agent。跨场景例子用于帮助读者识别输出形状，研究结论保持在各自来源的范围内。

## 起点

[X 账号 `@songkeys`](https://x.com/songkeys) 的帖子提供了番茄炒蛋与东坡肉的起源画面，发布时间显示为 2026-08-20。具体原帖链接尚未独立确认，截图按起源记录收录。

## 证据边界

“交付污染”是来自真实使用和公开讨论的工作流命名。它描述可观察的输出形状，适合指导交付检查；它不等于对某个模型、版本或训练目标的普遍定律。
