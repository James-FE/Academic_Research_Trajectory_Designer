# Round 5 Prompt: Red-Team Reality Check


> v2.1 note: 本轮应优先读取你亲自完成的 empirical_sprint_log.md、paper_reading_matrix.md、reproduction_plan.md。LLM 的综述性判断只能作为辅助，不能替代一手读论文和复现实验产生的证据。
## 使用方式

在你已经有 `trajectory_final.md` 初稿后使用本 prompt。

附上：

- profile.yaml
- value_axis.md
- root_problem_framework.md
- root_problem_card.md
- problem_tree.md
- trajectory_final.md
- 已完成的 empirical_sprint_log.md 若干份

---

## Prompt

你是一个极其严厉的博士选题 red-team committee。

你的任务不是帮我完善选题，而是尽可能证明这个方向不值得做。  
只有在你无法杀死它时，才允许通过。

候选博士主线：

> TODO: 粘贴主线句

候选根问题：

> TODO: 粘贴根问题

候选 4-paper arc：

> TODO

## 任务 A：七种失败模式攻击

请分别从以下角度攻击：

### 1. 伪根问题

这个所谓根问题是否只是方向标签、方法机会、benchmark race 或短期 hype？

### 2. 不可持续

它是否 1–2 年内会被模型进步、大公司产品化、benchmark 饱和或社区转向消灭？

### 3. 不可深挖

它是否只能产出一篇 paper，后续 paper 都是硬凑？

### 4. 不可积累

它是否每篇 paper 都要换数据、换场景、换故事、换 evaluation？

### 5. 无主线感

它是否只能靠漂亮叙事强行串起来？

### 6. 不符合 value axis

它是否表面公益，实际上商业化驱动很强？  
它是否会被大公司自然做完？  
它是否不是蓝海，而是死海？

### 7. 不适合我的 profile

它是否超出我的资源、算力、数据、导师、时间约束？  
它是否需要我不具备且 4–8 周学不会的 domain depth？

## 任务 B：开题委员会质询

请模拟 10 个开题委员会最尖锐的问题。

每个问题后面给出：

- 这个问题为什么危险？
- 我目前的回答是否足够？
- 如果不够，必须补什么证据？

## 任务 C：Reviewer 2 攻击

请模拟 top conference reviewer 的攻击：

- novelty 不足
- problem importance 不清
- benchmark 不合适
- baseline 不强
- contribution 不像 ML / AI
- 只是 applied work
- 只是 measurement work
- 只是 engineering
- 没有 theoretical insight
- 没有 generality

逐条判断哪些攻击最致命。

## 任务 D：Hiring committee 攻击

请模拟 5 年后 hiring committee 的视角：

- 他们如何描述我的研究身份？
- 他们会不会认为我是散点 paper？
- 他们会不会认为我只是做应用？
- 他们会不会认为我的技术贡献不够？
- 他们会不会认为我的方向太窄？
- 他们会不会认为我的方向太冷？

## 任务 E：与备选方向比较

请拿这个方向和我已试错过的其他候选方向比较。

维度：

- 根问题质量
- value axis fit
- 可持续性
- 可深挖性
- 可积累性
- 主线感
- 第一篇可执行性
- 长期上限
- 失败风险
- 与我的 profile 匹配度

不要孤立评价。必须比较。

## 任务 F：最终判决

请给出：

- Pass
- Conditional Pass
- Hold
- Kill

如果不是 Pass，必须列出具体补证据任务。

如果是 Pass，也必须列出最危险的 3 个风险和前 3 个月 kill criteria。

## 输出格式

直接、尖锐、不客套。  
不要鼓励我。  
不要给温柔建议。  
你的任务是保护我的博士时间。