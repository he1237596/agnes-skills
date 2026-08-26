---
name: douyin-aigc-sexy
description: '抖音/快手风格性感写真生成器，强调展露肌肤、突出身材曲线，支持多种风格（古风、赛博朋克、韩系、港风等）的性感化版本'
metadata:
  argument-hint: '[风格] [图片/视频]'
---

# Douyin AIGC 性感写真风格生成器（修正版）

## 核心定位
性感、妩媚、吸引眼球。无论何种服装风格，都强调展露肌肤、突出身材曲线。

## 触发条件
当用户请求生成抖音/快手风格图片或视频时触发，自动应用性感路线。

## 可用风格列表（性感化调整）

### 通用风格（性感化）
| 风格 | 性感化描述 |
|------|----------|
| `古风变装·性感` | 薄纱汉服、露背设计、高开叉裙摆、若隐若现 |
| `二次元·性感` | 动漫风格但强调曲线、露肩露背、丝袜元素 |
| `Pixar 3D·性感` | 皮克斯风格但身材火辣、曲线明显 |
| `吉卜力·性感` | 宫崎骏风格融入性感元素 |
| `赛博朋克 neon·性感` | 霓虹灯光效、发光紧身衣、露腰露腿 |
| `韩系清冷·性感` | 清冷高级感但穿着性感、露锁骨露肩 |
| `港风复古·性感` | 90年代香港女星性感风情 |
| `纯欲甜妹·性感` | 甜美中融入性感元素 |

### 性感写真风格（抖音爆款）
| 风格 | 描述 | 性感元素 |
|------|------|----------|
| `赛博发光女友` | 霓虹光效+发光紧身衣+露腰露腿 | LED发光服饰、机械舞步、未来感性感 |
| `纯欲甜妹` | 无辜大眼睛+粉嫩妆容+小吊带/露肩装 | 甜美与性感结合 |
| `韩系清冷·性感版` | 清冷高级脸+紧身包臀裙/露背装 | 白皙皮肤+曲线展示 |
| `港风复古明艳·性感` | 90年代港星+高开叉旗袍/露背礼服 | 大红唇+波浪卷发+曲线 |
| `翡翠珠韵千金·性感` | 新国风+薄纱透明感+翡翠首饰 | 若隐若现的东方性感 |
| `异域风情·性感` | 印度纱丽+露腰装+丰富首饰 | 浓郁妆容+身材展示 |
| `黑金古风·性感` | 黑红古风+露背设计+金色头饰 | 花瓣飘落+神秘性感 |
| `Old Money老钱·性感` | 极简奢华+贴身针织/丝绸 | 低调的性感 |
| `希腊神话女神·性感` | 白色丝绸薄纱+花瓣飘落 | 若隐若现的神话性感 |
| `日系胶片·性感` | 胶片感+清凉夏日装 | 清新中的性感 |
| `国风傣族·性感` | 傣族服饰+紧身短裙+露肩 | 民族风性感 |
| `西域琵琶精·性感` | 红色舞衣+露腰设计+西域风情 | 神秘冷艳性感 |

## 执行流程

### 第一步：确认风格
如果用户没有指定风格，展示上面的风格列表让用户选择。如果用户指定了风格，直接进入对应流程。

### 第二步：构建 Prompt（性感化核心）

**图片 Prompt 模板**：
```
[风格关键词], [性感主题描述], [环境/背景], [光线描述], [构图], 
sexy, alluring, curvy figure, skin-revealing, alluring pose, 
high quality, detailed, 720p, TikTok viral aesthetic
```

**性感化元素关键词库**：
- **服装**：sheer fabric（薄纱）、backless（露背）、high-slit（高开叉）、strapless（无肩带）、crop top（露脐）、tight-fitting（紧身）、see-through（透视）、off-shoulder（露肩）
- **身材**：curvy figure、slender waist、long legs、attractive pose
- **肌肤**：bare shoulders、exposed back、smooth skin、glowing skin
- **氛围**：alluring、seductive、mysterious、elegant sensual

**各风格专属性感化 Prompt 片段**：

- **古风变装·性感**: `ancient Chinese hanfu beauty, sheer silk robes, backless design, high-slit skirt, jade ornaments, cherry blossoms, soft traditional lighting, elegant yet sensual`
- **赛博发光女友**: `cyberpunk neon glow, LED light strips on tight outfit, glowing accessories, neon-lit urban background, alluring dancing pose, futuristic sexy aesthetic, 8K cinematic`
- **纯欲甜妹**: `sweet innocent girl, big expressive eyes, pink blush, soft pink lips, youthful beauty, strapless dress, exposed shoulders, gentle smile, warm soft lighting, sweet yet alluring`
- **韩系清冷·性感**: `Korean elegant beauty, clean minimal aesthetic, pale flawless skin, natural nude makeup, long sleek hair, form-fitting dress, exposed collarbones, soft diffused lighting, high fashion editorial, sexy minimalism`
- **港风复古明艳**: `1990s Hong Kong glamour style, bold red lips, voluminous wavy hair, warm film grain, high-slit qipao, backless design, golden hour lighting, nostalgic cinematic mood, sultry elegance`
- **翡翠珠韵千金**: `Chinese jade maiden, elegant new Chinese style, sheer fabric layers, jade hairpin and pearl earrings, soft garden courtyard, gentle warm lighting, refined traditional beauty, subtle sensual`
- **异域风情**: `Indian bridal style, rich silk sari, colorful gemstone jewelry, intricate henna details, warm golden lighting, bare midriff, exotic elegant atmosphere, captivating beauty`
- **黑金古风**: `black and crimson ancient Chinese dress, golden shoulder ornaments, floating petals, dramatic cinematic lighting, backless design, mysterious elegant mood, dark sensual`
- **Old Money老钱**: `quiet luxury aesthetic, neutral cream and sand tones, cashmere sweater, natural window light, form-fitting silhouette, understated elegance, timeless sophisticated portrait, subtle sexy`
- **希腊神话女神**: `Greek mythology goddess, flowing white silk robes, golden hour backlighting, cherry blossom petals, marble columns, ethereal divine glow, Botticelli inspired, translucent fabric, sensual divine beauty`
- **日系胶片少女**: `Japanese film photography style, natural outdoor setting, soft film grain, fresh natural makeup, gentle breeze, summer outfit, nostalgic summer vibe, fresh yet alluring`
- **国风傣族**: `Dai ethnic minority costume, colorful floral patterns, beaded jewelry, flower basket, tropical garden, vibrant ethnic aesthetic, form-fitting skirt, alluring traditional beauty`
- **西域琵琶精**: `red dancing costume, pipa instrument, exotic Western Regions style, dark mystical cave background, dramatic lighting, mysterious beautiful aura, seductive performance`

**视频 Prompt 模板**（含镜头运动）：
```
[风格关键词], [性感主题描述], [动作/动态], [镜头运动描述], 
sexy, alluring, viral video style, 720p
```

### 第三步：生成

**生成图片**：
- 调用 `agnes_aigc__text_to_image`，ratio 用 `9:16`（抖音竖屏）
- 画质默认 quality tier

**生成视频**：
- 调用 `agnes_aigc__text_to_video`
- width: `720`，height: `1280`（9:16 竖屏）
- num_frames: 301（10秒内，30fps）
- frame_rate: 30

**如果用户提供了参考图片**：
- 调用 `agnes_aigc__image_to_image` 或 `agnes_aigc__image_to_video`
- 保留参考图核心元素，应用性感风格化

### 第四步：输出

返回生成的图片和/或视频，并附带：
- 本地路径
- 使用的风格名称
- Prompt 简要说明

## 关键注意事项

1. **抖音竖屏优先**：ratio 统一使用 `9:16`
2. **视频不超过 10 秒**：num_frames 控制
3. **性感核心**：无论何种服装风格，强调展露肌肤、突出身材曲线
4. **Prompt 用英文**：Agnes 模型对英文 prompt 理解更好
5. **风格关键词必须嵌入 prompt**
6. **内容合规**：保持平台规范，性感但不违规
