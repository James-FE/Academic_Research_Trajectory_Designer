# Round 2 Prompt: Root Problem Deep Dive


> v2.1 note: 本轮应优先读取你亲自完成的 empirical_sprint_log.md、paper_reading_matrix.md、reproduction_plan.md。LLM 的综述性判断只能作为辅助，不能替代一手读论文和复现实验产生的证据。
## 使用方式

从 Round 1 或每周试错中选择 2–3 个 Hold / Go 候选根问题，分别运行本 prompt。

附上：

- profile.yaml
- value_axis.md
- root_problem_framework.md
- 该候选的 root_problem_card.md
- 该候选的 empirical_sprint_log.md（如果有）
- Round 1 中对应候选的原始输出

---

## Prompt

你是我的 adversarial research advisor。  
现在我们不再枚举方向，而是对一个候选根问题做深挖。

请完整阅读我提供的候选 root_problem_card、profile、value_axis、root_problem_framework。

候选根问题是：

> TODO: 粘贴根问题一句话

你的任务是判断：

> 它是否真的值得进入博士 trajectory 的候选池？

不是判断它是否“有趣”，不是判断它能否发一篇 paper，而是判断它能否成为 3–5 年博士主线。

## 任务 A：根问题真实性审计

请回答：

1. 这个问题真实存在吗？
2. 它在哪些真实场景中出现？
3. 谁会因为这个问题被影响？
4. 现有方法在哪些具体条件下失败？
5. 失败是否有可观察 evidence？
6. 这是不是一个被方法 hype 制造出来的问题？
7. 如果 LLM / 当前主流模型明年变化，这个问题还存在吗？

结论必须是：

- 真实根问题
- 可能是真问题但证据不足
- 伪问题 / 方法机会

## 任务 B：稳定核心矛盾分析

请把根问题拆成：

- 真实场景
- 稳定约束
- 长期目标
- 当前失败机制
- 受益对象
- 为什么这个矛盾未来 3–5 年不会自然消失

如果你无法找到稳定约束，请建议淘汰。

## 任务 C：Evaluation substrate 审计

请列出可复用的：

- datasets
- benchmarks
- metrics
- baselines
- leaderboards
- challenge / shared task
- official code
- survey / taxonomy

每一项必须给 URL。

请标注：

- 可直接用于第一篇 paper
- 需要轻微清洗
- 需要大量工程，不建议依赖
- 不可信 / 不适合

最后给出判断：

> 第一篇 paper 是否能在 3 个月内启动？

## 任务 D：问题树压力测试

请构造 2 个版本的问题树：

### 版本 1：最自然的问题树

从根问题自然长出 4–5 个子问题。说明递进关系。

### 版本 2：最小可行问题树

只保留能支撑博士前两年的 3 个子问题。说明第一篇从哪里切入。

对每个节点回答：

- 该节点解决根问题的哪一部分？
- 输入是什么？
- 输出是什么？
- 需要什么数据 / baseline？
- 可能投向什么类型 venue？
- 与前一个节点是什么关系？
- 如果这个节点失败，后续是否崩塌？

## 任务 E：可积累性审计

判断以下资产能否复用：

- 数据处理 pipeline
- baseline implementation
- evaluation protocol
- failure taxonomy
- problem framing
- theoretical lens
- domain interpretation
- visualization / analysis tooling
- writing narrative
- collaborator / community

给出：

- 高复用资产
- 中复用资产
- 一次性资产
- 不值得投入的资产

如果每篇 paper 都要换故事，请建议淘汰。

## 任务 F：差异化与竞争格局

请回答：

1. 这个根问题目前最强的 5 个相关团队 / researcher 是谁？
2. 他们各自在解决哪个子问题？
3. 我的潜在切入点与他们有什么差异？
4. 这个差异是实质性的，还是只是换数据 / 换场景？
5. 未来 12–18 个月内最可能被大团队抢走的部分是什么？
6. 哪个子问题更适合单兵博士长期深挖？

## 任务 G：第一篇 paper 设计

给出 3 个可能的 first paper entry：

每个 entry 包括：

- problem statement
- dataset / benchmark
- baseline
- minimum viable contribution
- 3 个月计划
- 最可能失败点
- 失败后如何转向
- 它如何连接后续 paper

最后推荐一个最优 entry，并说明为什么。

## 任务 H：Go / Hold / Kill

请给出最终判断：

- Go：进入 Round 3 问题树选择
- Hold：需要补哪些证据
- Kill：淘汰

必须给出评分表：

| 维度 | 0-5 | 理由 |
|---|---:|---|
| 真实重要性 | | |
| 稳定核心矛盾 | | |
| 可持续性 | | |
| 可深挖性 | | |
| 可积累性 | | |
| 主线感 | | |
| Evaluation substrate | | |
| 非对称困难 | | |
| 3 个月 entry | | |
| 4-paper narrative | | |

如果你选择 Go，但有任一关键维度低于 4，必须解释为什么仍然值得冒险。