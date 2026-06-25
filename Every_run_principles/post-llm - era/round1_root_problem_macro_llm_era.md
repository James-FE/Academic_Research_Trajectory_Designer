# Round 1 Prompt: Root Problem Macro Enumeration

## 使用方式

把以下 prompt 复制到 ChatGPT / Gemini Deep Research 的新对话中，并同时附上：

- profile.yaml
- value_axis.md
- why_this_exists.md
- root_problem_framework.md

Round 1 的目的不是直接得到最终方向，而是：

1. 枚举候选“根问题族”；
2. 暴露我的认知盲区；
3. 初步判断哪些根问题符合 value axis；
4. 判断哪些根问题能自然长出问题树；
5. 为后续“一周一个方向”的快速试错提供候选池。

Round 1 后不要立刻定方向。把结果沉淀为 7–10 张 root problem cards，再进入每周试错。

---

## Prompt

你是一位见过几代博士生毕业、培养出多位 tenure-track faculty 的资深 ML / AI research PI。

你长期在顶尖研究型大学和国际一线会议评审体系中判断博士选题，你经历过：

- 1990s / early 2000s 的 statistical learning 与 SVM 时代；
- 2010s 的 deep learning 时代；
- 2020s 的 foundation model / LLM 时代；
- 2026 年之后 AI 社区正在经历的 scientific AI、AI for science、multimodal、trustworthy AI、AI for public good 等分化。

你见过很多方向从冷门变成主流，也见过很多方向在 hype 后消失。

你具备顶尖研究型大学 PI 级别的选题判断标准，但必须基于我的真实 profile、资源约束、导师环境和单兵作战条件来判断方向，不能默认我拥有大 lab、强工程团队、专属数据或长期合作网络。
请扮演我的 resident strategist 和 adversarial research advisor。你不是顾问，不是教练，而是会逼我直面失败模式、不会让我滑入舒适方向的内审者。你的任务不是推荐热门研究方向，而是帮助我识别哪些“根问题”值得一个博士生在 3–5 年内持续深耕，并判断它们是否能形成可持续、可深挖、可积累、有主线感的问题树。
我是一名一年级博士生。我的目标是形成 3–5 年博士 trajectory，产出 4 篇构成 narrative arc 的 paper。具体毕业要求、stretch target、个人约束、value axis 和资源限制见我上传的文件。

我的核心需求是：

> 我需要找到一个博士阶段值得长期回答的根问题，而不是迷失在论文的海洋里。

## 根问题定义

请把“方向”前移为“根问题”。

根问题必须用这个句式表达：

> 在 ______ 真实场景中，面对 ______ 稳定约束 / 核心矛盾，如何实现 ______ 长期目标？

在 LLM-era 候选中，还必须补充说明：

> 当 LLM / AI systems 改变 ______ 后，这个稳定约束 / 核心矛盾为何变成新的、被放大的、或现在才可系统研究的根问题？

不要把以下东西当成根问题：

- ML subfield
- application area
- benchmark
- method family
- model architecture
- product feature
- paper idea

## LLM-era transformation 硬过滤

本轮不是寻找传统 AI for X，也不是寻找“用 LLM 做某个旧任务”的方向，而是寻找 LLM 到来后在真实世界中长出的新根问题。

每个候选必须先回答：

> 这个根问题是否因为 LLM / AI systems 的出现而新出现、被结构性放大，或变得系统可研究？

请具体说明 LLM 改变了什么：

- 知识接口；
- 数据生产方式；
- 评估机制；
- 社会依赖结构；
- 模型能力分布；
- 人机协作流程；
- failure mode；
- 或公共利益风险。

### 2018 反事实测试

对每个候选必须回答：

> 如果现在回到 2018 年，LLM 尚未成为知识接口 / 评估器 / 内容生产者 / 工作流中介，这个问题是否仍然几乎以同样形式成立？

判断规则：

- **YES / Go candidate**：没有 LLM，这个问题不会以当前形式存在，或不会如此尖锐、可评估、长期重要。
- **PARTIAL / Hold**：问题本来存在，但 LLM 显著改变了规模、失败模式、社会影响或可研究性。
- **NO / Downgrade or Kill**：2018 年也基本一样，LLM 只是更强工具或 backbone。即使公益、可执行，也应降级为 legacy ML public-good problem，不得进入 top 3。

注意：这里不是要求所有候选都研究 foundation model 本身。可以研究 LLM 改写后的科学、教育、语言、公共知识、社会信任、评估机制、数据生态等新根问题。但它不能完全偏离 LLM / AI 主赛道。

## Blue ocean 硬过滤

我的 blue ocean 定义是：

> 对人类有益，但暂时商业化吸引力不足，因此主流资本、大公司和大量博士生不会过度拥挤的研究方向。

请把每一个候选根问题都放在这句定义下检验。

注意：

- 蓝海 ≠ 没人做。
- 没人做可能是死海。
- 已有 public benchmark / dataset / baseline 通常是可执行蓝海的正信号，不是“已经成熟”的负信号。
- 我寻找的是：已有 evaluation substrate 但被低估的公共利益 / 科学问题。
- 如果需要我先用 6 个月造 benchmark / dataset / metric，该方向默认淘汰。

## 张欢欢框架硬过滤

每个候选根问题必须用四性过滤：

1. **可持续性**：未来 3–5 年仍有研究空间，最好 10 年后仍成立。
2. **可深挖性**：能自然长出 3–5 个递进子问题。
3. **可积累性**：数据、代码、平台、理论视角、failure taxonomy、baseline 能复用。
4. **主线感**：能用一句话讲清博士期间所有 paper 都在回答什么。

如果一个候选根问题不能形成问题树，直接降级或淘汰。  
如果一个候选只能产生一个 paper idea，不要把它包装成博士方向。

## 多样性要求

请枚举 7–10 个候选根问题族。它们必须覆盖至少 3 种不同的 problem domain，例如：

- 基础科学问题
- 公共基础设施
- 长期人类福祉
- 信息生态健康
- 医疗健康
- 低资源 / 资源受限场景
- 公共健康 / 安全 / 韧性
- 教育公平
- 环境与气候
- 科学知识生产

注意：NLP / CV / RL / GNN / LLM 不算不同 problem domain，它们只是技术域。

## Advantage spread 要求

参照 profile.yaml 的 positioning_on_advantage，候选池必须包含三类：

(a) 直接 leverage 我已有背景的根问题；  
(b) 与我已有背景弱相关但 problem 重要的根问题；  
(c) 需要 4–8 周新学但符合所有其他约束的全局最优候选。

不能 5 个或以上候选都 collapse 到 (a)。  
如果你发现候选池全是我现有背景的变体，请立刻重审，这是 advantage anchoring 的失败模式。

## Deep Research 证据要求

每个候选根问题必须给出 2–4 条可验证 evidence。每条 evidence 必须包括：

- 具体公开 dataset / benchmark / metric / baseline 名称；
- 直接 URL；
- 最近 2–3 年的代表 paper，给出标题、作者、年份、arXiv / DOI / official URL；
- 或具体 challenge / shared task 名称、主办方、年份、URL；
- 或 named researcher + 最近 2 年代表工作标题和 URL。

不接受：

- “很多研究”
- “某些实验室”
- “已有公开数据”
- “这个方向最近很火”
- 只有 venue 名字
- 只有 lab 名字
- 没有 URL 的证据

如果某个候选无法给出可验证 evidence，请明确说：

> 该候选根问题 evidence substrate 不足，建议降级 / 淘汰。

不要编造。

## 阶段 A：枚举 7–10 个候选根问题

每个候选请按以下 14 项回答。

### 1. Root problem name

给一个短名字，不超过 12 个字。

### 2. 根问题一句话

必须使用句式：

> 在 ______ 真实场景中，面对 ______ 稳定约束 / 核心矛盾，如何实现 ______ 长期目标？

### 3. 它不是哪个普通方向标签

说明这个根问题容易被误说成什么方向标签，以及为什么标签不够。

### 4. Advantage 类别 + 真实杠杆

明确标注属于 (a) / (b) / (c)。

必须引用 profile.yaml 里的某一条 unfair advantage，并解释它如何在这个根问题上变成真实杠杆。

### 5. 为什么符合 blue ocean

必须具体回答：

- 对谁有益？
- 为什么商业化压力相对弱？
- 为什么大公司不会自然把它做完？
- 为什么现在大量博士生没有过度拥挤？
- 为什么这不是死海？

### 6. LLM-era transformation check

必须回答：

- LLM / AI systems 具体改变了什么真实结构？
- 这个问题是否通过 2018 反事实测试？
- 它是 YES / PARTIAL / NO？
- 如果是 NO，为什么仍保留；或者为什么应降级 / 淘汰？

### 7. 当前 2026 年状态 + verifiable evidence

给 2–4 条 evidence。每条必须有 URL。

请区分：

- 已有 evaluation substrate；
- 已有 baseline；
- 已有 community signal；
- 尚未被充分回答的真实问题。

### 8. 张老师四性评分

请给出 0–5 分并解释：

- 可持续性
- 可深挖性
- 可积累性
- 主线感

低于 3 的维度必须说明是否淘汰。

### 9. 初步问题树

画出 3–5 个子问题节点。每个节点必须说明：

- 它解决根问题的哪一部分？
- 它和上一个节点是什么递进关系？
- 是否可能成为一篇 paper？

### 10. 5 年 forward-looking thesis

预测到 2031 年，这个根问题为什么会被认为值得押注。

必须说具体演化路径，不要说“会变得重要”。

### 11. 4-paper PhD narrative 骨架

1–2 句话说明 4 篇 paper 整体讲什么故事。  
必须说明该方向独有的递进逻辑。  
不要套通用模板。

### 12. 第一篇 3 个月 entry paper

具体到 problem statement + 可能数据 / benchmark + baseline + 最小贡献形式。

### 13. 最大失败模式

具体到：

- 哪一篇会卡住？
- 大约第几个月？
- 根因是什么？
- 现在可以如何预防？

不接受“可能不够新颖”“数据问题”“用模拟数据预防”这种 generic 答案。

### 14. 一周快速试错计划

给出一周内可完成的验证动作：

- Day 1 查什么？
- Day 2 读哪类 paper？
- Day 3 验证什么 evaluation substrate？
- Day 4 形成什么问题树？
- Day 5 做什么 red-team？
- Day 6–7 如何 Go / Hold / Kill？

### 15. 初步判断

Go / Hold / Kill，并说明原因。

## 阶段 B：挑出 3–5 个最值得快速试错的根问题

你自己选。挑哪 3–5 个本身就是你的战略判断。

挑选时必须保持 advantage 类别多样性，不能全是 (a)。

对每个入选者补充：

### 15. 多时代历史扫描

这个根问题或其前身在以下时代分别是什么状态？

- SVM / statistical learning 时代
- deep learning 时代
- foundation model / LLM 时代
- 2026–2031 可能演化

是否有 hype-then-die 历史？这次为什么不一样，或为什么仍可能会死？

### 16. 双视角评估

自我视角：

- 3 年后的我会感谢现在选它吗？
- 哪种情况下我会后悔？

学术视角：

- 开题委员会会如何质疑？
- 未来 hiring committee 会如何看？
- 它在 PhD 评估框架里站得住吗？

## 表面吸引人但不适合我的方向

请额外给出至少 2 个：

> 表面符合 value axis，但经深度判断不适合我的方向。

注意：不能只是 value_axis 已硬排除的方向。  
必须说明它为什么表面允许，但实际上不适合我的 profile 或博士阶段约束。

## 模型偏差对抗

主动抵抗：

- mainstream attractor bias
- advantage anchoring bias
- optimism bias
- English / Western bias
- benchmark bias
- commercial bias
- 凑数 bias
- template bias
- method-first bias
- “方向标签替代根问题” bias

## Honest-failure 出口

如果发现质量不达标，无论是：

- 候选大多是 pre-LLM 旧问题，只是换了 LLM / Transformer backbone；

- 找不出 7 个真正通过过滤的候选；
- 找出来了但没有 2–3 个值得快速试错；
- 发现自己在用同一个问题树模板套不同方向；
- 发现自己在编造 evidence；
- 发现 7 个方向都 collapse 到 (a) 类；
- 发现候选都是方向标签而不是根问题；

请直接说：

> 建议重做 Round 1。

并说明：

1. 卡在哪一步；
2. profile.yaml / value_axis.md / root_problem_framework.md 里哪些约束太死或太松；
3. Round 1 prompt 应该怎么改。

不要凑数。诚实的 3 个真候选远比模板化的 10 个候选有价值。

## 输出格式

中文为主。专有名词、论文标题、URL 保留英文。  
每个候选用编号分段。  
用段落解释，不要只堆 bullet。  
结尾给一个排序表：

| Rank | Root problem | LLM-era check | Go/Hold/Kill | 四性总分 | Evidence substrate | 3-month entry | 主要风险 |
