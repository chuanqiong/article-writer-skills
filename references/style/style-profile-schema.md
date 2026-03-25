# Style Profile Schema

建议把风格档案整理成下面这些维度，供 planning、writing、editing 复用。

## Core Fields

- `source_count`: 样本篇数
- `tone`: 语气，如冷静、锐利、朋友感、产品经理感、技术评测感
- `sentence_length`: 短句 / 中句 / 长短交替
- `opening_style`: 开头偏好，如问题开场、场景开场、结论先行、数据先行
- `structure_preference`: 结构偏好，如列表、对比、故事、问题-解决
- `vocabulary_preferences`: 常用词、术语风格、口语程度
- `avoid_terms`: 应避免的词、腔调、口头禅或公文句
- `evidence_style`: 更爱用数据、案例、亲历、类比，还是混合
- `cta_style`: 结尾 CTA 风格，如温和建议、强判断、开放问题
- `persona_hint`: 技术写作者 / 产品视角 / 创始人视角 / 个人体验型

## Reusable Output

建议下游技能至少读取这 5 项:
- `tone`
- `sentence_length`
- `opening_style`
- `avoid_terms`
- `cta_style`

## Failure Signals

- 样本主题差异太大，导致 profile 混乱
- 样本明显是多人代笔，无法稳定归纳
- 样本数量少于 2 篇，只能做临时 profile
