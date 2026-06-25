# Trajectory Designer v2.1: Root Problem First + Empirical Sprint

Trajectory Designer v2.1 是一个用于博士研究方向选择的战略级 thinking tool。

v2.1 的核心修正是：

> LLM 不负责替我完成试错。LLM 只负责提出候选、整理证据、设计验证路线、反向质疑。真正的试错必须由我自己通过读论文、复现实验、跑 baseline、观察失败模式来完成。

## 和 v2 的区别

v2 的问题是容易把 weekly sprint 误读成 Deep Research sprint：模型查资料、生成问题树、给出 Go / Hold / Kill。  
v2.1 改成 empirical sprint：

- Round 1 可以使用 ChatGPT / Gemini Deep Research 做宏观候选枚举。
- Weekly Sprint 不能只在 Deep Research 里完成。
- Weekly Sprint 的核心证据来自我的第一手工作：读论文、复现代码、跑 baseline、做最小改动、记录卡点、形成判断。
- LLM 在 Sprint 中只是辅助研究顾问，不是裁判。
- Go / Hold / Kill 必须基于我亲自获得的 evidence，而不是模型的综述性判断。

## 系统的核心问题

不要问：

> 我会什么技术？

要问：

> 我可以长期回答什么根问题？

再进一步问：

> 这个根问题，经过一周的亲自读论文和复现实验后，是否仍然显得真实、重要、可深挖、可积累、有主线感？

## 张欢欢老师框架在本系统中的位置

每个候选根问题都必须通过四性过滤：

1. **可持续性**：未来 3–5 年是否仍有研究空间。
2. **可深挖性**：是否能自然长出 3–5 个递进子问题。
3. **可积累性**：文献理解、代码、baseline、数据、failure taxonomy 是否能复用。
4. **主线感**：是否能用一句话讲清楚博士期间所有 paper 都在回答什么。

但这四性不能只靠模型判断。它们必须被 empirical sprint 校验。

## 推荐使用流程

```text
M0: profile + value axis 校准
        ↓
Round 1: LLM / Deep Research 枚举 7–10 个候选根问题
        ↓
人工筛选 4–6 个候选
        ↓
Weekly Empirical Sprint: 每周亲自试错 1 个根问题
        ↓
Go / Hold / Kill
        ↓
Round 2: 基于 empirical logs 深挖 2–3 个幸存根问题
        ↓
Round 3: 选择问题树
        ↓
Round 4: 设计 4-paper PhD narrative
        ↓
Round 5: Red-team reality check
        ↓
trajectory_final.md
```

## 每周 Sprint 的真正定义

每周只试一个候选根问题。  
这一周必须至少完成：

1. 读 8–12 篇核心论文，其中 3–5 篇精读。
2. 选择 1 个 baseline 或代表方法复现。
3. 跑通最小实验，或者明确记录为什么跑不通。
4. 做 1 个最小扰动、复现实验或 sanity check。
5. 更新 root problem card 和 problem tree。
6. 填写 empirical_sprint_log.md。
7. 做 Go / Hold / Kill。

如果一周内完全没有亲手读论文和跑实验，这一周不算 Sprint，只算 LLM 调研。

## LLM 在 Sprint 中可以做什么

LLM 可以帮助：

- 把方向标签改写成根问题句。
- 推荐第一批论文和 baseline。
- 帮我读论文时提炼 problem / assumption / method / failure mode。
- 帮我设计复现路线。
- 帮我 debug 报错。
- 帮我做 ablation / sanity check 设计。
- 帮我质疑这个方向是否伪蓝海。
- 帮我把一周日志整理成可比较的 root problem card。

LLM 不应该替我决定：

- 这个方向是否真实可做。
- baseline 是否实际可复现。
- 数据是否真的干净。
- 方法是否真的有效。
- 我的兴趣和耐受度是否足够。
- Go / Hold / Kill 的最终判断。

这些判断必须来自我的亲身研究摩擦。

## 文件地图

```text
trajectory_designer_v2_1_empirical_sprint/
├── README.md
├── why_this_exists.md
├── value_axis.md
├── root_problem_framework.md
├── empirical_trial_framework.md
├── profile_template.yaml
├── migration_notes_v2_1.md
├── prompts/
│   ├── round0_m0_profile_and_root_problem_calibration.md
│   ├── round1_root_problem_macro.md
│   ├── round2_root_problem_deep_dive.md
│   ├── round3_problem_tree_selection.md
│   ├── round4_phd_narrative_design.md
│   ├── round5_red_team_reality_check.md
│   ├── weekly_sprint_empirical_trial.md
│   ├── llm_auxiliary_for_empirical_sprint.md
│   └── deprecated/
│       └── weekly_sprint_deep_research_v2_deprecated.md
└── templates/
    ├── root_problem_card.md
    ├── problem_tree.md
    ├── empirical_sprint_log.md
    ├── paper_reading_matrix.md
    ├── reproduction_plan.md
    ├── direction_scorecard.md
    └── trajectory_final.md
```

## 最小可执行版本

如果时间紧，只跑这 4 件事：

1. 用 Round 1 让 LLM 生成候选根问题。
2. 每周选 1 个，用 `weekly_sprint_empirical_trial.md` 指导自己读论文 + 复现实验。
3. 每周填 `empirical_sprint_log.md`。
4. 连续完成 4 个日志后，再进入 Round 2–5。

## Anti-overengineering reminder

这个系统不是为了搭 pipeline。

如果我开始沉迷整理文件、优化 prompt、设计表格，而没有亲自读论文和复现实验，我就是在逃避真正的问题：

> 这个根问题是否值得我投入博士阶段？

判断来自第一手摩擦，不来自模型的漂亮总结。
