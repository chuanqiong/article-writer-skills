# article-writer-skills

从 `article-writer` 提炼出来的 `Codex/Claude` 写作技能库，面向中文文章、公众号、自媒体和结构化文档写作。目录名与 frontmatter 用英文，技能正文用中文，方便 agent 发现，也保留原项目的方法细节。

## Included Skills

| Skill | Purpose | Source Commands |
| --- | --- | --- |
| `article-writing-workflow` | 顶层路由，识别 workspace、阶段和下一步技能 | 全流程 |
| `article-style-learning` | 作者画像、范文学习、风格档案 | 风格学习扩展 |
| `article-planning` | 需求澄清、可行性预检、选题方向 | `/specify`, `/topic` |
| `article-research-workflow` | brief 调研、文档站爬取、知识库化研究 | `/research` |
| `article-material-development` | 搜索素材、扩展经历、结构提示 | `/collect`, `/extract`, `/expand`, `/hint` |
| `article-multi-mode-writing` | 四种写作模式与提纲约束写作 | `/write`, `/outline` |
| `article-authenticity-editing` | 真实性检查与三遍审校 | `/authentic`, `/review` |
| `article-visual-publishing` | 配图、终检、格式配置与发布产物 | `/images`, `/check`, `/publish`, `/format-config` |
| `wechat-draft-publishing` | 将 HTML 推送到公众号草稿箱 | `/push-draft` |

## Recommended Order

1. `article-writing-workflow`
2. `article-style-learning` 有历史文章或明确风格要求时插入
3. `article-planning`
4. `article-research-workflow`
5. `article-material-development`
6. `article-multi-mode-writing`
7. `article-authenticity-editing`
8. `article-visual-publishing`
9. `wechat-draft-publishing` 仅在需要推送公众号草稿时使用

## Reference Assets

- `references/workspaces/`: `wechat`, `video`, `general` 三类工作区规则
- `references/anti-ai/`: 套话、AI 句式、口语化替换速查
- `references/style/`: 风格档案 schema 与风格学习输入要求
- `references/planning/`: 热点、标题、金句、爆款检查启发式
- `references/personas/`: 技术写作 / 产品视角写作 persona
- `references/outlines/`: 结构化文档提纲模板
- `references/visual/`: 主题背景、封面 prompt、信息图 prompt 预设
- `references/publishing/`: 微信 frontmatter 与推草稿检查清单

## Scope

- 基于 `article-writer` 当前已实现能力整理，并补入 skill 层可独立成立的风格学习、选题增强、视觉 prompt 能力。
- 保留方法论和关键约束，不复制源项目的 shell/TS 脚本。
- 适合在 agent 环境中作为技能库调用，不是命令模板镜像仓库。
- 不把外部项目依赖的在线格式化/发布服务设为本仓库默认依赖。
