# WeChat Draft Checklist

1. 检查微信配置
   - `WECHAT_APP_ID`
   - `WECHAT_APP_SECRET`
   - 或 `.content/config.json` 中的微信配置
   - 白名单 IP 已配置
2. 检查输入文件
   - 必须是 `.html`
   - 顶部有 frontmatter
   - 至少包含 `title`, `author`, `digest`, `cover`
3. 检查图片
   - 封面路径可读
   - 格式为 `jpg/png`
   - 超过 2MB 先压缩
4. 运行推送
   - 上传图片
   - 创建草稿
   - 记录 `media_id`
5. 处理失败
   - `invalid credential` -> 重新核对凭证
   - `invalid ip` -> 补白名单
   - 缺少摘要或封面 -> 回补 frontmatter
   - 图片失败 -> 修正路径、格式、大小
   - 草稿箱满 -> 先删旧稿
6. 安全
   - 不把 `appSecret` 提交进仓库
   - 推送前先本地预览 HTML
