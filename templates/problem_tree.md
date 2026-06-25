# Problem Tree

## Root Problem

> 在 ______ 真实场景中，面对 ______ 稳定约束 / 核心矛盾，如何实现 ______ 长期目标？

## Mainline Sentence

> 我博士期间研究的是：在 ______ 场景中，面对 ______ 约束，如何实现 ______ 目标。

## Problem Tree

```text
Root Problem
├── P1:
├── P2:
├── P3:
└── P4:
```

## P1: Foundational Entry

核心问题：

为什么必须先做：

需要的数据 / benchmark / baseline：

最小贡献：

建立的可复用资产：

如何引出 P2：

失败风险：

Kill criteria：

## P2: First Mechanism / Method

核心问题：

继承 P1 的什么资产：

解决 P1 暴露出的哪个瓶颈：

方法路径：

建立的可复用资产：

如何引出 P3：

失败风险：

Kill criteria：

## P3: Generalization / Robustness / Transfer

核心问题：

继承 P1–P2 的什么资产：

为什么不是独立散点 paper：

如何扩展根问题边界：

建立的可复用资产：

如何引出 P4：

失败风险：

Kill criteria：

## P4: Synthesis / System / Impact

核心问题：

继承 P1–P3 的什么资产：

如何证明主线不是拼盘：

系统性贡献：

可能影响：

失败风险：

Kill criteria：

## Asset Accumulation

| Asset | Starts in | Reused by | Worth maintaining? | Notes |
|---|---|---|---|---|
| Evaluation protocol | P1 | P2/P3/P4 | | |
| Baseline code | P1 | P2/P3 | | |
| Failure taxonomy | P1 | P2/P4 | | |
| Theoretical lens | | | | |
| Community map | | | | |

## Anti-Fragmentation Check

| Paper | Can be linked to mainline? | Inherits previous assets? | Naturally leads to next? | Fragmentation risk |
|---|---|---|---|---|
| P1 | | | | |
| P2 | | | | |
| P3 | | | | |
| P4 | | | | |

## Final Judgment

- Is this a natural problem tree?
- Is any paper forced?
- If one paper is removed, does the narrative collapse or remain intact?
- Does the mainline sentence still hold?


## Evidence discipline

每个子问题节点必须标注证据来源：

- 来自哪篇论文？
- 来自哪次复现实验？
- 来自哪个 failure mode？

如果一个节点只能由 LLM 想象出来，而没有一手阅读 / 复现证据支撑，标记为 speculative，不要进入博士 narrative。
