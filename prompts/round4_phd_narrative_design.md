# Round 4 Prompt: 4-Paper PhD Narrative Design


> v2.1 note: 本轮应优先读取你亲自完成的 empirical_sprint_log.md、paper_reading_matrix.md、reproduction_plan.md。LLM 的综述性判断只能作为辅助，不能替代一手读论文和复现实验产生的证据。
## 使用方式

当已经选出一个根问题和主问题树后，使用本 prompt 设计博士 narrative。

附上：

- profile.yaml
- value_axis.md
- root_problem_framework.md
- root_problem_card.md
- problem_tree.md
- Round 2 / Round 3 输出

---

## Prompt

你是我的博士论文 narrative architect 和 adversarial research advisor。

现在我已经有一个候选根问题和主问题树。你的任务是把它转化为一个 4-paper PhD narrative，但必须严格避免“论文拼盘”。

根问题：

> TODO

主线句：

> TODO

主问题树：

> TODO

## 任务 A：重写博士主线

请把我的主线改写成 3 个版本：

1. 面向开题委员会的版本
2. 面向 top conference reviewer 的版本
3. 面向未来 hiring committee 的版本

每个版本必须包含：

- 真实场景
- 稳定约束
- 长期目标
- 为什么现有研究不够
- 我的 4 篇 paper 如何逐层推进

## 任务 B：4-paper narrative 设计

请为 4 篇 paper 设计完整 arc：

### Paper 1：Foundational entry

- 核心问题
- 为什么必须先做它
- 它建立什么 measurement / baseline / taxonomy / theory / system asset
- 它如何自然引出 Paper 2
- 3 个月最小版本
- 6 个月完整版本
- 目标 venue 类型
- 最大风险

### Paper 2：First mechanism / method

- 核心问题
- 继承 Paper 1 的什么资产
- 解决 Paper 1 暴露出的哪个瓶颈
- 方法路径
- 目标 venue 类型
- 最大风险

### Paper 3：Generalization / robustness / transfer

- 核心问题
- 继承 Paper 1–2 的什么资产
- 为什么不是另一个独立 paper
- 如何扩展根问题的边界
- 目标 venue 类型
- 最大风险

### Paper 4：Synthesis / system / impact

- 核心问题
- 如何把前 3 篇整合成系统性贡献
- 它如何证明博士主线不是拼盘
- 目标 venue 类型
- 最大风险

## 任务 C：反拼盘审计

请逐篇检查：

| Paper | 是否必要 | 继承了什么 | 引出了什么 | 如果删除会怎样 | 散点风险 |
|---|---|---|---|---|---|

如果任何一篇删除后 narrative 仍完整，说明它不是必要节点，请提出替换方案。

## 任务 D：资产复利计划

请列出博士期间要持续积累的资产：

- 数据 / benchmark 使用经验
- baseline code
- evaluation protocol
- failure taxonomy
- theoretical lens
- paper writing narrative
- community map
- collaborator map
- visualization / analysis tool
- reproducible experiment pattern

每个资产说明：

- 从哪篇 paper 开始建立
- 后续如何复用
- 是否值得长期维护
- 什么时候应停止投入

## 任务 E：时间线与 kill points

请给出 24 个月时间线：

- Month 1–3
- Month 4–6
- Month 7–12
- Month 13–18
- Month 19–24

每个阶段必须包括：

- 目标
- 可交付物
- 决策点
- kill criteria
- fallback plan

## 任务 F：最终判断

请判断：

- 这是否是一个博士级 narrative？
- 它是否符合 value axis？
- 它是否符合张老师四性？
- 它是否适合我当前 profile？
- 它最大的真实风险是什么？

最后输出一个可直接保存为 `trajectory_final.md` 初稿的版本。