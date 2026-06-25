# Trajectory Designer v2.1: Root Problem First + Empirical Sprint

Trajectory Designer v2.1 是一个用于博士研究方向选择的战略级 thinking tool。

它的目标不是帮我“找几个热门方向”，而是帮助我在博士早期完成一件更重要的事：

> 找到一个值得我投入 3-5 年的根问题，并通过亲自读论文、复现实验、跑 baseline 和观察失败模式，判断它能否长成一棵问题树。

v2.1 的核心原则是：

> LLM 可以帮我打开视野、整理证据、设计验证路线、反向质疑；但 LLM 不能替我完成试错。真正的方向判断必须来自我的第一手研究摩擦。

---

## 0. 这个 README 怎么用

这个文件不是 prompt，也不是模板。

它是整套系统的使用地图，回答四个问题：

1. 每个文件是干什么的；
2. 哪些文件每次都要带给 LLM；
3. 哪些文件只是给我自己看的；
4. 每周试错到底应该怎么运行。

如果我忘了流程，先看这个 README。  
如果我要执行具体任务，再去 `prompts/` 或 `templates/`。

---

## 1. 系统一句话

不要从“我会什么技术”出发。  
要从这个问题出发：

> 在什么真实场景中，面对什么稳定约束 / 核心矛盾，如何实现什么长期目标？

一个合格候选不应该只是方向标签，比如：

```text
AI for Science
Trustworthy AI
Multimodal Learning
Medical AI
```

而应该被压缩成根问题句，比如：

```text
在低资源科学研究中，面对数据稀缺、噪声高、实验反馈慢的问题，
如何让机器学习模型产生可验证、可泛化的科学假设？
```

---

## 2. 系统不做什么

Trajectory Designer v2.1 不做以下事情：

- 不替我自动选方向；
- 不替我判断 Go / Hold / Kill；
- 不用 LLM 的综述性判断代替复现实验；
- 不把热门方向等同于好方向；
- 不把“能发一篇 paper”误认为“能形成博士主线”；
- 不鼓励我沉迷整理 prompt、目录、表格，而逃避读论文和实验。

如果我只是在不断优化系统，而没有亲自读论文、复现 baseline、跑最小实验，这个系统就被我用错了。

---

## 3. 当前目录怎么理解

推荐目录结构如下。你现在把 `root_problem_framework.md` 和 `empirical_trial_framework.md` 放在最外层是合理的，因为它们主要是给自己反复看的判断手册。

```text
trajectory_designer_v2_1_empirical_sprint/
├── README.md
├── root_problem_framework.md
├── empirical_trial_framework.md
│
├── Every_run_principles/
│   ├── profile_edit.yaml
│   ├── value_axis.md
│   └── why_this_exists.md
│
├── prompts/
│   ├── round0_m0_profile_and_root_problem_calibration.md
│   ├── round1_root_problem_macro.md
│   ├── round2_root_problem_deep_dive.md
│   ├── round3_problem_tree_selection.md
│   ├── round4_phd_narrative_design.md
│   ├── round5_red_team_reality_check.md
│   ├── weekly_sprint_empirical_trial.md
│   └── llm_auxiliary_for_empirical_sprint.md
│
├── templates/
│   ├── root_problem_card.md
│   ├── problem_tree.md
│   ├── empirical_sprint_log.md
│   ├── paper_reading_matrix.md
│   ├── reproduction_plan.md
│   ├── direction_scorecard.md
│   └── trajectory_final.md
│
└── archive/
    ├── migration_notes.md
    └── migration_notes_v2_1.md
```

如果我的本地文件名略有不同，以实际文件为准。核心不是文件名，而是职责边界。

---

## 4. 文件分工

### 4.1 最外层文件

| 文件 | 用途 | 是否每次上传给 LLM |
|---|---|---|
| `README.md` | 系统使用地图 | 否，给我自己看 |
| `root_problem_framework.md` | 判断什么是好根问题、好问题树 | Round 1-3 建议上传；平时自己反复看 |
| `empirical_trial_framework.md` | 每周人工试错操作手册 | 每周自己看；需要 LLM 辅助设计 sprint 时上传 |

### 4.2 `Every_run_principles/`

这个文件夹放每次战略判断都应该带上的稳定原则。

| 文件 | 用途 | 使用方式 |
|---|---|---|
| `profile_edit.yaml` | 我是谁、资源、约束、优势、避免方向 | Round 1-5 必带 |
| `value_axis.md` | 我的蓝海定义和硬过滤器 | Round 1-5 必带 |
| `why_this_exists.md` | 防止模型把任务误解成热门方向推荐 | Round 1 / Round 2 / Round 5 建议带 |

`Every_run_principles` 的意思是：只要我让 LLM 做战略级方向判断，这些文件就应该一起出现。

### 4.3 `prompts/`

这个文件夹放给 LLM 的任务指令。

| Prompt | 什么时候用 | 主要产出 |
|---|---|---|
| `round0_m0_profile_and_root_problem_calibration.md` | 第一次使用或 profile 大改后 | 校准模型对我的理解 |
| `round1_root_problem_macro.md` | 初始宏观搜索 | 7-10 个候选根问题 |
| `round2_root_problem_deep_dive.md` | 有 2-3 个候选幸存后 | 深挖每个根问题的可行性 |
| `round3_problem_tree_selection.md` | 比较候选问题树 | 选择主问题树 |
| `round4_phd_narrative_design.md` | 准备博士主线 | 4-paper narrative |
| `round5_red_team_reality_check.md` | 最终定方向前 | 红队质疑和失败模式 |
| `weekly_sprint_empirical_trial.md` | 每周开始前 | 本周人工试错计划 |
| `llm_auxiliary_for_empirical_sprint.md` | 读论文、复现、debug、整理日志时 | 辅助分析，不做最终判断 |

### 4.4 `templates/`

这个文件夹放我每轮要填写的产物。

| Template | 什么时候填 | 作用 |
|---|---|---|
| `root_problem_card.md` | 每个候选根问题都填一份 | 让候选之间可比较 |
| `problem_tree.md` | 候选根问题初步成立后 | 判断是否能长成博士问题树 |
| `paper_reading_matrix.md` | 每周读论文时持续填 | 记录论文解决什么、没解决什么 |
| `reproduction_plan.md` | 复现 baseline 前填 | 降低“看起来能复现”的幻觉 |
| `empirical_sprint_log.md` | 每周结束后填 | 记录一手证据和 Go / Hold / Kill |
| `direction_scorecard.md` | 多个候选比较时填 | 横向比较候选根问题 |
| `trajectory_final.md` | 最终收敛时填 | 博士方向主线文档 |

### 4.5 `archive/`

`archive/` 放版本迁移说明和废弃文件。读一次即可。日常不使用。

---

## 5. 系统运行的两种模式

v2.1 有两个模式，必须区分。

### 模式 A：LLM / Deep Research 战略枚举

用途：打开宏观视野，找到候选根问题。

适合使用的阶段：

```text
Round 0-1: 校准 + 候选枚举
Round 2-5: 基于我已有日志做深挖、收敛、红队
```

LLM 可以做：

- 枚举候选根问题；
- 查公开 dataset / benchmark / baseline / paper / repo；
- 帮我识别红海、死海、伪蓝海；
- 帮我比较候选方向；
- 帮我做开题委员会视角的质疑。

LLM 不可以做：

- 替我完成每周试错；
- 替我判断 baseline 是否真的可复现；
- 替我判断这个方向我是否真的愿意做 3-5 年；
- 替我做 Go / Hold / Kill。

### 模式 B：Weekly Empirical Sprint

用途：用我的一手研究摩擦检验候选根问题。

这一阶段不是 Deep Research sprint，而是 empirical sprint。

每周只试一个候选根问题。最低要求：

1. 扫读 8-12 篇论文；
2. 精读 3-5 篇论文；
3. 选择 1 个 baseline / repo / benchmark 尝试复现；
4. 跑通 demo、baseline 或最小 evaluation，或者明确记录为什么跑不通；
5. 做 1 个 sanity check / 小扰动 / failure case 分析；
6. 更新 `root_problem_card.md` 和 `problem_tree.md`；
7. 填写 `empirical_sprint_log.md`；
8. 我自己做 Go / Hold / Kill。

如果这一周没有亲手读论文和跑实验，就不算 Sprint，只算调研。

---

## 6. 推荐完整流程

```text
M0: 准备 profile + value axis + root problem framework
        ↓
Round 1: LLM / Deep Research 枚举 7-10 个候选根问题
        ↓
人工筛选 4-6 个候选
        ↓
Weekly Empirical Sprint: 每周亲自试错 1 个根问题
        ↓
每周结束填写 empirical_sprint_log.md，并做 Go / Hold / Kill
        ↓
完成 3-5 个 Sprint 后，保留 1-3 个幸存候选
        ↓
Round 2: 基于 empirical logs 深挖幸存根问题
        ↓
Round 3: 选择问题树
        ↓
Round 4: 设计 4-paper PhD narrative
        ↓
Round 5: Red-team reality check
        ↓
trajectory_final.md
```

---

## 7. 每一轮具体怎么上传文件

### 7.1 Round 1：宏观候选根问题枚举

新开 ChatGPT / Gemini Deep Research，对话中上传：

```text
Every_run_principles/profile_edit.yaml
Every_run_principles/value_axis.md
Every_run_principles/why_this_exists.md
root_problem_framework.md
prompts/round1_root_problem_macro.md
```

目标输出：

```text
7-10 个候选根问题
每个候选对应一个初版 root problem card
建议保留 3-5 个进入人工 empirical sprint
```

Round 1 的任务不是选最终方向，而是生成高质量候选池。

### 7.2 每周 Sprint：人工试错一个候选

每周开始前，自己打开：

```text
root_problem_framework.md
empirical_trial_framework.md
templates/root_problem_card.md
templates/problem_tree.md
templates/paper_reading_matrix.md
templates/reproduction_plan.md
templates/empirical_sprint_log.md
```

如果需要 LLM 辅助制定计划，再上传：

```text
Every_run_principles/profile_edit.yaml
Every_run_principles/value_axis.md
root_problem_framework.md
empirical_trial_framework.md
prompts/weekly_sprint_empirical_trial.md
当前候选 root_problem_card.md
```

注意：这只是帮我制定本周人工试错计划，不是让 LLM 替我试错。

### 7.3 Sprint 中途：让 LLM 辅助读论文 / debug / 分析失败

上传：

```text
prompts/llm_auxiliary_for_empirical_sprint.md
当前论文笔记或 paper_reading_matrix.md
当前 reproduction_plan.md
报错信息 / 实验结果 / failure case
```

此时 LLM 的角色是研究助理，不是裁判。

### 7.4 Sprint 结束：做 Go / Hold / Kill

先自己填写：

```text
templates/empirical_sprint_log.md
```

再让 LLM 做红队辅助时，可以上传：

```text
empirical_sprint_log.md
paper_reading_matrix.md
reproduction_plan.md
root_problem_card.md
problem_tree.md
prompts/llm_auxiliary_for_empirical_sprint.md
```

最终 Go / Hold / Kill 由我决定。

### 7.5 Round 2-5：基于实证日志收敛方向

当我完成 3-5 个 Sprint 后，上传：

```text
Every_run_principles/profile_edit.yaml
Every_run_principles/value_axis.md
root_problem_framework.md
若干 root_problem_card.md
若干 problem_tree.md
若干 empirical_sprint_log.md
prompts/round2_root_problem_deep_dive.md
```

之后根据阶段继续使用 Round 3、Round 4、Round 5 prompt。

---

## 8. Go / Hold / Kill 标准

### Go

只有同时满足以下条件，才允许 Go：

- 根问题句变得更清楚，而不是更模糊；
- 至少 3-5 篇核心论文让我看到真实未解问题；
- 至少 1 个 baseline / repo / benchmark 可以启动；
- 复现或最小实验暴露出真实 failure mode；
- 问题树可以自然长出 3 个以上子问题；
- 第一篇 entry paper 在 3 个月内有可见进展；
- 这个方向仍然符合 value axis。

### Hold

以下情况进入 Hold：

- 问题重要，但 evaluation substrate 还不够清楚；
- 文献显示有空间，但第一篇 entry 不够明确；
- baseline 可复现，但暂时没看出强问题树；
- 我有兴趣，但还缺一周证据。

Hold 最多允许一次。连续两次 Hold，必须 Kill 或 Go。

### Kill

出现以下情况应直接 Kill：

- 根问题句写不清；
- 读完论文后发现只是热门标签，没有稳定矛盾；
- 需要先造 dataset / benchmark / metric 才能开始；
- 第一篇 paper 需要 6 个月以上准备；
- 复现成本明显超过单兵博士可承受范围；
- 4 篇 paper 只能硬凑，不能自然递进；
- 方向主要由商业化或大厂 roadmap 驱动；
- 我对这个问题没有持续好奇心。

---

## 9. 一个月最小执行计划

### Week 0：候选池生成

使用 Round 1 生成 7-10 个候选根问题。人工筛到 4-6 个。

产物：

```text
candidate_root_problems.md
root_problem_card_00x.md
```

### Week 1：Sprint 1

亲自试错候选 1。

产物：

```text
paper_reading_matrix_01.md
reproduction_plan_01.md
empirical_sprint_log_01.md
problem_tree_01.md
```

### Week 2：Sprint 2

亲自试错候选 2。

### Week 3：Sprint 3

亲自试错候选 3。

### Week 4：第一次收敛

基于 3 个 Sprint 日志，进入 Round 2 / Round 3，保留 1-2 个主候选。

---

## 10. 常见误用

### 误用 1：把 Weekly Sprint 做成 Deep Research

错误：让模型查资料、生成问题树、给 Go / Hold / Kill。  
正确：我自己读论文和复现，模型只辅助。

### 误用 2：把 profile 写成系统 prompt

错误：把 value axis、framework、sprint protocol 全塞进 profile。  
正确：profile 只描述我是谁、资源、约束、优势、风险偏好。

### 误用 3：把没有 benchmark 的荒地当蓝海

错误：觉得没人做就是蓝海。  
正确：蓝海应当是已有 evaluation substrate，但真实问题尚未被充分回答。

### 误用 4：用漂亮 narrative 掩盖不可复现

错误：方向故事很好听，但 baseline 跑不动、数据找不到、metric 不清楚。  
正确：没有最小可执行路径，就不能 Go。

### 误用 5：过度整理系统

错误：继续优化目录、prompt、模板，却不读论文、不跑实验。  
正确：每周必须产生第一手研究摩擦。

---

## 11. 每次开始前的自检问题

开始 Round 1 前问：

```text
我是不是在找根问题，而不是找热门方向？
```

开始每周 Sprint 前问：

```text
这周我要亲手读哪些论文、复现哪个 baseline、跑哪个最小实验？
```

结束每周 Sprint 后问：

```text
这个方向经过我的一手摩擦后，是更清楚了，还是更虚了？
```

最终定方向前问：

```text
如果我要为这个根问题投入 3-5 年，我是否仍然愿意？
```

---

## 12. Anti-overengineering reminder

这个系统不是为了获得工程满意感。

如果我开始沉迷于：

- 调整目录结构；
- 重写 prompt；
- 优化模板；
- 设计自动化流程；
- 让 LLM 反复给我更多候选；

但没有亲自读论文、复现 baseline、跑实验、观察 failure mode，那么我就是在逃避真正的问题：

> 这个根问题是否值得我投入博士阶段？

最终判断来自第一手摩擦，不来自模型的漂亮总结。
