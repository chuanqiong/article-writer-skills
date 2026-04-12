---
name: article-planning
description: Use when defining article requirements, checking feasibility, or choosing a topic direction before drafting
---

# Article Planning

## Overview
本技能负责 `/specify` 和 `/topic` 阶段，把模糊需求整理成 brief，做压力测试，再给出 3-4 个差异化方向，并补充热点、标题、金句、爆款风险等选题增强信息，让用户选，而不是替用户拍板。

## When to Use
用户还没有稳定 brief、想评估题目是否值得做、要选题方向、要估算时间成本或需要推荐写作模式时，使用本技能。

## Required Questions

开始前，先问这 3 个：

1. 这篇文章的核心观点是什么？你想让读者看完后记住什么？
2. 你的目标读者是谁？他们在什么场景下会读这篇文章？
3. 有没有必须包含的真实经历或数据？

## Hard Gates
- 不要跳过 workspace 规则确认就写 brief——不同 workspace 的质量目标不同。
- 不要跳过可行性预检——至少覆盖素材可得性、时间成本、质量目标、知识门槛四项。
- 不要替用户选择写作模式——只能推荐。
- 不要只给 1-2 个方向——至少 3 个差异化方向，且必须等待用户选择。
- 不要只给标题不给结构——用户没法选。
- 不要发现素材不足还给出高真实性承诺。
- 不要用标题技巧掩盖论点空洞——后面写作会无料可写。
- 热点、标题、金句、爆款检查都属于辅助判断，不能替代选题结构本身。

## Workflow
1. 读取 workspace 规则，收集 brief 需要的信息:
   - 主题
   - 读者
   - 平台
   - 字数
   - 内容类型
   - 时限
2. 做可行性预检:
   - 是否必须依赖真实经历
   - 现有素材够不够
   - 公开资料能否补足
   - 目标 AI 味是否现实
   - 时间是否匹配
3. 给出绿/黄/红结论和建议动作:
   - 绿灯 -> 可以进入选题或研究
   - 黄灯 -> 先补素材、缩范围或放宽目标
   - 红灯 -> 暂停或改题
4. 生成 3-4 个差异化方向，每个方向都给出:
   - 切入点
   - 结构
   - 所需素材
   - 优势与风险
   - 预估耗时
   - 预估 AI 味和适配模式
5. 如用户关心传播性，再补充选题增强层:
   - 热点对齐: 当前切口是否贴近热点、争议、刚需
   - 标题候选: 至少给 3 种标题策略，不只给一个标题
   - 金句候选: 给可提炼的句子方向，不提前写成整段正文
   - 爆款风险检查: 识别标题党、空泛承诺、证据不足等问题
6. 如用户已有 `style-profile` 或明确 persona，规划阶段要把它写进 brief:
   - 语气
   - 句长
   - 开头习惯
   - 结尾 CTA 风格
7. 用户选定方向后，产出 `specification.md` 所需的结构化信息。
8. 如果用户已经有固定提纲或明确要求立项报告、开题报告、技术报告，转交 `article-multi-mode-writing` 的提纲约束流程。

## Wait Points
- 可行性结论输出后，先等用户确认继续、调整或暂停。
- 选题方向输出后，先等用户选择。
- 若存在明显素材缺口，先等用户决定补素材还是改题。

## Output Contract
- 输出 brief 摘要、可行性等级、主要风险、推荐模式和下一步建议。
- 输出的方向必须可比较，而不是 3 个换皮标题。
- 如执行选题增强，输出热点判断、标题候选、金句方向和爆款风险，不把它们伪装成最终文案。
- 用户确认后，给下游技能一份清晰的 spec 结构。

## Common Mistakes
- 把选题变成写作提纲，提前透支写稿阶段。
- 只给标题，不给结构和风险，导致用户没法选。
- 发现素材不足却还给出高真实性承诺。
- 用标题技巧掩盖论点空洞，导致后面写作无料可写。

## Quality Self-Check

### error（阻塞）
- [ ] 没做可行性预检就给方向
- [ ] 只给了 1-2 个方向（至少 3 个）

### warning（需要修正）
- [ ] 方向之间只是换皮标题，切入角度雷同
- [ ] 没有评估每个方向的素材可得性

### info（建议改进）
- [ ] 没有询问用户是否关心传播性
- [ ] 没有把 style-profile 写进 brief（如果已有）

## Reference Files
- `references/workspaces/wechat.md`
- `references/workspaces/video.md`
- `references/workspaces/general.md`
- `references/planning/hot-topic-title-heuristics.md`
- `references/personas/technical-writer.md`
- `references/personas/product-writer.md`
- `references/style/style-profile-schema.md`
