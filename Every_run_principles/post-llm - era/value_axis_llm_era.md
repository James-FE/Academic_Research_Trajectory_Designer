# Value Axis

## 核心定义

我对“蓝海”的定义是：

> 对人类有益，但暂时商业化吸引力不足，因此主流资本、大公司和大量博士生不会过度拥挤的研究方向。

这不是软偏好，而是硬过滤器。

一个方向如果明显违反这个 value axis，即使它很热门、很容易发 paper、很容易找工作，也不应该进入我的博士主线候选池。

## v2 补充：蓝海必须落到根问题，而不是方向标签

不能问：

> 这个方向是不是蓝海？

要问：

> 这个根问题是不是蓝海？

因为同一个方向标签下可能同时存在蓝海和红海。

例如：

- “LLM reasoning”作为标签很拥挤。
- 但“在低资源公共科学任务中，如何让模型形成可验证的因果推理链”可能仍然有蓝海空间。

反过来：

- “AI for public good”作为标签看起来符合价值轴。
- 但如果具体根问题需要 2 年拿数据、没有可复用 benchmark、无法形成第一篇 paper，那对我就是死海。

## v2.1 补充：LLM-era transformation filter

在原有 blue ocean 过滤器之前，必须先增加一个时代过滤器：

> 这个根问题是否因为 LLM / AI systems 的到来而新出现、被结构性放大，或变得系统可研究？

这不是要求所有候选都必须研究 foundation model 本身，也不是要求从模型架构出发。它要求候选根问题必须说明：LLM 如何改变了真实场景中的知识接口、数据生产方式、评估机制、社会依赖结构、模型能力分布或 failure mode。

判断规则：

- 如果该问题在 2018 年也几乎以同样形式成立，只是现在可以换成 Transformer / LLM backbone，则默认降级为 legacy ML public-good problem。
- 如果问题本来存在，但 LLM 显著改变了它的规模、影响、失败模式或可研究性，则进入 Hold / Go 候选。
- 如果没有 LLM，这个问题不会以当前形式存在，或不会如此尖锐、可评估、长期重要，则优先进入 Go 候选池。

注意：

- 蓝海回答的是“竞争结构”：为什么商业资本、大公司和大量博士生不会自然把公共利益版本做完。
- LLM-era filter 回答的是“问题生成机制”：为什么这是这个时代长出来的新根问题，而不是旧问题换新工具。
- 两者必须同时满足。蓝海但没有时代生成性，容易变成“有价值但像文物”的旧 ML 公益问题；LLM-era 但不蓝海，容易滑入大厂红海。

## 核心原则

一个根问题只有同时满足以下条件，才值得进入战略候选池。新增规则：候选还必须通过 LLM-era transformation filter，证明它不是 pre-LLM 旧问题换新 backbone：

1. 因 LLM / AI systems 的到来而新出现、被结构性放大，或变得系统可研究。
2. 对人类、科学、公共利益或长期社会韧性有明确正外部性。
3. 商业化压力相对较弱，或者不是由商业化主要驱动。
4. 当前 AI 社区还没有完全拥挤。
5. 学术界仍有独立贡献空间。
6. 有公开可复用的 evaluation substrate：dataset / benchmark / metric / baseline 至少具备其一，最好具备多个。
7. 我能在 3 个月内启动第一篇 paper 的 credible baseline。
8. 它能自然长出 3–5 个递进子问题。
9. 它能够支撑博士论文 narrative，而不是只产生孤立 paper。
10. 它的困难对我而言是非对称的：大公司 / 大团队没有强动机或结构优势，但我可以凭问题意识、长期沉浸、跨域视角、单兵执行切入。

## 硬排除方向

以下方向默认排除，除非能给出极强反例：

- LLM-for-productivity
- enterprise agent tooling
- AI for finance
- AI for legal automation
- AI for advertising / marketing / growth
- 主要服务商业效率提升的自动化系统
- 纯 benchmark race，缺少真实科学或社会价值的问题
- 大公司已有压倒性数据、算力、产品闭环优势的方向
- 需要长期数据谈判 / 私有关系 / 大规模工程团队才能启动的方向
- 需要 6 个月以上纯 domain immersion 才能提出第一篇 paper 的方向
- 没有被社区接受的 synthetic-to-real evaluation protocol、只能靠 synthetic data 证明第一篇 paper 的方向

## “困难”必须非对称

蓝海的困难必须是“对大资源方困难、对我的 unfair advantage 不困难”。

通过的困难：

- 大公司没动机做，但开源数据 + 单兵算力可以启动。
- 需要长期沉浸思考，但不需要长期等待外部资源。
- 需要 problem-driven 视角，但不需要复杂工程团队。
- 可以在 3 周内跑通 credible baseline，然后把贡献放在 problem framing、robustness、generalization、interpretability、uncertainty 或 cross-domain insight 上。
- 需要连接两个社区，但两个社区都有公开数据和公开 baseline。

不通过的困难：

- 数据需要长期谈判 / 关系拿到。
- 需要 6 个月以上纯 domain immersion 才能开始。
- 需要多 agent / pipeline / 团队工程作为前提。
- 第一篇只能靠自造 benchmark 支撑。
- 贡献只能落在“我调了一个更好的模型”，而不是根问题的机制性推进。

## Evaluation substrate 是非对称困难的关键 case

对单兵博士生而言，“需要自己造 benchmark / dataset / metric / evaluation protocol 才能启动”是一类典型的对称困难。

因此，蓝海方向必须满足：

> 已有可复用的公开 dataset / benchmark / metric / baseline，即使社区还没有充分挖掘背后的真实问题。

我寻找的不是无人涉足的荒地，而是：

> 已有 evaluation substrate 但被低估的公共利益 / 科学问题。

如果一个方向需要 6 个月以上的 data wrangling / task definition / benchmark construction 才能投出第一篇，它对我而言是死海，即使它的核心问题很蓝海。

## 最终检验问题

当我评估一个根问题时，需要问：

1. 这个根问题是否因为 LLM / AI systems 到来而新出现、被结构性放大，或变得系统可研究？
2. 如果回到 2018 年，它是否也几乎以同样形式成立？如果是，是否应降级为 legacy ML public-good problem？
3. 这个根问题 5 年后仍然重要吗？
4. 如果它成功，对谁有真实帮助？
5. 它背后的核心矛盾是什么？是否长期稳定？
6. 为什么大公司不会自然把它做完？
7. 为什么大多数博士生现在没有押注它？
8. 我相比普通博士生有什么切入优势？
9. 这个困难是否非对称？
10. 有无公开 evaluation substrate？
11. 第一篇 paper 是否能在 3 个月内启动？
12. 它能否自然形成 4 篇 paper 的递进关系？
13. 如果失败，最可能死在哪里？
14. 它是否能用一句话成为我的博士主线？
