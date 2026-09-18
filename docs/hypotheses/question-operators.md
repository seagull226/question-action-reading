# Hypothesis: Shared Question Operators

**Status:** Unverified  
**Date:** 2026-09-19

## 先看这一段

我们观察到，三个 Skill 虽然任务不同，但会反复使用一些相似的“问题操作”：

- **Clarify**：你这句话具体什么意思？
- **Separate**：哪些是事实，哪些是解释？
- **Assumption Check**：这里默认了什么？
- **Reframe**：有没有更准确的问法？
- **Abstract**：去掉具体场景，这是什么反复出现的问题？
- **Decompose**：这个问题是不是混了几个子问题？

因此提出一个暂时假设：

> **Skill 之下，可能存在一个共享的 Question Operators 层。**

可能的关系是：

```text
Skill
  ↓
Question Operator
  ↓
Method
```

例如：

```text
Question Framing
→ Reframe
→ Socratic questioning

Question → Explanation → Action
→ Assumption Check
→ First Principles

Question-Action Reading
→ Abstract
→ Basic Question
```

**现在不据此重构。**

原因很简单：

> 这是一个假设，还没有被足够多的真实案例证明。

---

## 为什么值得记录

如果只放在聊天里，之后很容易只记得：

> “好像应该有 Operators。”

却忘了：

- 为什么当时这么想；
- 当时证据有多少；
- 为什么没有马上重构；
- 什么情况下应该正式采用；
- 什么情况下应该放弃。

所以这里记录的是**研究状态**，不是正式架构。

---

## 当前观察

### Question Framing

主要出现：

- Separate
- Clarify
- Reframe
- Decompose

### Question → Explanation → Action

主要出现：

- Clarify
- Assumption Check

### Question-Action Reading

主要出现：

- Abstract

这说明“共享问题操作层”有一定迹象，但目前样本还少。

---

## 当前假设

这些重复动作可能构成一个独立于具体 Skill 的共享层：

```text
Skill
解决什么任务
  ↓
Question Operator
当前要做什么认知动作
  ↓
Method
用什么方法把这个动作做好
```

---

## 现在为什么不行动

暂时不做：

- 不新增 `operators/` 目录；
- 不把三个 Skill 改成依赖共享 Operator；
- 不为了复用而拆分现有稳定流程。

因为还不确定：

- 这些 Operator 是否长期稳定；
- 是否真的跨 Skill 重复；
- 某些 Operator 是否只是局部动作；
- Operator 之间的边界是否清楚；
- 是否还缺更重要的 Operator。

---

## 什么证据会支持这个假设

当真实使用中反复出现以下情况时，再考虑正式抽象：

1. 同一个 Operator 在多个 Skill 中稳定出现；
2. 它的定义在不同案例里基本不变；
3. 至少两个 Skill 明显复用它；
4. 抽出来以后能减少重复，而不是增加理解成本；
5. 新案例不会频繁迫使我们修改 Operator 边界。

---

## 什么证据会推翻这个假设

如果后续发现：

- Operator 高度依赖具体 Skill；
- 定义频繁变化；
- 所谓“重复”只是表面文字相似；
- 抽出来后反而更难理解；
- 每个 Skill 内部保留动作更自然；

那么就放弃共享层假设。

---

## 当前决策

> **记录，但不重构。**

以后如果新案例再次出现类似结构，回到这份 Hypothesis Log 更新证据，而不是依赖记忆。

---

## 项目层规则

这个案例也形成了一条可复用原则：

> **重要但未验证的结构性发现：先记录假设、验证条件和证伪条件；在证据不足时，不据此重构。**
