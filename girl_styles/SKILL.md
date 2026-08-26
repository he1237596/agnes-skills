---
name: douyin-aigc-styles-v2
description: '当用户请求生成抖音/快手风格的图片或视频时使用，支持古风变装、二次元化、Pixar 3D、吉卜力、赛博朋克等多种抖音主流 AIGC 风格，以及赛博发光女友、纯欲甜妹、韩系清冷、港风复古、翡翠千金、异域风情等美女写真风格，输出 720p 竖屏内容，视频控制在 10 秒以内。触发词包括：生成图片、生成视频、抖音风格、AIGC、AI绘画、AI变装、美女写真等。'
metadata:
  argument-hint: '[风格名称, e.g. "赛博发光" or "纯欲甜妹" or leave empty for menu]'
---

# Douyin AIGC 风格生成器（含美女写真）

## 触发条件

当用户请求生成抖音/快手风格图片或视频时触发。支持多种抖音主流风格，输出 720p 左右画质，视频控制在 10 秒以内。

## 可用风格列表

### 通用风格
| 风格 | 描述 |
|------|------|
| `古风变装` | 素人照片转古装美人，工笔画/汉服/国风元素 |
| `二次元化` | 真人照片转动漫/二次元风格，Cel-shading |
| `AI变身` | 真人脸变二次元少女/少年，反差感强 |
| `Pixar 3D` | 皮克斯风格 3D 渲染，大眼睛、Subsurface scattering |
| `吉卜力动画` | 宫崎骏风格，手绘 2D，水彩纹理，柔和调色板 |
| `拍立得复古` | 复古 Flash 胶片感，颗粒质感，暖色调 |
| `赛博朋克 neon` | 霓虹夜景，发光感，赛博朋克氛围 |
| `粘土动画` | 黏土材质 Stop-Motion 感，可爱柔和 |
| `超写实电影` | 电影级光效，浅景深，真实感 |
| `Lo-Fi 治愈` | 温暖色调，安静场景，loop 感 |

### 美女写真风格（抖音爆款）
| 风格 | 描述 | 适用场景 |
|------|------|----------|
| `赛博发光女友` | 霓虹光效+发光服饰+机械舞步，赛博朋克美女 | 热舞视频、潮流穿搭、夜店风 |
| `纯欲甜妹` | 无辜大眼睛、粉嫩腮红、甜美少女感 | 日常穿搭、自拍风格、甜美系 |
| `韩系清冷` | 清冷高级脸、白皙皮肤、自然裸妆、柔顺长发 | 极简风、ins风、气质写真 |
| `港风复古明艳` | 90年代香港女星气质、大红唇、波浪卷发、胶片质感 | 复古风、优雅写真 |
| `翡翠珠韵千金` | 中式温婉闺秀、翡翠首饰、新国风、低调雅致 | 国风写真、东方美学 |
| `异域风情` | 印度/中东风格、华丽纱丽、彩色宝石、浓郁妆容 | 旅拍风、民族风写真 |
| `黑金古风` | 黑红配色古风礼服、金色头饰、花瓣飘落、电影感 | 国风大片、古装写真 |
| `Old Money老钱` | 极简奢华、中性色调、自然光影、高级质感 | 职场风、时尚写真 |
| `希腊神话女神` | 神话感、白色丝绸、花瓣飘落、金色光晕 | 梦幻风、艺术写真 |
| `日系胶片少女` | 胶片颗粒、清新自然、日系妆容、户外场景 | 清新写真、生活记录 |
| `国风傣族` | 傣族服饰、彩色流苏、花篮、异域国风 | 民族风、国风变装 |
| `西域琵琶精` | 红色舞衣、琵琶道具、西域风情、神秘冷艳 | 国风玄幻、角色写真 |

## 执行流程

### 第一步：确认风格

如果用户没有指定风格，展示上面的风格列表让用户选择。如果用户指定了风格（中文或英文均可），直接进入对应流程。

**中文映射规则**：
- 古风 / 国风 → `古风变装` / `黑金古风` / `国风傣族` / `西域琵琶精`
- 二次元 / 动漫 → `二次元化`
- AI 变身 / 变脸 → `AI变身`
- 皮克斯 / 3D 卡通 → `Pixar 3D`
- 吉卜力 / 宫崎骏 → `吉卜力动画`
- 拍立得 / 复古 / 胶片 → `拍立得复古` / `日系胶片少女`
- 赛博朋克 / neon / 霓虹 / 发光 → `赛博朋克 neon` / `赛博发光女友`
- 粘土 / 黏土 → `粘土动画`
- 超写实 / 电影感 → `超写实电影`
- Lo-Fi / 治愈 → `Lo-Fi 治愈`
- 纯欲 / 甜妹 / 可爱 → `纯欲甜妹`
- 韩系 / 韩式 → `韩系清冷`
- 港风 / 复古港味 → `港风复古明艳`
- 翡翠 / 千金 / 闺秀 → `翡翠珠韵千金`
- 异域 / 印度 / 中东 → `异域风情`
- 黑金 → `黑金古风`
- Old Money / 老钱 → `Old Money老钱`
- 希腊 / 神话 / 女神 → `希腊神话女神`
- 傣族 → `国风傣族`
- 琵琶精 / 西游女妖 → `西域琵琶精`

### 第二步：构建 Prompt

根据选定的风格和用户描述，生成详细的英文 prompt。

**图片 Prompt 模板**：
```
[风格关键词], [主题描述], [环境/背景], [光线描述], [构图], [情绪氛围], 
high quality, detailed, 720p, TikTok viral aesthetic
```

**视频 Prompt 模板**（含镜头运动）：
```
[风格关键词], [主题描述], [动作/动态], [镜头运动描述], 
[光线描述], [氛围], soft motion, viral video style, 720p
```

**各风格专属 Prompt 片段**：

- **古风变装**: `ancient Chinese hanfu beauty, traditional elegance, flowing silk robes, hair ornaments, cherry blossoms, soft traditional lighting`
- **赛博发光女友**: `cyberpunk neon glow, LED light strips on outfit, glowing accessories, neon-lit urban background, dancing pose, futuristic aesthetic, 8K cinematic`
- **纯欲甜妹**: `sweet innocent girl, big expressive eyes, pink blush on cheeks, soft pink lips, youthful beauty, light natural makeup, gentle smile, warm soft lighting`
- **韩系清冷**: `Korean elegant beauty, clean minimal aesthetic, pale flawless skin, natural nude makeup, long sleek hair, soft diffused lighting, minimalist background, high fashion editorial`
- **港风复古明艳**: `1990s Hong Kong glamour style, bold red lips, voluminous wavy hair, warm film grain, soft vintage filter, golden hour lighting, nostalgic cinematic mood`
- **翡翠珠韵千金**: `Chinese jade maiden, elegant new Chinese style, jade hairpin and pearl earrings, soft garden courtyard background, gentle warm lighting, refined traditional beauty`
- **异域风情**: `Indian bridal style, rich silk sari, colorful gemstone jewelry, intricate henna details, warm golden lighting, exotic elegant atmosphere`
- **黑金古风**: `black and crimson ancient Chinese dress, golden shoulder ornaments, floating petals, dramatic cinematic lighting, mysterious elegant mood`
- **Old Money老钱**: `quiet luxury aesthetic, neutral cream and sand tones, cashmere sweater, natural window light, understated elegance, timeless sophisticated portrait`
- **希腊神话女神**: `Greek mythology goddess, flowing white silk robes, golden hour backlighting, cherry blossom petals, marble columns, ethereal divine glow, Botticelli inspired`
- **日系胶片少女**: `Japanese film photography style, natural outdoor setting, soft film grain, fresh natural makeup, gentle breeze, nostalgic summer vibe`
- **国风傣族**: `Dai ethnic minority costume, colorful floral patterns, beaded jewelry, flower basket, tropical garden, vibrant ethnic aesthetic`
- **西域琵琶精**: `red dancing costume, pipa instrument, exotic Western Regions style, dark mystical cave background, dramatic lighting, mysterious beautiful aura`

### 第三步：生成

**生成图片**：
- 调用 `agnes_aigc__text_to_image`，ratio 用 `9:16`（抖音竖屏）
- 画质默认 quality tier，不强制指定 size

**生成视频**：
- 调用 `agnes_aigc__text_to_video`
- width: `720`，height: `1280`（9:16 竖屏）
- num_frames: 根据帧率控制，10 秒内（如 30fps 用 301 帧，满足 8n+1）
- frame_rate: 30
- 视频必须 10 秒以内

**如果用户提供了参考图片（图生图/图生视频）**：
- 调用 `agnes_aigc__image_to_image` 或 `agnes_aigc__image_to_video`
- 保留参考图核心元素，只修改风格

### 第四步：输出

返回生成的图片和/或视频，并附带：
- 本地路径（从 structured_content 的 `local_path` 获取）
- 使用的风格名称
- Prompt 简要说明

## 关键注意事项

1. **抖音竖屏优先**：ratio 统一使用 `9:16`
2. **视频不超过 10 秒**：num_frames 控制，30fps 最多 301 帧（8×37+1=301）
3. **画质与速度平衡**：不强制指定 size，使用默认 quality tier 保证速度
4. **Prompt 用英文**：Agnes 模型对英文 prompt 理解更好
5. **风格关键词必须嵌入 prompt**：如 "Studio Ghibli style"、"Pixar 3D render" 等
6. **禁止使用真实人物肖像**：用户如果提供真人照片，只做风格迁移，不保留可识别身份
7. **内容合规**：生成内容需符合平台规范，避免过度暴露或不当暗示
