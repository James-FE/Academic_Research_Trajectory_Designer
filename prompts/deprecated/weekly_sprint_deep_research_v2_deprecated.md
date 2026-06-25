# Weekly Sprint Prompt: One Root Problem per Week

## 使用方式

这是你“一周一个新方向快速试错”的主 prompt。

每周只选择一个候选根问题。  
不要同时试多个方向。  
不要试图在一周内确定博士最终方向。  
这一周只有一个目标：

> 判断这个根问题是 Go / Hold / Kill。

附上：

- profile.yaml
- value_axis.md
- root_problem_framework.md
- Round 1 中该候选的原始输出（如果有）
- 已有 root_problem_card.md（如果有）

---

## Prompt

你是我的 Deep Research analyst + adversarial research advisor。

本周我要快速试错一个候选根问题。  
你的任务是帮我在一周内判断它是否值得进入深挖，而不是帮我证明它值得做。

候选根问题：

> TODO: 使用句式“在 ______ 真实场景中，面对 ______ 稳定约束 / 核心矛盾，如何实现 ______ 长期目标？”

如果我给你的候选只是方向标签，请先把它改写成 3–5 个可能的根问题版本，并要求我选择一个。  
如果无法改写成根问题，请直接判为 Kill。

## Deep Research 要求

你必须搜索并引用可验证资料。每个关键判断必须有来源支持。

优先使用：

- 近 3 年论文
- arXiv / DOI / official proceedings
- official dataset / benchmark / challenge pages
- GitHub repos with active baselines
- Papers with Code / Hugging Face / Kaggle / official data portals
- named researchers and their recent papers
- survey / position paper / benchmark paper

不要依赖：

- 模糊博客
- 无来源行业观点
- 没有 URL 的 lab 名称
- “大家都在做”
- 只有 abstract-level 的二手总结

如果证据不足，请说证据不足，不要补脑。

## Day 1：根问题重写与真实性检查

请完成：

1. 把候选改写为标准根问题句。
2. 说明它容易被误认为哪个方向标签。
3. 识别真实场景、稳定约束、长期目标。
4. 找 5–8 条证据说明这个问题真实存在。
5. 判断这是否是方法 hype 制造出来的问题。

输出：

- 标准根问题句
- 真实性判断：强 / 中 / 弱
- 主要证据
- 初步 Kill 风险

## Day 2：Evaluation substrate 审计

请查找：

- dataset
- benchmark
- metric
- baseline
- leaderboard
- shared task / challenge
- official code
- survey / taxonomy

每项都必须有 URL。

请标注：

- 第一篇 paper 可直接用
- 需要轻微改造
- 需要大量工程，不建议
- 不可信 / 不相关

输出：

- Evaluation substrate table
- 是否满足“3 个月 entry”硬门槛
- 缺口是什么

## Day 3：社区与竞争格局

请查找：

1. 过去 3 年最相关的 10–15 篇 paper。
2. 5 个最相关 researcher / team。
3. 主要 community / venue / challenge。
4. 大公司是否已经有结构性优势。
5. 该问题为什么没有被大量博士生过度拥挤。

输出：

- community map
- crowdedness 判断
- 真冷门 vs 死海判断
- 我可能的差异化切口

## Day 4：问题树生成

请生成一棵问题树：

```text
根问题
├── 子问题 1
├── 子问题 2
├── 子问题 3
└── 子问题 4
```

每个子问题说明：

- 为什么自然从根问题长出？
- 需要什么 evidence substrate？
- 可能形成哪篇 paper？
- 继承前面节点的什么资产？
- 如果做不出来，后续是否崩塌？

输出：

- problem_tree.md 草案
- 4-paper arc 草案
- 可积累资产列表
- 散点风险

## Day 5：张老师四性评分

请对该根问题打分：

| 维度 | 0-5 | 理由 | 证据 |
|---|---:|---|---|
| 可持续性 | | | |
| 可深挖性 | | | |
| 可积累性 | | | |
| 主线感 | | | |

并额外评分：

| 维度 | 0-5 | 理由 | 证据 |
|---|---:|---|---|
| Value axis fit | | | |
| Evaluation substrate | | | |
| 非对称困难 | | | |
| 3 个月 entry | | | |
| 竞争压力 | | | |

输出：

- Go / Hold / Kill 初判
- 最大不确定性
- 需要我亲自验证的点

## Day 6：第一篇 paper 最小可行设计

请设计 2–3 个 first paper entry。

每个包括：

- title sketch
- problem statement
- dataset / benchmark
- baseline
- minimum viable contribution
- 3 个月计划
- 需要新学的 skill
- 第一个 kill point
- 如何自然引出 Paper 2

输出：

- 推荐 entry
- 备用 entry
- 不推荐 entry
- 原因

## Day 7：最终决策

请基于前 6 天内容，输出一份可保存为 weekly_sprint_log.md 的结论。

必须包括：

1. 标准根问题句
2. 是否真实重要
3. 是否符合 value axis
4. 是否有 evaluation substrate
5. 是否能 3 个月启动
6. 是否能长出问题树
7. 是否有可积累资产
8. 是否有主线感
9. 最可能失败点
10. Go / Hold / Kill 判决

### 判决规则

Go：

- 根问题真实；
- value axis 通过；
- evaluation substrate 明确；
- 第一篇 3 个月可启动；
- 问题树自然；
- 4-paper arc 不是拼盘。

Hold：

- 根问题强，但某个关键证据不足；
- 一周内未能确认 evaluation substrate，但存在强迹象；
- 需要亲自跑一个 baseline 才能判断。

Kill：

- 只是方向标签，不是根问题；
- 没有公开 evaluation substrate；
- 需要长期数据谈判；
- 3 个月无法启动第一篇；
- 4 篇 paper 明显是硬凑；
- value axis 不通过；
- 大公司有压倒性优势；
- 只是 benchmark race。

## 输出格式

请最后输出三个 markdown artifact：

1. `root_problem_card.md`
2. `problem_tree.md`
3. `weekly_sprint_log.md`

不要只给行业综述。  
不要为了好看而模糊判决。  
我需要的是战略判断。
