---
name: article-writing-workflow
description: Use when routing an article-writing request across stages or workspaces before choosing a deeper skill
---

# Article Writing Workflow

## Overview
本技能是顶层路由器。先判断当前请求属于哪个 workspace，再判断用户处在准备、收集、写作、审校还是发布阶段，然后把任务分发给对应技能，而不是直接写稿。

## When to Use
当用户刚开始描述写作需求、问“下一步做什么”、中途切换目标，或你不确定应该调用哪个 article skill 时，先运行本技能。

## Hard Gates
- 若存在 `.content/config.json`，必须先读取 `workspace` 字段；不要猜 workspace。
- 必须先判断阶段，再决定下一技能；不要因为用户一句“帮我写”就跳过 brief、选题、素材或审校。
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

## Reference Files
- `references/workspaces/wechat.md`
- `references/workspaces/video.md`
- `references/workspaces/general.md`
- `README.md`
