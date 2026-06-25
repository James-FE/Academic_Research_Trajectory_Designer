# Round 0 Prompt: M0 Profile + Root Problem Calibration

## 使用方式

当 profile.yaml 还不完整，或者你不确定自己的 value axis / constraints 是否足够清晰时，使用本 prompt。

把以下内容复制到 ChatGPT / Gemini Deep Research，并附上：

- profile.yaml 或 profile_template.yaml
- value_axis.md
- why_this_exists.md
- root_problem_framework.md

---

## Prompt

你是一位资深 ML / AI research PI，也是我的 adversarial research advisor。

你的任务不是帮我找方向，而是先判断我的选题输入是否足以支持高质量方向判断。

请完整阅读我提供的 profile.yaml、value_axis.md、why_this_exists.md、root_problem_framework.md。

我的目标不是选择一个热门 topic，而是找到一个博士阶段可持续深耕的“根问题”：

> 在什么真实场景中，面对什么稳定约束 / 核心矛盾，如何实现什么长期目标？

## 任务 A：检查 profile 是否足够诚实

请逐项评估：

1. 我的 technical floor 是否写清楚？
2. 我是否把已有背景误写成 ceiling？
3. 我的 unfair advantages 是否是真优势，还是泛泛自我描述？
4. 我的资源约束是否足够具体？
5. 我的 cannot_afford_to_spend_6_months_on 是否足够现实？
6. 我的 value axis 是否会过窄导致没有可做方向？
7. 我的 value axis 是否过松导致热门方向溜进来？
8. 我的导师 / 实验室 / 学校约束是否足够明确？

每一项请给出：

- 通过 / 不通过 / 信息不足
- 原因
- 需要我补写的具体字段
- 如果不补，会导致什么选题偏差

## 任务 B：识别我的三类优势

请把我的优势分成三类：

(a) 直接 leverage 当前背景的方向  
(b) 弱相关但 problem 重要的方向  
(c) 需要 4–8 周新学但可能是全局最优的方向

注意：不能把所有方向都 anchor 到我已有背景。我的既有背景是 floor，不是 ceiling。

请指出模型在后续推荐时最容易犯的 advantage anchoring bias。

## 任务 C：生成我的根问题过滤器

请基于我的 profile 和 value axis，生成一份“根问题硬过滤器”，包括：

1. 必须满足的条件
2. 直接淘汰的条件
3. 需要特别警惕的伪蓝海
4. 需要特别警惕的伪可执行方向
5. 需要特别警惕的伪主线

## 任务 D：给出修改后的 profile.yaml patch

请给出一个可直接复制的 YAML patch，只包含建议我补充或修改的字段。

## 输出格式

中文为主。直接、尖锐，不客套。  
如果我的输入不足以进入 Round 1，请明确说：“不建议进入 Round 1”，并说明必须补齐什么。
