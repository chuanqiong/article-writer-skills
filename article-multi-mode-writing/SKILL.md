---
name: article-multi-mode-writing
description: Use when drafting with coach, fast, hybrid, or outline-constrained modes and you need strict mode selection before writing
---

# Article Multi Mode Writing

## Overview
本技能负责正式写稿阶段，覆盖教练模式、快速模式、混合模式和提纲约束模式。核心要求是先选模式，再写稿，推荐不是授权。

## When to Use
brief、spec、研究或素材已经基本到位，用户要开始写初稿，或用户明确要按固定提纲生成立项报告、开题报告、技术报告时，使用本技能。

## Required Questions

开始前，先问这 3 个：

1. 你对这篇文章的 AI 味容忍度是多少？（越自然越好 / 适度即可 / 不在意）
2. 你打算花多少时间参与写作？（全程参与 / 写完我来改 / 帮我快速出稿）
3. 你有没有已经想好的提纲或结构？

## Hard Gates
- 不要自动替用户选模式——必须展示四种模式并等待用户明确选择。
- 不要因为 brief 里有推荐模式就自动进入对应模式。
- 不要跳过结果演算就开始写稿——进入写稿前要做一次结果演算: 输入质量、风险、预估 AI 味、时间成本。
- 不要在提纲约束模式下跳过结构确认就开始生成。
- 不要学过作者风格却在写稿时全部洗成通用语气——如果已存在 `style-profile`，必须显式继承。
- 不要素材不足却承诺低 AI 味结果。
- 不要把提纲约束模式写成普通自由发挥。

## Workflow
1. 检查前置输入:
   - brief
   - specification
   - 研究资料
   - 素材等级
   - style-profile 或 persona
2. 展示模式菜单:
   - 教练模式: AI 提问, 用户自己写
   - 快速模式: AI 生成初稿, 用户重审
   - 混合模式: AI 写框架, 用户写核心
   - 提纲约束模式: 用户给固定结构, AI 按结构展开
3. 做结果演算:
   - brief 质量
   - 素材等级
   - 结构清晰度
   - 预估 AI 味
   - 返工次数和总耗时
4. 用户确认后执行对应模式:
   - 教练模式: 逐段提问, 不代写可直接使用的内容
   - 快速模式: 生成完整初稿, 再迭代修改
   - 混合模式: 先写框架和过渡, 用户补核心内容
   - 提纲约束模式: 解析提纲, 确认结构, 收集背景, 按章节生成
5. 在任一模式下，如果存在 `style-profile`，都要在以下层面继承:
   - 开头节奏
   - 句长偏好
   - 常用表达
   - 结尾 CTA 强度
6. 如果用户没有自带提纲，可参考:
   - `references/outlines/project-proposal.yaml`
   - `references/outlines/thesis-opening.yaml`
   - `references/outlines/technical-report.yaml`

## Wait Points
- 模式菜单出来后，先等用户选模式。
- 结果演算出来后，如风险明显，先等用户决定继续、优化还是改模式。
- 提纲解析出来后，先等用户确认结构。

## Output Contract
- 明确记录所选模式、风险、预估 AI 味和预计耗时。
- 输出 draft 时，说明哪些部分来自 AI，哪些部分必须由用户补。
- 提纲模式下，输出统一术语和背景信息要求，避免章节前后不一致。
- 如果用了 `style-profile`，说明本稿继承了哪些风格约束，避免后续审校时误删作者特征。

## Common Mistakes
- 自动替用户选模式。
- 素材不足却承诺低 AI 味结果。
- 把提纲约束模式写成普通自由发挥，导致结构跑偏。
- 已经学过作者风格，却在写稿时全部洗成通用互联网语气。

## Quality Self-Check

### error（阻塞）
- [ ] 没展示模式菜单就自动进入某个模式
- [ ] 有 style-profile 但写稿时没继承

### warning（需要修正）
- [ ] 没做结果演算就开始写稿
- [ ] 提纲模式下没先确认结构就开始生成

### info（建议改进）
- [ ] 没有说明 draft 中哪些部分来自 AI、哪些需用户补
- [ ] 提纲模式下没有统一术语和背景信息

## Reference Files
- `references/outlines/project-proposal.yaml`
- `references/outlines/thesis-opening.yaml`
- `references/outlines/technical-report.yaml`
- `references/style/style-profile-schema.md`
