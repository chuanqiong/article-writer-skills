---
name: article-material-development
description: Use when collecting, expanding, or structuring real materials for article writing without fabricating details
---

# Article Material Development

## Overview
本技能负责 `/collect`、`/extract`、`/expand`、`/hint`。核心原则是先找真实素材，再扩展真实经历，只给结构和问题，不代写细节。

## When to Use
用户需要搜索个人素材、扩展一条经历、快速补细节、写到一半卡住表达，或准备进入写稿前想确认素材够不够时，使用本技能。

## Hard Gates
- `/collect` 只搜索现有素材，不造素材。
- `/extract` 和 `/expand` 只能通过提问帮助用户回忆，不输出可直接粘贴的成文段落。
- `/hint` 只给结构，不给示例正文。
- 素材如果无法支撑目标，必须说清楚缺口。

## Workflow
1. `/collect`:
   - 从 spec 或用户问题提取关键词
   - 先查 `materials/indexed/`
   - 再查 `materials/raw/` 和 `archive/`
   - 产出相关度分层和 A/B/C/D 素材等级
2. `/extract`:
   - 选一条真实素材
   - 追问时间、地点、人物、动作、结果、感受
   - 让用户自己写完整经历
3. `/expand`:
   - 针对一句话素材做轻量扩展
   - 只问 2-4 个最关键问题
   - 适合快速补洞，不代替深挖
4. `/hint`:
   - 提供对比法、数据化、故事化、问题-解决等表达框架
   - 标出“这里需要你填真实细节”的位置
5. 交付时说明哪些素材可直接用，哪些还需补细节或重新验证。

## Wait Points
- 素材等级和缺口说明出来后，等用户决定继续、补素材还是改题。
- `/extract` 和 `/expand` 提问后，等用户自己写完再继续。
- `/hint` 给出结构后，等用户选择或填充。

## Output Contract
- `/collect` 输出应包含来源、相关度、素材等级、缺失点和下一步建议。
- `/extract` 和 `/expand` 输出应包含问题清单和真实性检查点。
- `/hint` 输出应包含结构骨架和待填占位，而不是正文。

## Common Mistakes
- 用“合理脑补”填细节，这会直接破坏真实性。
- 搜到素材后不做分层，导致用户无法判断够不够。
- 把 `/hint` 变成代写。

## Reference Files
- `article-authenticity-editing`
