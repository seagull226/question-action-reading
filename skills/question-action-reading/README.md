[← 返回项目首页](../../README.md) · [如果问题还不清楚：Question Framing](../question-framing/README.md) · [查看 AI 执行规则](./SKILL.md)

# Question-Action Reading

> A problem-driven reading skill for turning books into judgment, action, and transferable understanding.

这不是一个“帮你总结一本书”的 Prompt。\n\n如果用户还说不清楚“到底希望这本书帮自己解决什么”，可以先使用 [Question Framing](../question-framing/README.md) 形成 Working Question，再进入本 Skill。

它更关注一个问题：

> **一本书，究竟有没有改变你遇到真实问题时的思考和行动？**

它现在明确定位为一个 **Reading Adapter**：负责把书中的 claim、证据、模型和边界转成可检验输入；如果阅读过程中问题已经变成竞争解释、系统反馈或杠杆设计，则借用 [Question → Explanation → Action](../question-explanation-action/README.md) 的通用推理路由，而不是让 Reading Skill 无限膨胀。

当前版本：**v0.3.0**

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
使用 Question-Action Reading Skill v0.3 带我学习这本书。
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
- 严格区分作者 claim、作者证据、我们的推断与用户经验
- 理解足够时尽快行动
- 把行动当作实验，用真实反馈修正理解
- 遇到系统问题时调用通用推理路由，不强行把所有系统分析塞进 Reading 流程

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

v0.3 在前两轮真实阅读基础上，又经过《第五项修炼》的完整实测。

这次测试确认了两点：

1. Reading Skill 需要更严格地区分作者原观点与我们自己的推断；
2. 当阅读自然进入竞争解释、反馈回路、限制条件和杠杆点时，应调用通用推理路由，而不是继续扩张 Reading 本身。

下一步继续通过真实阅读任务验证边界和交接点。

## Roadmap

- [x] v0.2：Question → Action 学习闭环
- [x] 用《第五项修炼》进行第三轮真实测试
- [x] v0.3：增加来源/推断分离，并明确与通用推理路由的交接
- [ ] 增加示例学习记录
- [ ] 探索 Problem / Action Cards
- [ ] 探索多本书的问题综合与公开内容产出

## License

暂未确定。后续会根据公开传播、再利用和商业使用边界决定授权方式。
