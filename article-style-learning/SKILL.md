---
name: article-style-learning
description: Use when learning an author's voice from sample articles or building a reusable style profile before planning, drafting, or humanizing text
---

# Article Style Learning

## Overview
本技能用于从历史文章、范文或明确的人设要求中提炼作者风格，产出可复用的 `style-profile`。它不做模型训练，而是把风格拆成可在 planning、writing、editing 阶段复用的约束。

## When to Use
用户说“学我的风格”“按这个作者口吻写”“保持品牌语气一致”，或已经有 2-3 篇代表性文章希望后续流程复用时，使用本技能。

## Required Questions

开始前，先问这 3 个：

1. 你能提供几篇代表你风格的文章？（至少 2 篇，最好 3-5 篇）
2. 你的目标读者是谁？他们习惯什么阅读场景？
3. 有没有你明确不想用的词或表达方式？

## Hard Gates
- 不要凭空捏造作者风格——输入必须是真实样本文章、可信的品牌文案，或明确的人设约束。
- 不要把"风格学习"做成"句式照抄"——要提炼判断方式，不止表面形式。
- 风格学习输出的是 profile，不是直接模仿后的正文。
- 不要样本少于 2 篇就开始提炼——必须先告知不稳定。
- 不要样本风格冲突太大还强行合并——必须先让用户决定缩小范围还是补样本。
- 不要只总结关键词不总结结构和判断方式。

## Workflow
1. 收集输入:
   - 历史文章 2-5 篇
   - 品牌/作者说明
   - 可选 persona
2. 提炼风格维度:
   - 语气
   - 句长
   - 开头习惯
   - 结构偏好
   - 常用词或禁用词
   - 结尾 CTA 风格
3. 形成 `style-profile`:
   - 核心风格标签
   - 保留项
   - 禁忌项
   - 适用场景
4. 交给下游:
   - `article-planning` 用于定调
   - `article-multi-mode-writing` 用于起稿
   - `article-authenticity-editing` 用于 style-preserving humanize

## Wait Points
- 如果样本不足或互相冲突，先让用户决定是缩小范围还是补样本。
- 提炼出 profile 后，先让用户确认“像不像你/这个品牌”。

## Output Contract
- 输出 `style-profile` 摘要，而不是只说“偏口语化”“偏专业”。
- 明确说明哪些风格项可继承，哪些只在特定场景使用。
- 给出是否推荐叠加 persona 的建议。

## Common Mistakes
- 把“风格学习”做成“句式照抄”。
- 只总结关键词，不总结结构和判断方式。
- 认为去 AI 化就一定要抹掉作者特色。

## Quality Self-Check

### error（阻塞）
- [ ] 没有真实样本就开始提炼风格
- [ ] 样本数量 < 2 篇但没告知用户

### warning（需要修正）
- [ ] 只总结了关键词，没有分析结构和判断方式
- [ ] 样本之间风格冲突但没标出

### info（建议改进）
- [ ] 没有建议用户是否叠加 persona
- [ ] 没有说明哪些风格项只在特定场景使用

## Reference Files
- `references/style/style-profile-schema.md`
- `references/personas/technical-writer.md`
- `references/personas/product-writer.md`
