# Round 3 Prompt: Problem Tree Selection


> v2.1 note: 本轮应优先读取你亲自完成的 empirical_sprint_log.md、paper_reading_matrix.md、reproduction_plan.md。LLM 的综述性判断只能作为辅助，不能替代一手读论文和复现实验产生的证据。
## 使用方式

当一个候选根问题在 Round 2 中被判为 Go 或强 Hold 后，使用本 prompt。

附上：

- profile.yaml
- value_axis.md
- root_problem_framework.md
- Round 2 输出
- root_problem_card.md
- empirical_sprint_log.md（如果有）

---

## Prompt

你是我的博士选题委员会模拟器，也是 adversarial research advisor。

现在候选根问题已经通过初筛。你的任务不是继续夸它，而是帮我选择：

> 哪一棵问题树最适合作为博士主线？

候选根问题：

> TODO: 粘贴根问题一句话

## 任务 A：生成 3 棵竞争性问题树

请围绕同一个根问题，生成 3 棵不同的问题树。它们必须有本质不同的递进逻辑，例如：

- measurement → mechanism → method → generalization
- theory → algorithm → benchmark stress-test → deployment
- failure taxonomy → robust method → uncertainty → decision support
- single-domain → cross-domain → open-world → synthesis
- human-centered → model-centered → system-centered → field validation

每棵树包括：

- 树名
- 主线句
- 4 个 paper 节点
- 每个节点的核心问题
- 每个节点的最小实验 / 证据
- 每个节点继承了上一个节点的什么资产
- 每个节点的失败风险

不要使用通用模板。  
如果 3 棵树只是换词，请承认并重新生成。

## 任务 B：张老师四性比较

对三棵树分别打分：

| 问题树 | 可持续性 | 可深挖性 | 可积累性 | 主线感 | 总评 |
|---|---:|---:|---:|---:|---|

并解释：

- 哪棵最像“博士论文主线”？
- 哪棵最容易变成散点 paper？
- 哪棵最适合 3 个月内启动？
- 哪棵长期上限最高？
- 哪棵最容易被大团队碾压？

## 任务 C：Paper 1 反推

对每棵问题树，设计 Paper 1：

- 题目草案
- problem statement
- 研究问题
- 数据 / benchmark
- baseline
- 最小贡献
- 3 个月里程碑
- Paper 1 如何自然引出 Paper 2
- 如果 Paper 1 失败，整棵树是否还能保留？

## 任务 D：主线句压力测试

对每棵树，写一句博士主线：

> 我博士期间研究的是：在 ______ 场景中，面对 ______ 约束，如何实现 ______ 目标。

然后检查每个 paper 是否都能挂回主线句。

如果某个 paper 挂不回去，请标记为“散点风险”。

## 任务 E：选择一棵主树 + 一棵备份树

请最终选择：

- 主问题树
- 备份问题树
- 淘汰问题树

并说明：

1. 为什么主树最适合我？
2. 备份树什么时候启用？
3. 淘汰树为什么看起来好但不适合？
4. 主树第一个月应该做什么？
5. 主树第一个杀点是什么？

## 输出

请生成一个可直接保存为 `problem_tree.md` 的版本，包括：

- 根问题
- 主线句
- 4-paper arc
- 每篇 paper 的递进关系
- 复用资产
- 风险与 kill criteria
- 未来一周行动