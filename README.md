# Trajectory Designer v2.1 + LLM-era Filter: Root Problem First + Empirical Sprint

Trajectory Designer v2.1 是一个用于博士研究方向选择的轻量级 thinking tool。

它的目标不是帮我“找几个热门方向”，而是帮助我在博士早期完成一件更重要的事：

> 找到一个值得我投入 3–5 年的根问题，并通过亲自读论文、复现实验、跑 baseline 和观察失败模式，判断它能否长成一棵问题树。

本阶段在 v2.1 的基础上只加入一个关键过滤器：

> **LLM-era transformation filter**：候选根问题必须说明 LLM / AI systems 的到来如何改变了真实场景中的知识接口、数据生产方式、评估机制、社会依赖结构、模型能力分布或 failure mode。

这个更新不是把系统升级成 research OS，也不是重写全部流程。它只是防止系统继续把“pre-LLM 时代已经成立的旧问题 + 更强 backbone”误判为博士主线候选。

v2.1 的核心原则仍然保留：

> LLM 可以帮我打开视野、整理证据、设计验证路线、反向质疑；但 LLM 不能替我完成试错。真正的方向判断必须来自我的第一手研究摩擦。

---

## 0. 这个 README 怎么用

这个文件不是 prompt，也不是模板。

它是整套系统的使用地图，回答五个问题：

1. 每个文件是干什么的；
2. 哪些文件每次要带给 LLM；
3. 哪些文件只是给我自己看的；
4. pre-LLM-era 与 post-LLM-era principles 怎么选；
5. 每周 empirical sprint 到底怎么运行。

如果我忘了流程，先看这个 README。  
如果我要执行具体任务，再去 `prompts/` 或 `templates/`。

---

## 1. 系统一句话

不要从“我会什么技术”出发。  
要从这个问题出发：

> 在什么真实场景中，面对什么稳定约束 / 核心矛盾，如何实现什么长期目标？

加入 LLM-era filter 后，还要额外问：

> LLM / AI systems 到来后，这个场景中的知识接口、数据生产、评估机制、社会依赖、模型能力分布或 failure mode 发生了什么结构性变化？

一个合格候选不应该只是方向标签，比如：

```text
AI for Science
Trustworthy AI
Multimodal Learning
Medical AI
LLM reasoning
```

也不应该只是：

```text
用 LLM 做 X
用 Transformer 刷某个 benchmark
把旧任务换成更强 backbone
```

而应该被压缩成根问题句，比如：

```text
在低资源语言用户通过 LLM 获取知识、教育和公共服务的真实场景中，
当 LLM 成为默认知识接口时，
面对语料长期稀缺、文化语义不可压缩、英语中心能力迁移失真和有限本地算力的核心矛盾，
如何实现可靠、文化合适、可迁移、可校准的模型能力？
```

---

## 2. 本阶段新增的核心过滤器

### 2.1 LLM-era transformation filter

每个候选根问题必须先回答：

> 这个问题是否因为 LLM / AI systems 的出现而新出现、被结构性放大，或变得系统可研究？

必须具体说明 LLM 改变了什么：

- 知识接口：search / database / paper reading → conversational AI assistant；
- 数据生产：human-written content → human + AI-generated content；
- 评估机制：fixed ground truth → LLM-as-judge / model-assisted evaluation；
- 社会依赖：人类知识获取、教育、科研、公共服务被模型中介；
- 模型能力分布：不同语言、文化、群体之间的能力不平等被放大；
- failure mode：流利错误、文化误读、模型生成污染、能力幻觉等新风险出现。

### 2.2 2018 反事实测试

每个候选都必须问：

> 如果现在回到 2018 年，LLM 尚未成为知识接口 / 内容生产者 / 评估器 / 工作流中介，这个问题是否仍然几乎以同样形式成立？

判断：

- **YES / Go candidate**：没有 LLM，这个问题不会以当前形式存在，或不会如此尖锐、可评估、长期重要。
- **PARTIAL / Hold**：问题本来存在，但 LLM 显著改变了规模、失败模式、社会影响或可研究性。
- **NO / Downgrade or Kill**：2018 年也基本一样，LLM 只是更强工具或 backbone。即使公益、可执行，也应降级为 legacy ML public-good problem，不得进入 top 3。

### 2.3 与 blue ocean 的关系

LLM-era filter 不替代 blue ocean。

- **LLM-era filter** 回答：这个问题是不是这个时代长出来的新根问题？
- **Blue ocean** 回答：这个问题的公共利益版本为什么不会被商业系统自然做完？
- **Empirical sprint** 回答：这个问题我是否真的做得动、看得见 failure mode、长得出问题树？

三者缺一不可。

---

## 3. 系统不做什么

Trajectory Designer v2.1 + LLM-era filter 不做以下事情：

- 不替我自动选方向；
- 不替我判断 Go / Hold / Kill；
- 不用 LLM 的综述性判断代替复现实验；
- 不把热门方向等同于好方向；
- 不把“能发一篇 paper”误认为“能形成博士主线”；
- 不把 pre-LLM 旧问题换上 LLM / Transformer backbone 后包装成新时代根问题；
- 不鼓励我沉迷整理 prompt、目录、表格，而逃避读论文和实验。

如果我只是在不断优化系统，而没有亲自读论文、复现 baseline、跑最小实验，这个系统就被我用错了。

---

## 4. 当前目录怎么理解

当前项目结构如下：

```text
C:.
|   empirical_trial_framework.md
|   README.md
|   README_original.md
|   root_problem_framework.md
|
+---archive
|       migration_notes.md
|       migration_notes_v2_1.md
|       migration_notes_v2_1_llm_era.md
|
+---Every_run_principles
|   +---post-llm - era
|   |       profile_edit_llm_era.yaml
|   |       round1_root_problem_macro_llm_era.md
|   |       value_axis_llm_era.md
|   |       why_this_exists_llm_era.md
|   |
|   \---pre-llm-era
|           profile_edit.yaml
|           value_axis.md
|           why_this_exists.md
|
+---prompts
|   |   llm_auxiliary_for_empirical_sprint.md
|   |   round0_optional_preflight_profile_audit.md
|   |   round1_root_problem_macro.md
|   |   round2_root_problem_deep_dive.md
|   |   round3_problem_tree_selection.md
|   |   round4_phd_narrative_design.md
|   |   round5_red_team_reality_check.md
|   |   weekly_sprint_empirical_trial.md
|   |
|   \---deprecated
|           weekly_sprint_deep_research_v2_deprecated.md
|
\---templates
    |   direction_scorecard.md
    |   empirical_sprint_log.md
    |   paper_reading_matrix.md
    |   problem_tree.md
    |   reproduction_plan.md
    |   root_problem_card.md
    |   trajectory_final.md
    |
    \---deprecated
            weekly_sprint_log_v2_deprecated.md
```

`root_problem_framework.md` 和 `empirical_trial_framework.md` 仍然放在最外层，因为它们是反复阅读的判断手册。  
`Every_run_principles/` 现在分为两套：`pre-llm-era/` 保留历史版本，`post-llm - era/` 是当前默认使用版本。

---

## 5. 文件分工

### 5.1 最外层文件

| 文件 | 用途 | 是否每次上传给 LLM |
|---|---|---|
| `README.md` | 系统使用地图 | 否，给我自己看 |
| `README_original.md` | 旧 README 备份 | 否 |
| `root_problem_framework.md` | 判断什么是好根问题、好问题树 | Round 1–3 建议上传；平时自己反复看 |
| `empirical_trial_framework.md` | 每周人工试错操作手册 | 每周自己看；需要 LLM 辅助设计 sprint 时上传 |

### 5.2 `Every_run_principles/pre-llm-era/`

这是历史版本，用于对照，不作为当前默认入口。

| 文件 | 用途 |
|---|---|
| `profile_edit.yaml` | v2.1 原始 profile |
| `value_axis.md` | v2.1 原始 blue ocean 定义 |
| `why_this_exists.md` | v2.1 原始系统动机 |

除非我刻意想回看旧系统，否则不要在新一轮选题中上传这些文件。

### 5.3 `Every_run_principles/post-llm - era/`

这是当前默认使用版本。

| 文件 | 用途 | 使用方式 |
|---|---|---|
| `profile_edit_llm_era.yaml` | 我是谁、资源、约束、优势、避免方向，并加入 LLM-era transformation requirement | Round 1–5 默认必带 |
| `value_axis_llm_era.md` | 蓝海定义 + LLM-era transformation filter | Round 1–5 默认必带 |
| `why_this_exists_llm_era.md` | 防止模型把任务误解成热门方向推荐或旧问题换 backbone | Round 1 / Round 2 / Round 5 建议带 |
| `round1_root_problem_macro_llm_era.md` | 加入 LLM-era transformation check 的 Round 1 宏观枚举 prompt | Round 1 默认使用 |

`post-llm - era/` 的意思不是只研究 foundation model，而是优先寻找 LLM 到来后结构性变新的根问题。

### 5.4 `prompts/`

这个文件夹保留通用 prompt。

| Prompt | 什么时候用 | 主要产出 |
|---|---|---|
| `round0_optional_preflight_profile_audit.md` | 第一次使用或 profile 大改后 | 校准模型对我的理解 |
| `round1_root_problem_macro.md` | 旧版宏观搜索 prompt | 仅作为历史/备用，不作为默认 |
| `round2_root_problem_deep_dive.md` | 有 2–3 个候选幸存后 | 深挖每个根问题的可行性 |
| `round3_problem_tree_selection.md` | 比较候选问题树 | 选择主问题树 |
| `round4_phd_narrative_design.md` | 准备博士主线 | 4-paper narrative |
| `round5_red_team_reality_check.md` | 最终定方向前 | 红队质疑和失败模式 |
| `weekly_sprint_empirical_trial.md` | 每周开始前 | 本周人工试错计划 |
| `llm_auxiliary_for_empirical_sprint.md` | 读论文、复现、debug、整理日志时 | 辅助分析，不做最终判断 |

当前 Round 1 默认不要用 `prompts/round1_root_problem_macro.md`，而应使用：

```text
Every_run_principles/post-llm - era/round1_root_problem_macro_llm_era.md
```

### 5.5 `templates/`

这个文件夹放每轮要填写的产物。

| Template | 什么时候填 | 作用 |
|---|---|---|
| `root_problem_card.md` | 每个候选根问题都填一份 | 让候选之间可比较 |
| `problem_tree.md` | 候选根问题初步成立后 | 判断是否能长成博士问题树 |
| `paper_reading_matrix.md` | 每周读论文时持续填 | 记录论文解决什么、没解决什么 |
| `reproduction_plan.md` | 复现 baseline 前填 | 降低“看起来能复现”的幻觉 |
| `empirical_sprint_log.md` | 每周结束后填 | 记录一手证据和 Go / Hold / Kill |
| `direction_scorecard.md` | 多个候选比较时填 | 横向比较候选根问题 |
| `trajectory_final.md` | 最终收敛时填 | 博士方向主线文档 |

### 5.6 `archive/`

`archive/` 放迁移说明和废弃文件。读一次即可，日常不使用。

| 文件 | 用途 |
|---|---|
| `migration_notes.md` | 早期迁移说明 |
| `migration_notes_v2_1.md` | v2 → v2.1：从 Deep Research sprint 转为 empirical sprint |
| `migration_notes_v2_1_llm_era.md` | v2.1 → v2.1 + LLM-era filter：新增时代生成性过滤器 |

---

## 6. 系统运行的两种模式

### 模式 A：LLM / Deep Research 战略枚举

用途：打开宏观视野，找到候选根问题。

适合使用的阶段：

```text
Round 0–1: 校准 + 候选枚举
Round 2–5: 基于我已有日志做深挖、收敛、红队
```

LLM 可以做：

- 枚举候选根问题；
- 查公开 dataset / benchmark / baseline / paper / repo；
- 帮我识别红海、死海、伪蓝海；
- 帮我识别 legacy ML problem disguised as LLM-era problem；
- 帮我比较候选方向；
- 帮我做开题委员会视角的质疑。

LLM 不可以做：

- 替我完成每周试错；
- 替我判断 baseline 是否真的可复现；
- 替我判断这个方向我是否真的愿意做 3–5 年；
- 替我做最终 Go / Hold / Kill；
- 把“用 LLM 做旧问题”包装成新时代根问题。

### 模式 B：Weekly Empirical Sprint

用途：用我的一手研究摩擦检验候选根问题。

这一阶段不是 Deep Research sprint，而是 empirical sprint。

每周只试一个候选根问题。最低要求：

1. 扫读 8–12 篇论文；
2. 精读 3–5 篇论文；
3. 选择 1 个 baseline / repo / benchmark 尝试复现；
4. 跑通 demo、baseline 或最小 evaluation，或者明确记录为什么跑不通；
5. 做 1 个 sanity check / 小扰动 / failure case 分析；
6. 更新 `root_problem_card.md` 和 `problem_tree.md`；
7. 填写 `empirical_sprint_log.md`；
8. 我自己做 Go / Hold / Kill。

如果这一周没有亲手读论文和跑实验，就不算 Sprint，只算调研。

---

## 7. 推荐完整流程

```text
M0: 准备 post-LLM-era profile + value axis + why_this_exists + root problem framework
        ↓
Round 1: 使用 post-LLM-era Round 1 prompt 枚举候选根问题
        ↓
先做 LLM-era transformation check，再做 blue ocean / 四性 / substrate / entry paper 判断
        ↓
人工筛选 3–5 个候选
        ↓
Weekly Empirical Sprint: 每周亲自试错 1 个根问题
        ↓
每周结束填写 empirical_sprint_log.md，并做 Go / Hold / Kill
        ↓
完成 3–5 个 Sprint 后，保留 1–3 个幸存候选
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

## 8. 每一轮具体怎么上传文件

### 8.1 Round 1：宏观候选根问题枚举

新开 ChatGPT / Gemini Deep Research，对话中上传：

```text
Every_run_principles/post-llm - era/profile_edit_llm_era.yaml
Every_run_principles/post-llm - era/value_axis_llm_era.md
Every_run_principles/post-llm - era/why_this_exists_llm_era.md
root_problem_framework.md
Every_run_principles/post-llm - era/round1_root_problem_macro_llm_era.md
```

目标输出：

```text
7–10 个候选根问题
每个候选必须先做 LLM-era transformation check
每个候选对应一个初版 root problem card
建议保留 3–5 个进入人工 empirical sprint
```

Round 1 的任务不是选最终方向，而是生成高质量候选池。  
但本阶段新增一条规则：如果候选大多是 pre-LLM 旧问题换新 backbone，应直接建议重做 Round 1。

### 8.2 每周 Sprint：人工试错一个候选

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
Every_run_principles/post-llm - era/profile_edit_llm_era.yaml
Every_run_principles/post-llm - era/value_axis_llm_era.md
root_problem_framework.md
empirical_trial_framework.md
prompts/weekly_sprint_empirical_trial.md
当前候选 root_problem_card.md
```

注意：这只是帮我制定本周人工试错计划，不是让 LLM 替我试错。

### 8.3 Sprint 中途：让 LLM 辅助读论文 / debug / 分析失败

上传：

```text
prompts/llm_auxiliary_for_empirical_sprint.md
当前论文笔记或 paper_reading_matrix.md
当前 reproduction_plan.md
报错信息 / 实验结果 / failure case
```

此时 LLM 的角色是研究助理，不是裁判。

### 8.4 Sprint 结束：做 Go / Hold / Kill

先自己填写：

```text
templates/empirical_sprint_log.md
```

再让 LLM 做红队辅助时，可以上传：

```text
Every_run_principles/post-llm - era/profile_edit_llm_era.yaml
Every_run_principles/post-llm - era/value_axis_llm_era.md
empirical_sprint_log.md
paper_reading_matrix.md
reproduction_plan.md
root_problem_card.md
problem_tree.md
prompts/llm_auxiliary_for_empirical_sprint.md
```

最终 Go / Hold / Kill 由我决定。

### 8.5 Round 2–5：基于实证日志收敛方向

当我完成 3–5 个 Sprint 后，上传：

```text
Every_run_principles/post-llm - era/profile_edit_llm_era.yaml
Every_run_principles/post-llm - era/value_axis_llm_era.md
root_problem_framework.md
若干 root_problem_card.md
若干 problem_tree.md
若干 empirical_sprint_log.md
prompts/round2_root_problem_deep_dive.md
```

之后根据阶段继续使用 Round 3、Round 4、Round 5 prompt。

---

## 9. Go / Hold / Kill 标准

### Go

只有同时满足以下条件，才允许 Go：

- 通过 LLM-era transformation check：不是旧问题换新 backbone；
- 根问题句变得更清楚，而不是更模糊；
- 至少 3–5 篇核心论文让我看到真实未解问题；
- 至少 1 个 baseline / repo / benchmark 可以启动；
- 复现或最小实验暴露出真实 failure mode；
- 问题树可以自然长出 3 个以上子问题；
- 第一篇 entry paper 在 3 个月内有可见进展；
- 这个方向仍然符合 value axis；
- 我愿意把未来 3–5 年的学术身份押在这个问题上。

### Hold

以下情况进入 Hold：

- LLM-era transformation 是 PARTIAL：问题本来存在，但 LLM 确实改变了规模、失败模式、社会影响或可研究性；
- 问题重要，但 evaluation substrate 还不够清楚；
- 文献显示有空间，但第一篇 entry 不够明确；
- baseline 可复现，但暂时没看出强问题树；
- 我有兴趣，但还缺一周证据。

Hold 最多允许一次。连续两次 Hold，必须 Kill 或 Go。

### Kill

出现以下情况应直接 Kill：

- 2018 年反事实测试显示：问题几乎同样成立，LLM 只是更强工具；
- 根问题句写不清；
- 读完论文后发现只是热门标签，没有稳定矛盾；
- 需要先造 dataset / benchmark / metric 才能开始；
- 第一篇 paper 需要 6 个月以上准备；
- 复现成本明显超过单兵博士可承受范围；
- 4 篇 paper 只能硬凑，不能自然递进；
- 方向主要由商业化或大厂 roadmap 驱动；
- 我对这个问题没有持续好奇心。

---

## 10. 一个月最小执行计划

### Week 0：候选池生成

使用 post-LLM-era Round 1 prompt 生成 7–10 个候选根问题。人工筛到 3–5 个。

产物：

```text
candidate_root_problems.md
root_problem_card_00x.md
```

每个候选必须记录：

```text
LLM-era transformation check: YES / PARTIAL / NO
2018 counterfactual result
blue ocean 判断
evaluation substrate
3-month entry paper
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

基于 3 个 Sprint 日志，进入 Round 2 / Round 3，保留 1–2 个主候选。

---

## 11. 常见误用

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

### 误用 6：把旧问题换上 LLM backbone

错误：这个问题在 2018 年已经成立，现在只是“可以用 LLM 做得更好”。  
正确：必须说明 LLM 如何改变了问题结构、影响规模、failure mode 或可研究性。

---

## 12. 每次开始前的自检问题

开始 Round 1 前问：

```text
我是不是在找根问题，而不是找热门方向？
这个候选是否通过 LLM-era transformation check？
它是不是 pre-LLM 旧问题换新 backbone？
```

开始每周 Sprint 前问：

```text
这周我要亲手读哪些论文、复现哪个 baseline、跑哪个最小实验？
这个实验能否帮助我验证 LLM-era transformation 是否真实？
```

结束每周 Sprint 后问：

```text
这个方向经过我的一手摩擦后，是更清楚了，还是更虚了？
LLM-era transformation 是更成立了，还是被证伪了？
```

最终定方向前问：

```text
如果我要为这个根问题投入 3–5 年，我是否仍然愿意？
它是否既属于这个时代，又能在我的资源约束下做出博士主线？
```

---

## 13. Anti-overengineering reminder

这个系统不是为了获得工程满意感。

如果我开始沉迷于：

- 调整目录结构；
- 重写 prompt；
- 优化模板；
- 设计自动化流程；
- 让 LLM 反复给我更多候选；

但没有亲自读论文、复现 baseline、跑实验、观察 failure mode，那么我就是在逃避真正的问题：

> 这个根问题是否值得我投入博士阶段？

本阶段新增 LLM-era filter 不是为了让系统更复杂，而是为了修复一个具体失败模式：

> 系统容易推荐“有价值、可执行、低拥挤，但像 pre-LLM 文物”的方向。

最终判断仍然来自第一手摩擦，不来自模型的漂亮总结。
