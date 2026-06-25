# Reproduction Plan

## Candidate root problem

> 在 ______ 真实场景中，面对 ______ 稳定约束 / 核心矛盾，如何实现 ______ 长期目标？

## Target

- Paper / repo / benchmark:
- URL:
- Why this target is representative:
- Why it is feasible this week:

## Minimal reproduction goal

不要一开始追求完整复现。先定义最小目标：

- [ ] Run official demo
- [ ] Run evaluation script
- [ ] Reproduce one reported number
- [ ] Reproduce one qualitative failure case
- [ ] Compare with one baseline
- [ ] Run on one small data slice

本周目标：

## Environment

- OS:
- Python / CUDA / framework version:
- Hardware:
- Expected setup time:

## Data

- Dataset:
- URL:
- Size:
- License / access:
- Preprocessing needed:

## Steps

```bash
# TODO: setup commands
```

```bash
# TODO: minimal run commands
```

## Expected outputs

- Metric:
- Qualitative output:
- Logs:
- Figures:

## Success criteria

最小成功标准：

- [ ] Code runs
- [ ] Data loads
- [ ] Evaluation completes
- [ ] Result roughly matches paper / baseline
- [ ] Failure case observable

## Failure diagnosis

如果跑不通，判断属于哪类：

| Type | Signal | Direction implication |
|---|---|---|
| Environment issue | dependency / version / CUDA | low implication |
| Repo decay | old code, missing files | medium implication |
| Data access issue | unavailable / private / huge | high implication |
| Compute barrier | too expensive | high implication |
| Unclear claim | cannot map paper to code | medium implication |
| Evaluation fragility | metric unstable / script unclear | high implication |

## Minimal perturbation

跑通后做一个小扰动：

- Change:
- Why:
- Expected insight:

## What this reproduction should tell me

这次复现完成后，我应该能判断：

1. 第一篇 paper 是否 3 个月内可启动。
2. Evaluation substrate 是否可靠。
3. 当前方法的 failure mode 是否真实可见。
4. 这个方向是否有可积累资产。
