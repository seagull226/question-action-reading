# Question-Action

> 一组围绕“问题 → 理解 → 判断 → 行动 → 反馈”构建的 AI Skills。
>
> 这个仓库最初只有 Question-Action Reading。现在加入第二个独立 Skill 后，项目从“一个读书 Skill”升级为“问题驱动的学习与推理工具集”。

当前包含两个彼此独立、但可以组合使用的 Skill。

## Skills

### 1. Question-Action Reading · v0.2.1

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

### 2. Question → Explanation → Action · v0.1.0

**用途：分析一个现实问题，找到当前最有解释力的答案，并决定是否继续下钻、进入系统思考或转向行动。**

它不是另一套固定“八步法”，而是一个思考路由器：

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

## 两个 Skill 的关系

| | Question-Action Reading | Question → Explanation → Action |
|---|---|---|
| 起点 | 一本书 + 一个真实问题 | 一个现象 / 问题 / 矛盾 |
| 主要知识来源 | 书、本地材料、多本书 | AI 已有知识、Web、数据、书、用户经验 |
| 核心任务 | 学会、判断、应用 | 解释、验证、下钻、系统化、行动 |
| 主要输出 | Learning State、Action、Skill Feedback | 当前解释、关键剩余、下一问、系统结构、杠杆点 |
| 是否依赖另一个 Skill | 否 | 否 |

它们不是上下级，也不是强依赖。

更准确地说：

> **Question-Action Reading 是“如何用书解决问题”。**
>
> **Question → Explanation → Action 是“面对问题时，接下来该用哪一种思考动作”。**

如果一个现实问题需要书里的模型，可以组合使用；如果不需要，就各自独立运行。

## 共享的上层原则

两个 Skill 虽然用途不同，但共享几条底层原则：

- **问题优先于内容。** 先确定要解决什么，再决定学什么、查什么。
- **区分事实、解释和假设。** 不把“听起来合理”直接当成事实。
- **只达到最小充分深度。** 不为了显得深刻而无限追问。
- **边界比口号重要。** 一个方法什么时候不成立，同样重要。
- **理解最终要回到行动。** 如果继续解释已经不再改变判断或行动，就应该停。
- **行动也是验证。** 真实反馈会反过来修正原来的解释。

## Repository Structure

    question-action-reading/
    ├─ README.md
    └─ skills/
       ├─ question-action-reading/
       │  ├─ README.md
       │  └─ SKILL.md
       └─ question-explanation-action/
          ├─ README.md
          └─ SKILL.md

## 怎么选？

如果你的起点是：

- **“我有一本书，想真正学会并用出来。”** → Question-Action Reading
- **“我有一个现象，不知道为什么，也不知道该往哪里追。”** → Question → Explanation → Action
- **“我先有现实问题，后来发现某本书可能能帮我。”** → 两者可以组合，但不需要强制串联

## 当前状态

- Question-Action Reading：v0.2.1，已从真实读书过程持续迭代。
- Question → Explanation → Action：v0.1.0，刚形成第一版通用推理路由，需要通过不同领域的真实问题继续压力测试。

这个仓库会优先通过真实使用暴露失败模式，再迭代 Skill，而不是为了“方法论完整”不断增加步骤。

## License

暂未确定。后续会根据公开传播、再利用和商业使用边界决定授权方式。