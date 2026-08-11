---
name: chinese-motion-photo-poster
description: Transform casual portraits, travel photos, and outdoor snapshots into horizontal contemporary Chinese poetic photo posters with physically motivated slow-shutter foliage or light motion, preserved identity, and fine expressive handwritten Chinese copy. Use when the user asks for a Chinese-style poster, dreamy motion photo, poetic travel image, reference-matched handwritten typography, horizontal editorial cover, or iterative text-weight/size adjustments.
---

# 中文诗意慢门海报

把普通照片提炼成一张横版、摄影写实、带中国气质的诗意海报。核心不是套滤镜，而是保留一个清晰的人物或主体，将环境压缩为具有方向性的树影、叶片、花卉、光线或水面拖影，再用细线手写中文建立海报层级。

## 执行原则

- 默认使用内置 `image_gen` 编辑路径，不使用 CLI，除非用户明确要求。
- 编辑前先用 `view_image` 检查目标图；若有风格参考，也先检查参考图。
- 目标图和风格参考分工明确：目标图负责人物、场景和语义；参考图只负责视觉语言，不复制人物、界面、水印或原文案。
- 每轮只改变用户要求的变量。用户说“文字太粗”时只修文字，不重新设计照片。
- 不模仿具体在世艺术家或创作者；从参考图提取可迁移的构图、色彩、慢门、手写和留白原则。

## 适用构图

默认输出 16:9 横版单张海报，不做手机截图、不加入社交平台 UI、不做上下拼图，除非用户明确要求对照图。

1. 确定语义核心：保留一个主体、一个关键动作或物件，以及不超过两个环境线索。
2. 保留身份敏感细节：脸部比例、眼镜、发型、年龄、肤色、表情、服装、身体比例和关键标志/文字。
3. 根据主体位置放置文案：主体在左侧时优先使用右侧树影或天空留白；主体在右侧时优先使用左侧暗部或水面留白。文案不得遮挡脸、手、服装标志或场景中的关键石刻/招牌。
4. 让主体占约 25–45% 画面。留白要有环境纹理，不要替换成静止的纯色渐变。
5. 保留三层动感：近景大面积掠影、中景叶片/枝条/花卉拖影、远景光线或色块流动。模糊必须有慢门、风、移动或镜头扩散等物理原因。

## 中国风视觉方向

- 采用当代、克制、书卷气的中国视觉，而不是旅游纪念品式符号。
- 可用墨绿、竹青、黛蓝、灰青、米白、暖金等自然色；红色只作为极小的印章或线条点缀，除非用户另有要求。
- 保留摄影写实、自然光向、真实透视和细颗粒；不要把照片变成完整水墨画。
- 不添加龙、凤、灯笼、古装、扇子、假山、祥云、仙鹤、随机花朵、霓虹或玄幻粒子。
- 夜景优先保留蓝黑/墨绿暗部和局部暖光；日景优先压低过饱和绿，保留树叶的青绿与蜂蜜色阳光。

## 文案与字体

### 文案选择

- 优先沿用用户给出的文案。没有文案时，根据画面中的真实元素写 1–2 行短句，不添加抽象宏大叙事。
- 文字要短，适合海报阅读。可采用“主句 / 回应句”结构，例如：
  - `树影落在夏日` / `风从石上经过`
  - `夏夜未眠` / `在莲影与微光之间`
- 必须在提示词中逐字写出需要渲染的中文，要求准确、可读、无额外文字。

### 默认字形

- 使用细而有力的中文手写笔：细到中等可变笔画、自然压力变化、飞白、干笔边缘、长笔锋和略带不规则的书写节奏。
- 保持大字号和海报存在感，但不要使用厚重填充、粗黑块面、规整电脑字体或过度装饰的书法。
- 主句通常比回应句大 1.2–1.5 倍；两行之间留出空气，避免挤成一团。
- 文字默认用暖白或柔白；只加很轻的局部暗化、细阴影或低强度衬底提升对比，不使用金属金、强发光或厚描边。
- 文字可占约 20–35% 画面宽度，具体服从主体和留白。目标是“明显但不压过人物”。

### 用户指定文字要求（硬约束）

- 用户提供了字体参考图时，以参考图的笔画粗细为准：保持细、轻、带飞白和压力变化的手写线条，不因“更明显”而改成粗重填充字。
- “文字更大/更明显”优先通过放大文字块、增加行间距、提高暖白亮度和局部对比实现，不通过加粗笔画实现。
- “文字太粗”时降低笔画重量并保留整体字号；“文字太细”时先增加字号和对比，再只做小幅笔压调整；“字体风格不变”时禁止更换成另一种书法或电脑字体。
- 参考图控制笔触语言，用户的明确字号、位置、颜色、文案和可读性要求控制最终版式；两者冲突时保留参考图的细线风格，并用尺寸和对比解决可读性。
- 不擅自改写、增删或补充中文文案；若生成器写错字或增加文字，必须重试文字编辑。

## 工具提示词结构

使用 `image_gen` 时按以下顺序组织提示词：

1. `Image 1 is the edit target`; 明确其他图片只是 style reference。
2. 先写不可改变的身份、主体、关键物件和场景关系。
3. 指定 16:9 横版、主体位置、文案区域和三层慢门动势。
4. 指定光线、颜色、胶片颗粒、柔焦和运动的物理原因。
5. 写出准确文案、细线手写字形、字重、大小、颜色和避让区域。
6. 用负面约束锁定：无 UI、无水印、无额外文字、无新人物、无脸部漂移、无均匀高斯模糊、无过度中国符号。

可复用的核心编辑段落：

```text
Edit only the requested visual variables and preserve the source identity aggressively. Keep the face, glasses, hairstyle, age, skin tone, expression, clothing, body proportions, key object, and scene perspective unchanged. Create a single horizontal 16:9 photographic poster. Preserve one sharp semantic hero and build believable foreground sweep, midground foliage or object drag, and background light/color flow. Use contemporary Chinese editorial restraint: natural jade/ink-green, muted blue, warm cream light, fine film grain, and subtle optical diffusion. Keep motion physically motivated by wind, slow shutter, shallow depth, or lens diffusion; never blur the whole frame uniformly.
```

文案段落：

```text
Render the exact Chinese copy “主句” and “副句” in a thin expressive Chinese handwritten brush-pen style: slender variable strokes, dry-brush texture, airy spacing, natural long sweeping tails, occasional pressure variation, warm white ink, clearly legible but not heavy or blocky. Make the text large enough to read as poster typography, place it in the open low-detail area away from the face, hands, clothing labels, and key scene inscriptions. Add only a restrained local contrast support; no thick glow, metallic gold, seal, underline, extra words, UI, watermark, or text mutation.
```

## 迭代规则

先生成一版，再检查：人物身份、文案逐字准确、横版比例、文字占比、字重、可读性和背景动势。

- “文字太细/不明显”：只编辑文字；增加字号约 30–45%，提高暖白亮度和局部对比，保留细线笔触；可加极轻暗化衬底。
- “文字太粗”：只编辑文字；降低笔画重量约 40–50%，打开字内留白，改用细线、飞白和长笔锋；不缩小整体字号。
- “文字太小”：只编辑文字；增加整体文字块比例和行间距，保持字体风格不变。
- “文字太规整”：改成更松弛的手写排列和自然长线条，但不改文案。
- “照片被改坏”：下一轮明确 `Change only typography; keep every non-text pixel unchanged.`，并重新强调脸、手、服装和场景文字保真。

每次迭代都要再次用 `view_image` 检查结果。若图像生成器改写了中文、增加了额外文字或改变了人物，不交付该版本，继续使用只改文字的提示词重试。

## 交付检查

- 输出为单张 16:9 横版摄影图。
- 主体脸部和关键服装细节可辨认，背景动感有方向且不均匀糊化。
- 文案只有用户要求的文字，字形细、清晰、有手写节奏，大小足够形成海报层级。
- 中国风来自色彩、留白、题字和克制的材质，不依靠俗套装饰。
- 交付最终工作区路径，并用 Markdown 图片链接展示成片。
