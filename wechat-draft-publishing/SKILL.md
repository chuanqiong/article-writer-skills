---
name: wechat-draft-publishing
description: Use when pushing a formatted HTML article into a WeChat public account draft with frontmatter and credential validation
---

# WeChat Draft Publishing

## Overview
本技能用于把已经格式化好的微信 HTML 推送到公众号草稿箱。它负责检查 frontmatter、微信凭证、IP 白名单、封面图和图片上传条件，然后再创建草稿。

## When to Use
已经拿到 `publish/wechat.html`，并且用户明确要推送到公众号草稿箱，而不是只做本地预览时，使用本技能。

## Hard Gates
- 输入必须是 `.html` 文件，不是 markdown。
- HTML 头部必须带微信 frontmatter。
- 必须先确认 `WECHAT_APP_ID` 和 `WECHAT_APP_SECRET`，或 `.content/config.json` 里的微信配置存在。
- 服务器 IP 未进白名单、摘要缺失、封面图缺失、图片不可读时，必须阻塞。

## Workflow
1. 检查输入文件是否为 `publish/wechat.html` 或同类 HTML。
2. 读取并验证 frontmatter:
   - `title`
   - `author`
   - `digest`
   - `cover`
3. 检查微信配置、白名单和草稿箱容量。
4. 上传图片:
   - 本地图片 -> 上传
   - 在线图片 -> 下载后上传
   - 已是 `mmbiz.qpic.cn` -> 跳过
5. 创建草稿并返回 `media_id`、标题、图片数量等结果。

## Wait Points
- 如果凭证或白名单不满足，先停下，让用户补配置。
- 如果 frontmatter 缺字段，先停下，让用户补齐 HTML。
- 如果图片失败，先停下，让用户修路径、大小或格式。

## Output Contract
- 成功时输出标题、字数、图片上传数量和 `media_id`。
- 失败时输出明确阻塞原因和解决动作，不做模糊描述。
- 推送前后都提醒用户去后台复核草稿。

## Common Mistakes
- 把 markdown 直接拿去推草稿。
- 忘记写 `digest` 或 `cover`。
- 只检查本地预览，不检查微信凭证和 IP 白名单。

## Reference Files
- `references/publishing/wechat-frontmatter.md`
- `references/publishing/wechat-publish-checklist.md`
