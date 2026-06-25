# Migration Notes: v2.1 -> v2.1 + LLM-era Filter

## 1. 本阶段升级一句话

本阶段不是重写 Trajectory Designer，也不是把它扩展成 research OS。

本阶段只做一个轻量升级：

> 在原有“根问题 + empirical sprint”框架上，加入 **LLM-era transformation filter**，防止系统把 pre-LLM 时代已经成立的旧问题，仅仅因为可以换成 LLM / Transformer backbone，就误判为 2026 之后值得押注的博士主线。

---

## 2. 为什么需要这次升级

v2.1 已经解决了一个关键问题：  
它把 Weekly Sprint 的判断权从 Deep Research / LLM 还给研究者本人，强调真正的方向判断必须来自亲自读论文、复现 baseline、跑实验和观察 failure mode。

这个方向是对的，但在实际使用中又暴露出新的失败模式：

> 系统会筛出很多“公共利益强、可执行、有公开 substrate、低商业拥挤”的方向，但其中相当一部分本质上是 pre-LLM 时代已经成立的 legacy ML public-good problem。

这些方向不是错，也不是没有价值。它们的问题是：

> 它们可以用，但不像 2026 之后 AI / LLM 时代新长出来的问题。

用户对上一轮 Deep Research 的判断可以概括为：

> 这些根问题像刚出土的文物：能用，但没有新意。

这说明原系统缺少一个时间维度过滤器。  
它能判断“是不是好问题”，但不能充分判断“是不是属于这个时代的博士问题”。

---

## 3. 本阶段要修复的具体失败模式

### 3.1 Public-good old-problem attractor bias

原系统强烈偏好：

- 对人类有益；
- 商业吸引力不足；
- 有公开 evaluation substrate；
- 单兵可执行；
- 3 个月内能启动 entry paper。

这些标准本身都对，但它们组合在一起容易吸出一批经典 ML 公益应用方向：

- 灾害预测；
- 空气质量；
- 医疗时序；
- 遥感；
- 公共健康；
- 生态监测；
- 资源受限传感。

这些方向可能长期重要，也可能可发 paper，但很多问题在 2016、2020、2026 都几乎以同样形式成立。LLM / Transformer 只是更强工具，不是根矛盾的来源。

### 3.2 Backbone substitution error

模型容易把：

> 用 LLM / Transformer 做旧任务

误写成：

> LLM 时代的新根问题

这会导致方向看起来新，但问题结构并不新。

### 3.3 Blue ocean 与时代生成性混淆

原系统把 blue ocean 作为强硬过滤器，这是必要的。  
但 blue ocean 回答的是竞争结构，不回答问题生成机制。

- Blue ocean 问：为什么商业系统和大公司不会自然优先做公共利益版本？
- LLM-era filter 问：为什么这是 LLM 到来后新出现、被放大、或变得可研究的问题？

一个方向可以是 blue ocean，但仍然是旧问题。  
一个方向也可以很 LLM-era，但落入大厂红海。  
本阶段的升级要求两者同时满足。

---

## 4. 新增的核心概念：LLM-era transformation filter

每个候选根问题必须先回答：

> 这个问题是否因为 LLM / AI systems 的出现而新出现、被结构性放大，或变得系统可研究？

候选必须具体说明 LLM 改变了什么：

1. 知识接口：search / database / paper reading → conversational AI assistant；
2. 数据生产方式：human-written content → human + AI-generated content；
3. 评估机制：fixed ground truth → LLM-as-judge / model-assisted evaluation；
4. 社会依赖结构：教育、科研、公共服务、知识获取越来越被模型中介；
5. 模型能力分布：不同语言、文化、群体之间的能力不平等被放大；
6. 人机协作流程：专家与模型共同产生判断、文本、代码、证据；
7. failure mode：流利错误、文化误读、合成内容污染、能力幻觉等新问题出现。

---

## 5. 2018 反事实测试

每个候选都必须问：

> 如果现在回到 2018 年，LLM 尚未成为知识接口 / 内容生产者 / 评估器 / 工作流中介，这个问题是否仍然几乎以同样形式成立？

判断规则：

### YES / Go candidate

没有 LLM，这个问题不会以当前形式存在，或不会如此尖锐、可评估、长期重要。

这类问题可以进入主候选池。

### PARTIAL / Hold

问题本来存在，但 LLM 显著改变了规模、失败模式、社会影响或可研究性。

这类问题可以进入 Hold，但必须通过 empirical sprint 验证 LLM-era transformation 是否真实。

### NO / Downgrade or Kill

2018 年也基本一样，LLM 只是更强工具或 backbone。

这类问题即使公益、可执行，也应降级为 legacy ML public-good problem，不得进入 top 3。

---

## 6. 为什么不是 foundation model filter

本阶段没有采用 “foundation-model-era filter” 这个更窄的表述。

原因是：用户明确修正过，真正重要的不是研究 foundation model 本身，而是：

> 只要是在这个时代因为 LLM 到来、改变真实世界结构而产生的新根问题，都可以进入候选。

因此，本阶段使用 **LLM-era transformation filter**，而不是 foundation model filter。

这保留了更宽的空间：

- 低资源语言与文化可及性；
- 科学证据可验证性；
- 公共模型评估可信度；
- AI-generated content 污染后的知识生态；
- LLM 作为教育 / 科研 / 公共服务接口后产生的新公平性与可靠性问题。

但它仍然排除：

- 传统公益 ML 问题简单换成 LLM；
- 纯 enterprise agent / productivity / automation；
- 与 LLM 主赛道完全脱节的旧应用问题。

---

## 7. 为什么不是 research OS

这次迁移明确避免把系统变重。

没有新增：

- 大量新目录；
- 自动化 agent workflow；
- 复杂 research operating system；
- 额外模板体系；
- 复杂项目管理结构。

原因是当前系统的核心需求不是“组织更多东西”，而是修复一个具体选择偏差：

> 原系统容易把“好问题”误判为“属于这个时代的博士主线问题”。

所以本阶段只做最小 patch：

- 更新 `README.md`；
- 保留 `README_original.md`；
- 在 `Every_run_principles/` 下区分 `pre-llm-era/` 与 `post-llm - era/`；
- 把加入 LLM-era filter 的四个核心文件放入 `post-llm - era/`；
- 增加本迁移说明。

---

## 8. 文件结构变化

### 8.1 原有核心结构保留

保留：

```text
root_problem_framework.md
empirical_trial_framework.md
prompts/
templates/
archive/
```

这说明 v2.1 的核心仍然成立：

> 根问题判断 + empirical sprint + researcher-owned Go / Hold / Kill。

### 8.2 Every_run_principles 拆分为两套

新增逻辑：

```text
Every_run_principles/
├── pre-llm-era/
└── post-llm - era/
```

### pre-llm-era

保存旧版稳定原则：

```text
profile_edit.yaml
value_axis.md
why_this_exists.md
```

用途：历史对照，不作为当前默认入口。

### post-llm - era

保存当前默认原则：

```text
profile_edit_llm_era.yaml
value_axis_llm_era.md
why_this_exists_llm_era.md
round1_root_problem_macro_llm_era.md
```

用途：当前 Round 1–5 的默认上传材料。

---

## 9. 四个核心文件分别改了什么

### 9.1 `profile_edit_llm_era.yaml`

新增：

- `llm_era_transformation_requirement`
- 对 research orientation 的补充；
- 对 LLM backbone 替换旧问题的反模式提醒；
- 保留 8×A100、单兵执行、不做大规模 agent/pipeline 的原约束。

设计意图：

> profile 仍然描述“我是谁”，但现在也明确“我不想做 pre-LLM 旧问题的新模型版本”。

### 9.2 `value_axis_llm_era.md`

新增：

- `LLM-era transformation filter`
- `2018 counterfactual`
- blue ocean 与时代生成性的区分。

设计意图：

> 蓝海不再单独决定 Go。候选必须同时说明为什么它是 LLM 到来后结构性变新的公共利益问题。

### 9.3 `why_this_exists_llm_era.md`

新增：

- 为什么只问“重要、长期、可深挖”还不够；
- 为什么 LLM 改变了知识接口、内容生产、评估机制和社会依赖结构；
- 为什么要防止“pre-LLM 旧问题 + 更强模型”。

设计意图：

> 让模型理解这次升级不是追热点，而是防止错把旧问题当成新时代主线。

### 9.4 `round1_root_problem_macro_llm_era.md`

新增：

- Round 1 候选必须先做 `LLM-era transformation check`；
- 每个候选必须通过 `2018 反事实测试`；
- 输出表新增 `LLM-era check` 一列；
- 如果候选大多是旧问题换 backbone，应触发 Honest-failure，建议重做 Round 1。

设计意图：

> 把 LLM-era filter 放到候选生成阶段，而不是事后排序阶段。

---

## 10. 当前默认工作流

当前默认 Round 1 上传：

```text
Every_run_principles/post-llm - era/profile_edit_llm_era.yaml
Every_run_principles/post-llm - era/value_axis_llm_era.md
Every_run_principles/post-llm - era/why_this_exists_llm_era.md
root_problem_framework.md
Every_run_principles/post-llm - era/round1_root_problem_macro_llm_era.md
```

当前默认 Sprint 仍然使用：

```text
empirical_trial_framework.md
prompts/weekly_sprint_empirical_trial.md
prompts/llm_auxiliary_for_empirical_sprint.md
templates/root_problem_card.md
templates/problem_tree.md
templates/paper_reading_matrix.md
templates/reproduction_plan.md
templates/empirical_sprint_log.md
```

区别是：每个 Sprint 要额外验证 LLM-era transformation 是否经得住一手摩擦。

---

## 11. Go / Hold / Kill 的更新

### Go 新增条件

候选必须通过：

```text
LLM-era transformation check = YES
或 PARTIAL 但经过 empirical sprint 后证明 LLM 确实重塑了问题结构
```

### Hold 新增条件

候选可以 Hold，如果：

```text
LLM-era transformation = PARTIAL
但仍需验证它不是旧问题换 backbone
```

### Kill 新增条件

候选应 Kill，如果：

```text
2018 counterfactual 显示该问题几乎同样成立，
LLM 只是更强工具或 backbone。
```

---

## 12. 当前强信号：低资源语言与文化可及性

本阶段讨论中，用户对几个候选方向的偏好形成了明确判断：

- 低资源语言与文化可及性：Go
- 科学证据可验证性：Hold
- 公共模型评估可信度：Hold / Kill
- 小数据科学中的 LLM-era 可靠性：Nearly Kill
- 可验证科学 agent：Kill

这不是 migration 的硬编码结果，但它解释了为什么 LLM-era filter 必须更精细：

> 用户真正想找的不是所有 LLM-era 新问题，而是 LLM 主赛道内的公共利益盲区，并且必须在 8×A100 资源约束下能形成博士主线。

低资源语言与文化可及性之所以强，是因为它同时满足：

- LLM 改写知识接口；
- 模型能力分布不均；
- 公共利益强；
- 商业不会自动优先解决公平版本；
- evaluation substrate 已存在；
- 8×A100 足够；
- 可形成长期问题树。

---

## 13. 非目标

本阶段不做：

- 不重写 `root_problem_framework.md`；
- 不重写 `empirical_trial_framework.md`；
- 不新增大型目录；
- 不新增 research OS；
- 不新增自动化 workflow；
- 不把低资源语言方向硬编码成唯一方向；
- 不删除 pre-LLM-era 文件；
- 不把 LLM-era filter 等同于必须做 foundation model 训练。

---

## 14. 成功标准

这次迁移成功，当且仅当：

1. 新的 Round 1 不再把多数 legacy ML public-good problem 推成 Go；
2. 每个候选都能明确回答 LLM 到底改变了什么；
3. blue ocean 与 LLM-era transformation 被区分开；
4. 每周 empirical sprint 仍然保留一手研究摩擦；
5. 系统没有变重；
6. 用户可以继续用同一套轻量流程推进博士选题。

---

## 15. 最终理解

v2.1 的核心是：

> 方向判断不能只靠 LLM，要靠 empirical sprint。

本阶段新增的核心是：

> 好问题还不够，必须是 LLM 改写世界结构后出现或被放大的时代根问题。

两者合起来，当前系统的目标变成：

> 在 LLM 改变真实世界结构之后，寻找一个真实重要、长期存在、公共利益明确、可深挖、可积累、能在 8×A100 内通过 empirical sprint 推进的博士根问题。
