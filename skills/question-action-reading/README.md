[← 返回项目首页](../../README.md) · [如果问题还不清楚：Question Framing](../question-framing/README.md) · [查看 AI 执行规则](./SKILL.md)

# Question-Action Reading

> A problem-driven reading skill for turning books into judgment, action, and transferable understanding.

这不是一个“帮你总结一本书”的 Prompt。\n\n如果用户还说不清楚“到底希望这本书帮自己解决什么”，可以先使用 [Question Framing](../question-framing/README.md) 形成 Working Question，再进入本 Skill。

它更关注一个问题：

> **一本书，究竟有没有改变你遇到真实问题时的思考和行动？**

当前版本：**v0.2.1**

## 核心流程

**Question → Basic Question → Breakdown → Models → Boundary → Action → Feedback**

中文：

> **真实问题 → 基本问题 → 拆结构 → 调用模型 → 判断边界 → 最小行动 → 反馈修正**

## 它和传统读书总结有什么不同

传统方式通常是：

> 读书 → 提炼概念 → 分类 → 总结 → 做笔记

Question-Action Reading 更偏向：

> 我正在解决什么问题？  
> → 把具体场景拿掉，这背后是哪一类反复出现的基本问题？  
> → 这个问题由哪些因素和关系构成？  
> → 哪些是真正会改变结论的关键卡点？  
> → 书里的哪些方法、规律、模型能帮助我？  
> → 它们在什么条件下成立？  
> → 我下一步能采取什么最小行动？  
> → 实践结果如何修正我的理解？

## 使用方式

把 [`SKILL.md`](./SKILL.md) 交给支持长上下文/文件读取的 AI，然后提供一本书或相关材料。

最小启动方式：

```text
使用 Question-Action Reading Skill v0.2 带我学习这本书。
不要先总结。
先问我这本书想帮我解决什么真实问题，然后一次只推进一个关键问题。
```

## 设计原则

- 用户先答，AI 再补充
- 一次只推进一个关键问题
- 问题驱动，而不是目录驱动
- 只补当前最小必要知识
- 不追求覆盖整本书
- 重要观点必须讨论边界
- 理解足够时尽快行动
- 用真实反馈修正理解

## 多本书模式

当多本书在讨论相似主题时，不建议做“多份摘要”。

更适合围绕同一个 **Basic Question** 对比：

- 每本书从什么领域切入？
- 它站在哪个层级？
- 它提供什么方法或思维模型？
- 不同书之间是互补、冲突，还是前提和尺度不同？

目标是形成：

> **一个问题，多种领域、多种层级、多种解决策略。**

## 当前状态

v0.2 来自对两本书的实际学习过程：重点不在“覆盖更多概念”，而在把有效的学习动作固化为可复用流程。

下一步会通过新的真实阅读任务继续测试和修正，而不是直接把方法扩展得更复杂。

## Roadmap

- [x] v0.2：Question → Action 学习闭环
- [ ] 用第三本书进行真实测试
- [ ] 根据真实卡点迭代 v0.3
- [ ] 增加示例学习记录
- [ ] 探索 Problem / Action Cards
- [ ] 探索多本书的问题综合与公开内容产出

## License

暂未确定。后续会根据公开传播、再利用和商业使用边界决定授权方式。
