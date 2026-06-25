# Migration Notes: v2 -> v2.1

## 为什么需要 v2.1

v2 的方向是对的：把选题系统从“宏观方向”升级到“根问题 + 问题树”。

但 v2 的 Weekly Sprint 模块容易产生一个误解：

> 一周试错可以主要在 ChatGPT / Gemini Deep Research 中完成。

这是偏的。

真正的一周试错应该是：

> 我自己读论文、复现实验、跑 baseline、观察失败；LLM 只作为辅助研究顾问。

因此 v2.1 修正了 Sprint 模块。

## 删除 / 降级的东西

- `prompts/weekly_sprint_deep_research.md` 已移到 `prompts/deprecated/`。
- 它不再是主流程文件。
- Deep Research 不再承担 Weekly Sprint 的主体判断。

## 新增的东西

- `empirical_trial_framework.md`：定义人工实证试错原则。
- `prompts/weekly_sprint_empirical_trial.md`：每周读论文 + 复现实验的主 prompt。
- `prompts/llm_auxiliary_for_empirical_sprint.md`：Sprint 中如何使用 LLM 的辅助 prompt。
- `templates/empirical_sprint_log.md`：一周真实试错日志。
- `templates/paper_reading_matrix.md`：论文阅读矩阵。
- `templates/reproduction_plan.md`：复现实验计划。

## 新版流程

```text
Round 1: LLM 枚举候选根问题
        ↓
人工选择 4–6 个候选
        ↓
Weekly Empirical Sprint: 每周亲自验证 1 个
        ↓
基于 empirical_sprint_log 做 Go / Hold / Kill
        ↓
Round 2–5 收敛博士 trajectory
```

## 判断权转移

v2 中，LLM 可能隐性承担了判断权。  
v2.1 中，判断权回到研究者本人。

LLM 可以说：

> 根据文献，这个方向可能有潜力。

但只有你亲自读过论文、跑过 baseline、看过失败模式后，才能说：

> 这个根问题值得我继续投入。

## 对张欢欢老师框架的修正理解

“方向不是想出来的，是做出来的”不是“让模型做一周 Deep Research”。

它应该被执行为：

- 读代表论文，确认问题是否真实。
- 复现前沿方法，确认是否做得动。
- 做小切口实验，确认是否能看见 failure mode。
- 通过摩擦修正根问题句和问题树。

这才是 v2.1 的核心。
