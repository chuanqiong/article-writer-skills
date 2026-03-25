---
name: article-research-workflow
description: Use when researching a topic, crawling documentation sites, or building a knowledge base before article drafting
---

# Article Research Workflow

## Overview
本技能负责把 brief、问题或 URL 转成可写作的研究包。它覆盖常规网页调研、文档站爬取、PDF 提取和知识库整理，但不替代写稿。

## When to Use
用户需要调研资料、给了技术文档 URL、要你整理竞品/数据/事实依据，或写作前需要建立知识库时，使用本技能。

## Hard Gates
- 先判断输入类型: brief、项目编号、普通 URL、文档站 URL、PDF。
- 文档站或官方文档优先走结构化采集，不要退化成零散搜索。
- 高时效或高风险信息必须保留来源和日期。
- 研究输出和正文输出分开，研究阶段不要偷跑成文。

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

## Reference Files
- `references/workspaces/wechat.md`
- `references/workspaces/video.md`
- `references/workspaces/general.md`
