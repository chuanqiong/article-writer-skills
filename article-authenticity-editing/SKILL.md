---
name: article-authenticity-editing
description: Use when checking authenticity, lowering AI tone, or running content style detail review passes on article drafts
---

# Article Authenticity Editing

## Overview
本技能负责 `/authentic` 和 `/review`。先看文章像不像真的人写的，再按 `content -> style -> detail` 三遍处理，逐步降 AI 味，而不是一把梭综合润色。这里还负责控制 humanize 强度，并在存在 `style-profile` 时优先保住作者风格。

## When to Use
已经有 `draft.md`，用户要做真实性检查、降 AI 味、三遍审校、精修发稿前版本时，使用本技能。

## Required Questions

开始前，先问这 3 个：

1. 这篇文章的目标 AI 味是多少？（< 30% / < 20% / 越低越好）
2. 有没有已经学好的 style-profile？（如果有，优先保住作者风格）
3. 你更在意哪个方面？（事实准确性 / 自然程度 / 整体精修）

## Hard Gates
- 不要跳过真实性判断就直接改文。
- 不要改变三遍顺序——固定为 `content -> style -> detail`。
- 不要只说”更自然一点”——style pass 必须结合本仓库的 anti-AI references。
- 不要在事实、结构或引用有硬伤时跳到 style pass——先修事实。
- humanize 必须有强度档位: `gentle`, `medium`, `aggressive`——不要默认 medium 不告知用户。
- 不要把作者习惯误判成噪音——有 `style-profile` 时，先保风格特征，再删 AI 痕迹。
- 不要用更多套话替换旧套话——看起来更”润”但更假。
- 不要只改词不改空洞内容。

## Workflow
1. `/authentic`
   - 按 5 维检查:
     - 温度
     - 个性
     - 地域或场景具体性
     - 真实细节
     - 思想深度
   - 标出最空洞、最像 AI 的段落
2. `/review content`
   - 检查事实、逻辑、结构、覆盖度、引用
   - 确认 spec 中的重要点没有漏
3. `/review style`
   - 删除套话
   - 拆常见 AI 句式
   - 把空泛书面语改成更自然、更具体的表达
   - 优先引入真实动作、时间、场景、判断
   - 按强度档位执行:
     - `gentle`: 轻量清理套话，不动作者节奏
     - `medium`: 清理套话并重写高风险句式
     - `aggressive`: 对空洞段落做大幅重构，但要说明改动范围
   - 如果有 `style-profile`，先比对是否保留了作者常用开头、句长、判断方式和 CTA 风格
4. `/review detail`
   - 标点
   - 节奏
   - 段落长度
   - 标题层级
   - 版式和细小错漏
5. 汇总修改结果和剩余风险。

## Wait Points
- `/authentic` 报告出来后，如果问题很大，先等用户决定是否重写关键段落。
- content pass 如果发现事实硬伤，先修事实再做 style。
- 大幅改写前，先让用户知道修改会改变哪些段落。

## Output Contract
- 给出真实性判断、主要风险段落和建议动作。
- 给出三遍审校的处理顺序和每一遍的重点修改点。
- 明确说明是否已达到目标 AI 味区间，还是只是从高风险降到了中风险。
- style pass 输出必须带:
  - 使用的强度档位
  - 是否参考了 `style-profile`
  - 改动风险说明
  - 简短质量评分

## Common Mistakes
- 只改词，不改空洞内容。
- style pass 先于事实修正。
- 用更多套话替换旧套话，看起来更“润”但更假。
- 为了去 AI 痕迹，把作者原本有辨识度的表达也一起洗掉。

## Quality Self-Check

### error（阻塞）
- [ ] 有事实硬伤但没修就开始 style pass
- [ ] 用 aggressive 档位但没有告知用户改动范围

### warning（需要修正）
- [ ] 有 style-profile 但审校时没比对
- [ ] 同一句式模式连续出现超过阈值

### info（建议改进）
- [ ] 没有给出质量评分（1-10 分 × 5 维度）
- [ ] 没有说明当前 AI 味是"已达标"还是"从高降到中"

## Reference Files
- `references/anti-ai/boilerplate.md`
- `references/anti-ai/ai-patterns.md`
- `references/anti-ai/colloquial-replacements.md`
- `references/style/style-profile-schema.md`
