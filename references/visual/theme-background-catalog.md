# Theme And Background Catalog (Nano Banana Pro)

## Theme Options

| Theme | Prompt Keywords | 适用场景 |
|-------|-----------------|----------|
| `clean-tech` | clean tech editorial, minimal color palette, studio lighting | 技术评测、工具介绍 |
| `magazine-opinion` | magazine editorial aesthetic, paper texture, dramatic shadows | 观点专栏、深度分析 |
| `data-report` | modern infographic style, card-based sections, muted teal accents | 数据报告、对比总结 |
| `creator-story` | cinematic, warm tones, shallow depth of field, film grain | 个人经历、经验复盘 |
| `product-brief` | product mockup aesthetic, softbox lighting, neutral background | 方案介绍、教程说明 |

## Background Options (Prompt Keywords)

| Background | Prompt Keywords | 适用场景 |
|------------|-----------------|----------|
| 纯色 | solid [color] background, clean minimal | 严肃内容、强调主体 |
| 渐变 | gradient background from [color1] to [color2], smooth transition | 科技感、趋势感 |
| 网格/坐标 | grid pattern background, subtle coordinate lines, technical aesthetic | 数据方法论、技术框架 |
| 纸张/杂志纹理 | paper texture background, magazine print feel | 专栏观点、故事叙述 |
| 卡片分区 | card-based layout, section dividers, clean whitespace | 多要点总结、小绿书规划 |

## Camera & Lighting Keywords

### Lighting
| 类型 | Prompt Keywords | 效果 |
|------|-----------------|------|
| Studio | studio lighting, softbox, even illumination | 干净专业 |
| Dramatic | dramatic side lighting, high contrast, chiaroscuro | 戏剧张力 |
| Golden Hour | golden hour backlighting, warm glow, soft shadows | 温暖情绪 |
| Backlit | backlit, rim lighting, silhouette | 轮廓感 |
| Neon | neon lighting, cyberpunk aesthetic, vibrant glow | 科技未来感 |

### Camera
| 类型 | Prompt Keywords | 效果 |
|------|-----------------|------|
| Low Angle | low angle shot, heroic perspective | 强气势 |
| Aerial | aerial view, top-down perspective, bird's eye | 全局概览 |
| Close-up | close-up shot, macro lens, shallow depth of field f/1.8 | 细节聚焦 |
| Wide | wide-angle lens, environmental context | 场景感 |
| Portrait | portrait orientation, centered subject, blurred background | 人物聚焦 |

### Texture & Material
| 类型 | Prompt Keywords | 适用 |
|------|-----------------|------|
| Film | film grain texture, analog feel, subtle noise | 复古情绪 |
| Smooth | smooth texture, clean finish, high polish | 现代科技 |
| Paper | paper texture, matte finish, print feel | 杂志感 |
| Glass | glass material, translucent, reflection | 产品展示 |

## Selection Rules

1. **技术评测** → `clean-tech` + 纯色/网格背景 + studio lighting
2. **个人经验** → `creator-story` + 渐变/纸张纹理 + golden hour
3. **结构化报告** → `product-brief` + 卡片分区 + softbox lighting
4. **数据对比** → `data-report` + 网格背景 + dramatic side lighting
5. **观点专栏** → `magazine-opinion` + 纸张纹理 + dramatic shadows

## Output Format

主题/背景 prompt 应包含:
- **Theme keyword**: 从 Theme Options 选择
- **Background keyword**: 从 Background Options 选择
- **Lighting**: 从 Lighting Keywords 选择
- **Camera** (可选): 从 Camera Keywords 选择
- **Texture** (可选): 从 Texture Keywords 选择

示例:
```
Theme: clean-tech
Background: solid white background, clean minimal
Lighting: studio lighting, softbox
Camera: close-up shot, shallow depth of field
```
