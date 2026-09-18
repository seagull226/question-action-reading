# Question-Action

> 一组围绕“找到问题 → 理解问题 → 学习知识 → 判断 → 行动 → 反馈”构建的 AI Skills。
>
> 这个仓库最初从 Question-Action Reading 开始，现在逐渐发展成一套**问题驱动的学习与推理工具集**。

当前包含三个彼此独立、但可以组合使用的 Skill。

## 一张图看懂三个 Skill

```text
模糊困惑 / 现象
       ↓
Question Framing
我真正应该问什么？
       ↓
 Working Question
       ↓
Question → Explanation → Action
这个问题该怎么理解、验证、下钻和行动？
       ↓
如果需要书里的知识或模型
       ↓
Question-Action Reading
怎样围绕问题去学习一本或多本书？
```

这不是固定流水线。

任何一个 Skill 都可以单独使用；后续证据如果暴露原问题框架有误，也可以返回 Question Framing。

---

## Skills

### 1. Question Framing · v0.1.0

**用途：在认真回答之前，先确认“现在问的是不是值得回答的问题”。**

核心通路：

> 现象还原 → 目标还原 → 问题诊断 → 候选问题 → Working Question

它不寻找“宇宙里唯一真正的问题”，而是形成一个：

> **当前最值得研究、可以被证据继续修正的工作问题。**

- [README：给人看的问题重构方法](./skills/question-framing/README.md)
- [SKILL.md：给 AI 执行的规则](./skills/question-framing/SKILL.md)

适合：

- 我只有模糊困惑，不知道真正应该问什么；
- 怀疑自己一开始就问错了问题；
- 我可能把答案、症状或解决方案塞进了问题；
- 一个问题混了多个目标或多个层级；
- 想先确定一个值得研究的 Working Question。

---

### 2. Question → Explanation → Action · v0.1.0

**用途：分析一个已经暂时值得研究的问题，找到当前最有解释力的答案，并决定是否继续下钻、进入系统思考或转向行动。**

核心路由：

> 1. 我到底在问什么？  
> 2. 我是不是偷偷默认了什么？  
> 3. 有哪些可能解释？  
> 4. 如果这些解释是真的，我应该看到什么？  
> 5. 现实证据更支持谁？又反驳谁？  
> 6. 这个原因还值得继续问“为什么”吗？  
> 7. 它是不是其实是一个循环问题？  
> 8. 如果要改变结果，哪里最值得动？

- [README：给人看的 8 条通路与完整架构](./skills/question-explanation-action/README.md)
- [SKILL.md：给 AI 执行的路由规则](./skills/question-explanation-action/SKILL.md)

适合：

- 为什么某件事会发生？
- 当前解释到底是不是关键？
- 证据不完整时应该如何保留不确定性？
- 什么时候应该继续追因，什么时候应该停止？
- 一个问题是否已经变成反馈循环和系统问题？
- 如果要改变结果，真正值得发力的位置在哪里？

---

### 3. Question-Action Reading · v0.2.1

**用途：带着真实问题读一本或多本书。**

它不以“总结全书”为目标，而是让书真正改变判断和行动。

核心闭环：

> Question → Basic Question → Breakdown → Models → Boundary → Action → Feedback

- [README：给人看的方法说明](./skills/question-action-reading/README.md)
- [SKILL.md：给 AI 执行的规则](./skills/question-action-reading/SKILL.md)

适合：

- 我想用一本书解决一个真实问题；
- 我想判断自己是否真正学会，而不是只记住概念；
- 我想比较多本书对同一个基本问题的不同回答；
- 我希望把阅读结果转成行动，并用反馈修正理解。

---

## 三个 Skill 的边界

| | Question Framing | Question → Explanation → Action | Question-Action Reading |
|---|---|---|---|
| 核心问题 | 我应该问什么？ | 这个问题该怎么想下去？ | 一本书怎么帮助这个问题？ |
| 典型输入 | 模糊困惑 / 初始问题 / 症状 | Working Question | 问题 + 一本或多本书 |
| 主要任务 | 还原现象、目标、重构问题 | 竞争解释、证据、下钻、系统、杠杆 | 调用书中模型、判断边界、行动 |
| 主要输出 | Working Question | 当前解释、剩余、系统结构、杠杆点 | Learning State、Action、Skill Feedback |
| 停止条件 | 问题已足够支持分析 | 理解已足够或证据不足以继续 | 对当前问题已经学到够用 |
| 是否能单独使用 | 是 | 是 | 是 |

它们有意保留少量重叠，因为现实推理不是一条单向流水线。

例如：

> Question → Explanation → Action 在分析过程中发现原问题框架错了，就应该返回 Question Framing。

---

## 共享的上层原则

三个 Skill 虽然用途不同，但共享几条底层原则：

- **问题优先于内容。** 先确定要解决什么，再决定学什么、查什么。
- **Question 也是假设。** 最初的问题可以被后续证据修正。
- **区分事实、解释和假设。** 不把“听起来合理”直接当成事实。
- **只达到最小充分深度。** 不为了显得深刻而无限追问。
- **边界比口号重要。** 一个方法什么时候不成立，同样重要。
- **理解最终要回到行动。** 如果继续解释已经不再改变判断或行动，就应该停。
- **行动也是验证。** 真实反馈会反过来修正问题和解释。

---

## Repository Structure

```text
question-action-reading/
├─ README.md
└─ skills/
   ├─ question-framing/
   │  ├─ README.md
   │  └─ SKILL.md
   ├─ question-explanation-action/
   │  ├─ README.md
   │  └─ SKILL.md
   └─ question-action-reading/
      ├─ README.md
      └─ SKILL.md
```

---

## 怎么选？

如果你的起点是：

- **“我感觉哪里不对，但不知道真正该问什么。”** → Question Framing
- **“问题已经比较清楚，我想知道为什么、该不该继续追、哪里值得发力。”** → Question → Explanation → Action
- **“我有一本书，想真正学会并用出来。”** → Question-Action Reading
- **“我先有模糊困惑，后来形成问题，再发现一本书能帮我。”** → 三个 Skill 可以依次组合，但不是强制流程

---

## 当前状态

- Question Framing：v0.1.0，第一版问题入口 Skill。
- Question → Explanation → Action：v0.1.0，第一版通用推理路由。
- Question-Action Reading：v0.2.1，已从真实读书过程持续迭代。

接下来会优先通过真实问题测试三个 Skill 的**边界和交接点**，而不是继续为了“完整”增加方法。

## License

暂未确定。后续会根据公开传播、再利用和商业使用边界决定授权方式。
