---
name: article-writing-workflow
description: Use when routing an article-writing request across stages or workspaces before choosing a deeper skill
---

# Article Writing Workflow

## Overview
本技能是顶层路由器。先判断当前请求属于哪个 workspace，再判断用户处在准备、收集、写作、审校还是发布阶段，然后把任务分发给对应技能，而不是直接写稿。

## When to Use
当用户刚开始描述写作需求、问“下一步做什么”、中途切换目标，或你不确定应该调用哪个 article skill 时，先运行本技能。

## Required Questions

收到写作相关请求后，先问这 3 个：

1. 这篇文章要发在哪个平台？（公众号 / 视频号 / 博客 / 知乎 / 其他）
2. 你现在处于哪个阶段？（还没想好写什么 / 已有方向但缺资料 / 已有资料要开始写 / 已有初稿要改 / 已改好要发）
3. 有没有参考文章或风格要求？（给链接或文件）

## Hard Gates
- 不要猜测 workspace——必须从 `.content/config.json` 读取 `workspace` 字段。
- 不要因为用户一句”帮我写”就跳过 brief、选题、素材或审校。
- 不要把 `/write` 当流程入口——它是准备完成后的阶段。
- 不要在 `wechat` 下跳过配图约束，不要在 `video` 下生成公众号格式。
- 不要把”润色”直接当润色处理——先判断是否应进入真实性检查或三遍审校。
- 不要把”学我的风格”直接当 planning 处理——先调用 `article-style-learning`。
- 所有强制等待点都要保留：可行性结论、选题方向、写作模式、提纲解析、重大审校修改，都不能自动越过。

## Workflow
1. 读取 workspace:
   - `wechat` -> 参考 `references/workspaces/wechat.md`
   - `video` -> 参考 `references/workspaces/video.md`
   - `general` -> 参考 `references/workspaces/general.md`
2. 判断阶段:
   - 没有 brief 或需求还散乱 -> `article-planning`
   - 有历史文章、作者样本或明确要学风格 -> `article-style-learning`
   - 有 brief/spec，但缺资料或来源 -> `article-research-workflow`
   - 有 brief/spec，但缺真实素材 -> `article-material-development`
   - 进入正式写稿或提纲约束写作 -> `article-multi-mode-writing`
   - 已有 draft，需要真实性检查或三遍审校 -> `article-authenticity-editing`
   - 已到配图、终检、发布产物生成 -> `article-visual-publishing`
   - 已有 `publish/wechat.html`，且用户要推公众号草稿 -> `wechat-draft-publishing`
3. 给下一技能传递必要上下文:
   - workspace
   - brief/spec 路径或关键信息
   - 是否已有 `style-profile`
   - 当前目标平台
   - 是否要求真实经历
   - 时间预算和质量目标
4. 在每次阶段切换时，重新确认是否缺失上游产物，例如 `brief.md`、`specification.md`、`materials-found.md`、`draft.md`、`checklist.md`。

## Wait Points
- 可行性评级出来后，等用户确认继续、调整或暂停。
- 选题方向给出后，等用户明确选择。
- 写作模式菜单给出后，等用户明确选择。
- 提纲解析结果给出后，等用户确认结构正确。

## Output Contract
- 明确给出当前 workspace、当前阶段、下一技能和原因。
- 概括必须遵守的硬规则，例如段落长度、Hook、配图数量、AI 味目标。
- 传递给下游技能的上下文必须足够，不要只丢一句“继续”。

## Common Mistakes
- 把 `/write` 当成流程入口，而不是准备完成后的阶段。
- 在 `wechat` 下忘记配图和发布约束，在 `video` 下错误生成公众号格式。
- 用户只说“润色一下”就直接改文，没先判断是否应该进入真实性检查或三遍审校。
- 用户明明要“学我的风格”，却直接进入 planning 或 writing，导致风格要求丢失。

## Quality Self-Check

### error（阻塞）
- [ ] 没读 workspace 就开始分发
- [ ] 跳过了用户确认直接进入下一阶段

### warning（需要修正）
- [ ] 传递给下游的上下文不足，只有一句"继续"
- [ ] 用户中途切换目标，但没有重新判断阶段

### info（建议改进）
- [ ] 没有概括当前阶段需要遵守的硬规则（段落长度、配图数量等）

## Reference Files
- `references/workspaces/wechat.md`
- `references/workspaces/video.md`
- `references/workspaces/general.md`
- `README.md`
