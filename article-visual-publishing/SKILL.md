---
name: article-visual-publishing
description: Use when preparing illustrations, running final checks, or generating workspace-specific publish outputs for articles
---

# Article Visual Publishing

## Overview
本技能覆盖 `/images`、`/check`、`/publish` 和 `/format-config`。目标是让不同 workspace 的配图、终检、格式和发布产物都落在正确路径里，不跨区、不猜测。同时在发布前补齐主题、背景、封面 prompt、信息图 prompt 这类视觉决策。

## When to Use
草稿已经基本成型，接下来要补图、做发布前检查、生成微信 HTML、视频脚本成品或通用发布稿时，使用本技能。

## Hard Gates
- `/publish` 前必须读取 `.content/config.json` 的 `workspace`；不要猜平台。
- `wechat` 需要配图时，先完成 `/images` 再发布。
- `video` 不跑静态配图流程，改用 Hook 和分镜说明。
- 终检结果如果还有阻塞项，不能把状态说成“可发布”。
- `newspic` 目前只做规划分支，不应假装已具备真实发布能力。

## Workflow
1. `/images`
   - `wechat`: 规划并落地 5-8 张图，插回稿件并记录来源
   - `video`: 跳过静态配图，检查 Hook、镜头和字幕重点
   - `general`: 先确认是否需要图，再决定数量和类型
   - 如用户需要更强视觉一致性，再补:
     - 主题选择
     - 背景类型
     - 封面 prompt
     - 信息图 prompt
2. `/check`
   - 检查内容完整性、真实性、编辑视角、AI 味、版权、链接、图片或 Hook 缺口
   - 生成 `checklist.md` 或等价结论
3. `/publish`
   - `wechat` -> `publish/wechat.html`, `publish/wechat.md`, `metadata.json`
   - `video` -> `publish/video-script.md`
   - `general` -> `publish/article.md`
4. `/format-config`
   - 只在需要调整微信展示样式时介入
   - 修改的是 `formatting` 配置，不是文章正文逻辑
5. 可选的视觉规划分支:
   - `theme-selection`: 从品牌感、技术感、专业感、轻内容感中选主题
   - `background-selection`: 选择纯色、渐变、网格、杂志感、数据卡片感背景
   - `cover-prompt`: 输出封面图 prompt，不直接假装已生成封面
   - `infographic-prompt`: 输出信息图 prompt，适合对比、流程、框架总结
   - `newspic-planning`: 如果用户想做小绿书/图文卡片，只规划素材结构与图卡节奏，不承诺自动发布

## Wait Points
- 如果 `general` 的配图或 SEO 需求不明确，先问用户。
- 如果终检发现硬阻塞项，先等用户决定修还是停。
- 如果用户要求切换输出平台，先重新确认 workspace。

## Output Contract
- 说明当前 workspace、输出文件路径和是否还有阻塞项。
- 明确说明是“已可发布”还是“仍需补图/补数据/补检查”。
- 对微信发布链路，提示是否需要继续调用 `wechat-draft-publishing`。
- 如果执行了视觉规划，输出所选主题、背景、封面 prompt、信息图 prompt，以及它们服务的是哪个平台。

## Common Mistakes
- 在 `wechat` 下跳过配图直接发布。
- 在 `video` 下错误生成 `wechat.html`。
- 把样式配置问题和内容问题混在一起处理。
- 把“封面 prompt”误说成“已经生成封面成品”。

## Reference Files
- `references/workspaces/wechat.md`
- `references/workspaces/video.md`
- `references/workspaces/general.md`
- `references/visual/theme-background-catalog.md`
- `references/visual/cover-prompt-presets.md`
- `references/visual/infographic-prompt-presets.md`
- `references/publishing/wechat-frontmatter.md`
- `references/publishing/wechat-publish-checklist.md`
