# Empirical Trial Framework

## 核心原则

Weekly Sprint 的主体不是 Deep Research，而是我自己的 empirical trial。

LLM 的宏观视野可以帮我发现候选根问题，但不能替代以下三件事：

1. 亲自读论文时形成的问题感。
2. 亲自复现 baseline 时遇到的摩擦。
3. 亲自观察实验失败后产生的判断。

张欢欢老师说“方向不是想出来的，是做出来的”。在本系统里，“做出来”被具体化为：

> 一周内完成一轮最小文献理解 + 最小 baseline 复现 + 最小实验摩擦 + 最小问题树修正。

## 一周试错的判据

一个候选根问题经过一周后，不要求你已经做出创新点，但必须能回答：

1. 我是否能读懂这个社区的核心问题？
2. 我是否能跑通一个基本 baseline？
3. 我是否能看见当前方法的真实 failure mode？
4. 我是否能说出一个不是模板化的 Paper 1 入口？
5. 我是否能自然写出 Paper 2 的问题接口？
6. 我是否愿意继续再投入 2–4 周？

如果答案多数是否定，这个方向应该 Hold 或 Kill。

## 每周 Sprint 的最低工作量

推荐最低标准：

- 论文：扫读 8–12 篇，精读 3–5 篇。
- 代码：选择 1 个 baseline / repo / benchmark 尝试复现。
- 实验：跑通官方 demo、baseline 或最小训练 / eval。
- 扰动：做 1 个 sanity check、参数改动、数据切片、failure case 分析或 ablation。
- 记录：填写 empirical_sprint_log.md。

如果一周内没有跑任何代码，也可以暂时保留判断，但不能给 Go，只能 Hold。

## Go / Hold / Kill 规则

### Go

只有同时满足以下条件，才能 Go：

1. 根问题句清楚。
2. 真实场景和受益对象清楚。
3. 至少一个 baseline / dataset / benchmark 可以启动。
4. 亲手复现或最小实验产生了有效摩擦。
5. 能自然长出至少 3 个子问题。
6. 第一篇 entry paper 有 3 个月内可启动路径。
7. 你愿意继续投入下一阶段深挖。

### Hold

出现以下情况，应该 Hold：

- 问题很重要，但 evaluation substrate 仍不清楚。
- baseline 可复现性尚未确认。
- 文献读完后有兴趣，但问题树还不自然。
- 你发现了 failure mode，但还不确定是否可论文化。
- 第一篇 paper 可能可行，但需要再验证 1–2 个关键点。

Hold 不能无限期存在。每个 Hold 方向必须指定下一次验证触发条件。

### Kill

出现以下情况，应该 Kill：

- 根问题句写不清，只剩方向标签。
- 论文越读越散，没有主线感。
- baseline 跑不动且不是短期技术问题，而是资源 / 数据 / 依赖不可控。
- 需要先造 dataset / benchmark / metric 才能开始。
- 4 篇 paper 是硬凑模板。
- 你明显没有持续兴趣。
- 方向违反 value_axis 或落入商业化红海。

## LLM 的辅助模式

在 Sprint 期间，LLM 应该被当作四种角色使用：

1. **Librarian**：帮我找论文、baseline、dataset。
2. **Reading partner**：帮我拆论文的 problem / assumption / method / limitation。
3. **Lab assistant**：帮我设计复现步骤、debug、设计 sanity check。
4. **Red-team advisor**：帮我攻击这个方向是否伪蓝海、伪主线、伪可做。

LLM 不能被当作 judge。Judge 是我的 empirical evidence。

## 每周的理想输出

```text
root_problem_card.md
problem_tree.md
paper_reading_matrix.md
reproduction_plan.md
empirical_sprint_log.md
```

其中最重要的是 empirical_sprint_log.md，因为它记录的是一手判断，而不是模型总结。
