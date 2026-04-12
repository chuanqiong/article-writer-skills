---
name: article-research-workflow
description: Use when researching a topic, crawling documentation sites, or building a knowledge base before article drafting
---

# Article Research Workflow

## Overview
本技能负责把 brief、问题或 URL 转成可写作的研究包。它覆盖常规网页调研、文档站爬取、PDF 提取和知识库整理，但不替代写稿。

## When to Use
用户需要调研资料、给了技术文档 URL、要你整理竞品/数据/事实依据，或写作前需要建立知识库时，使用本技能。

## Required Questions

开始前，先问这 3 个：

1. 你最想在这篇文章里回答的核心问题是什么？
2. 你需要哪些类型的数据或案例？（数字、对比、用户反馈、行业报告...）
3. 这些信息需要多新？（只要最新的 / 近半年 / 不限）

## Hard Gates
- 不要跳过输入类型判断——先识别是 brief、文档站、PDF 还是常规搜索。
- 不要把文档站退化成几个关键词搜索——优先走结构化采集。
- 不要省略来源和日期——高时效或高风险信息必须保留。
- 不要在研究阶段写出整段结论——只整理事实，不做写作。
- 不要把社区观点标注为"事实"——社区观点只作补充。

## Workflow
1. 识别模式:
   - brief 驱动调研
   - 文档站爬取
   - PDF 提取
   - 常规网页搜索
2. 设定范围:
   - 核心问题
   - 需要的数据或案例
   - 时效要求
   - 是否要建立知识库
3. 执行采集:
   - 官方文档优先
   - 对比资料补充二级来源
   - 社区观点只作补充，不代替事实
4. 产出研究包:
   - 关键事实
   - 来源链接或出处
   - 可引用数据
   - 未解决问题
   - 可复用知识库路径
5. 把研究结果交给 `article-planning`、`article-material-development` 或 `article-multi-mode-writing`。

## Wait Points
- brief 含糊且研究方向会明显影响范围时，先确认重点。
- 来源冲突且会改变结论时，先把冲突点摊开。
- 如果用户要求“只查最新”，先确认时间窗口。

## Output Contract
- 产出研究摘要，而不是正文草稿。
- 每条关键事实都尽量带来源或出处说明。
- 明确指出哪些结论可靠，哪些仍待补证。

## Common Mistakes
- 拿社区观点当事实。
- 明明是文档站，却只做几个关键词搜索。
- 研究阶段直接写出整段结论，导致来源和判断混在一起。

## Quality Self-Check

### error（阻塞）
- [ ] 研究包中有关键事实没有来源
- [ ] 把社区观点标注为"事实"

### warning（需要修正）
- [ ] 来源冲突但没有标注出来
- [ ] 明明是文档站却只做了零散搜索

### info（建议改进）
- [ ] 没有按"可靠 / 待补证 / 不可靠"分级
- [ ] 没有标注哪些结论仍需更多证据

## Reference Files
- `references/workspaces/wechat.md`
- `references/workspaces/video.md`
- `references/workspaces/general.md`
