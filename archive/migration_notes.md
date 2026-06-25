# Migration Notes: v1 → v2

## What changed

v1 的 Trajectory Designer 已经有很强的战略意识：

- 它把 Trajectory Designer 与 Academic Radar 分离。
- 它强调 3–5 年博士 trajectory，而不是 6–12 个月 paper gap。
- 它把 blue ocean 作为硬过滤器。
- 它强调 benchmark 不能决定长期方向，但 evaluation substrate 是早期可执行性硬门槛。
- 它反对工程化、pipeline 化、schema 化。

v2 不推翻这些原则。v2 只做一个关键升级：

> 从“宏观方向枚举”升级为“根问题发现 + 问题树验证 + 每周快速试错”。

## Why this upgrade matters

原来的 Round 1 让模型枚举 7–10 个宏观研究方向。这个设计已经很强，但仍有一个风险：

> LLM 可能给出看起来战略、其实仍然是方向标签的答案。

比如：

- AI for science
- trustworthy AI
- LLM reasoning
- AI for public good
- multimodal learning

这些标签太大。它们还不能直接决定博士主线。

张欢欢老师的分享提醒我们：真正决定博士上限的不是“方向标签”，而是一个能长期深挖的问题主线。

所以 v2 要求所有候选必须先写成根问题：

> 在 ______ 真实场景中，面对 ______ 稳定约束 / 核心矛盾，如何实现 ______ 长期目标？

## Core conceptual changes

### 1. Direction → Root problem

v1 问：

> 我长期要押什么研究主题？

v2 问：

> 我长期要回答什么根问题？

### 2. Candidate direction → Root problem card

v1 的候选方向输出升级为：

- root problem sentence
- value axis fit
- evaluation substrate
- Zhang four-property score
- first paper entry
- problem tree
- Go / Hold / Kill

### 3. 4-paper arc → Problem tree

v1 已要求 4-paper arc 不能套模板。

v2 进一步要求：

> 4 篇 paper 必须是问题树上的自然节点，而不是 narrative 包装。

### 4. Round 1 → Weekly sprint pool

v1 Round 1 后进入 Round 2。

v2 建议 Round 1 后先进入“一周一个方向快速试错”：

- 每周只试一个根问题。
- 一周结束必须 Go / Hold / Kill。
- 每次产出 root_problem_card.md、problem_tree.md、weekly_sprint_log.md。
- 连续试 4–6 周后，再进入 Round 2 / Round 3。

### 5. Good direction criteria → Zhang four-property filter

v2 把张老师四个标准变成硬评分：

- 可持续性
- 可深挖性
- 可积累性
- 主线感

这四个维度任何一个太弱，都不能进入博士主线。

## Recommended new workflow

```text
M0: Profile + value axis calibration
↓
Round 1: Root problem macro enumeration
↓
Weekly Sprint × 4–6 weeks
    Week 1: Root problem A → Go / Hold / Kill
    Week 2: Root problem B → Go / Hold / Kill
    Week 3: Root problem C → Go / Hold / Kill
    Week 4: Root problem D → Go / Hold / Kill
↓
Round 2: Deep dive on 2–3 surviving root problems
↓
Round 3: Select problem tree
↓
Round 4: Design 4-paper PhD narrative
↓
Round 5: Red-team reality check
↓
trajectory_final.md
```

## Files mapped from v1 to v2

| v1 file | v2 replacement / upgrade |
|---|---|
| README.md | README.md |
| why_this_exists.md | why_this_exists.md |
| value_axis.md | value_axis.md |
| round1_macro.md | prompts/round1_root_problem_macro.md |
| N/A | root_problem_framework.md |
| N/A | prompts/weekly_sprint_deep_research.md |
| N/A | templates/root_problem_card.md |
| N/A | templates/problem_tree.md |
| N/A | templates/weekly_sprint_log.md |
| N/A | templates/trajectory_final.md |

## What should not change

不要把 v2 变成工程项目。

不需要：

- code
- CLI
- schema
- JSONL
- cache
- lineage tracking
- multi-agent orchestration
- automated ranking
- database

只需要：

- 高质量 prompt
- 残酷判断
- 每周沉淀
- 可比较的 root problem cards
- 明确 Go / Hold / Kill
