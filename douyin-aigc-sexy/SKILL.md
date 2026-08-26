---
name: douyin-aigc-sexy
description: '抖音/快手风格性感写真生成器，支持多种主流AIGC风格（古风、赛博朋克、韩系、港风等），融合史诗仙侠与现代都市白领元素，写实真人摄影，网红级哑光肤质，18-30岁年轻女性，苗条黄金比例身材，必须全身构图含丝袜腿链脚链。'
metadata:
  argument-hint: '[风格选项] + [角色/职业] + [服装/配饰要求] 或 直接描述'
---

# Douyin AIGC 风格写真生成器（终极融合版）

## 核心定位
抖音/快手风格性感写真生成器，支持多种主流AIGC风格（古风、赛博朋克、韩系、港风等）的性感化版本。
结合史诗仙侠氛围与现代都市白领元素，强调展露肌肤、突出身材曲线。

## 触发条件
当用户请求生成抖音/快手风格图片或视频时触发，自动应用性感路线。

## 默认参数
- **肤质**：网红级精致面容，细腻光滑（not oily, not greasy），哑光至半哑光质感
- **年龄**：18-30岁年轻女性
- **身材**：苗条/黄金比例（slim, golden ratio figure），curvy figure
- **风格**：写实真人摄影（realistic photography style）
- **无过度磨皮**：保留自然皮肤质感
- **抖音竖屏**：9:16 比例
- **构图**：全身（full-body），必须包含完整腿部和鞋履

## 身材控制参数
- **允许**：slim, curvy, golden ratio, plump（丰腴/微微胖）
- **禁止**：overweight, obese, fat

---

## 一、风格列表

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
| `史诗仙侠·性感` | 奔放仙侠+短裙高开叉+都市白领融合 | 写实真人+黄金比例+自由行动 |

### 都市白领融合风格
| 风格 | 描述 | 性感元素 |
|------|------|----------|
| `职场精英·性感` | 职业装+短裙/开叉+高跟鞋 | 干练中透着性感 |
| `内衣模特·性感` | 内衣/睡衣+都市背景 | 私密感+职业感融合 |
| `仙侠白领·融合` | 仙侠元素+现代办公场景 | 古风仙气+都市白领 |

---

## 二、Prompt 构建系统

### 肤质控制（重要）
- **禁止**：oily, greasy, shiny, wet skin, sweat
- **使用**：matte finish, satin finish, natural skin texture, flawless porcelain skin, smooth complexion, refined skin texture

### 基础 Prompt 模板（必须全身）
```
[风格关键词], [主题描述], [环境/背景], [光线描述], [构图],
sexy, alluring, curvy figure, skin-revealing, alluring pose,
no over-smoothing, natural skin texture, matte finish,
full-body composition, complete legs, visible shoes, head-to-toe,
high quality, detailed, 720p, TikTok viral aesthetic
```

### 写实真人 + 网红肤质 Prompt 模板（必须全身）
```
18-30 years old young beautiful Chinese woman,
realistic photography style,
网红级精致面容,
flawless porcelain skin, smooth complexion,
matte finish, natural skin texture, no oily skin,
beautiful delicate facial features, large expressive eyes,
small nose, pouty lips, youthful radiant skin,
[风格关键词], [性感主题描述], [环境/背景], [光线描述],
slim slender figure, 黄金比例身材, curvy figure,
sexy, alluring, skin-revealing, alluring pose,
full-body composition, complete legs, visible shoes, head-to-toe,
high quality, detailed, 720p, TikTok viral aesthetic
```

### 仙侠+都市白领融合 Prompt 模板（必须全身）
```
18-30 years old young beautiful Chinese woman,
realistic photography style,
网红级精致面容,
flawless porcelain skin, smooth complexion,
matte finish, natural skin texture, no oily skin,
epic xianxia atmosphere, unrestrained fantasy aesthetic,
short hemline, high-slit design, thigh-length outfit,
free movement, no fabric restriction,
modern urban白领 elements, corporate fashion,
slim slender figure, 黄金比例身材, curvy figure,
sexy, alluring, skin-revealing,
full-body composition, complete legs, visible shoes, head-to-toe,
high quality, 720p, viral TikTok aesthetic
```

---

## 三、性感化元素关键词库

### 身材
slim, curvy, golden ratio, long legs, slender waist, attractive pose, plump figure（丰腴）

### 服装
sheer fabric（薄纱）、backless（露背）、high-slit（高开叉）、strapless（无肩带）、crop top（露脐）、short hemline（短款）、thigh-length（大腿长度）、tight-fitting（紧身）、see-through（透视）、off-shoulder（露肩）、business attire（职业装）、lingerie model（内衣模特）

### 肌肤
bare shoulders（露肩）、exposed back（露背）、smooth skin（光滑肌肤）、matte finish（哑光质感）、flawless porcelain skin（完美瓷肌）、natural skin texture（自然肤质）

### 氛围
alluring、seductive、mysterious、elegant sensual、epic fantasy（史诗幻想）

### 仙侠元素
xianxia、immortal、floating clouds、ethereal、flowing ribbons

### 都市白领
urban professional、corporate fashion、modern workplace、business chic

### 丝袜/腿部元素（必须完整展示）
- **丝袜**：sheer black stockings, sheer white stockings, lace stockings, thigh-high stockings, over-the-knee stockings, patterned stockings, elegant fishnet stockings, satin stockings
- **腿饰**：decorative thigh garter, jeweled thigh chain, delicate leg chain, ankle bracelet, jeweled anklet
- **脚链**：delicate anklet, jeweled ankle chain, pearl anklet, ornamental foot jewelry, crystal ankle ornament

### 鞋履（必须完整展示）
pointed-toe stilettos, black heels, crystal high heels, strappy high heels, ankle-strap heels, platform heels, lace-up heels

---

## 四、各风格专属 Prompt 片段

- **古风变装·性感**: `ancient Chinese hanfu beauty, sheer silk robes, backless design, high-slit skirt, jade ornaments, cherry blossoms, soft traditional lighting, elegant yet sensual, slim curvy figure, sheer black stockings, delicate ankle bracelet, elegant shoes, full-body composition, complete legs`
- **赛博发光女友**: `cyberpunk neon glow, LED light strips on tight outfit, glowing accessories, neon-lit urban background, alluring dancing pose, futuristic sexy aesthetic, 8K cinematic, slim curvy figure, fishnet stockings, thigh chain, platform heels, full-body composition, complete legs`
- **纯欲甜妹**: `sweet innocent girl, big expressive eyes, pink blush, soft pink lips, youthful beauty, strapless dress, exposed shoulders, gentle smile, warm soft lighting, sweet yet alluring, slim figure, lace stockings, delicate leg chain, cute heels, full-body composition, complete legs`
- **韩系清冷·性感**: `Korean elegant beauty, clean minimal aesthetic, pale flawless skin, natural nude makeup, long sleek hair, form-fitting dress, exposed collarbones, soft diffused lighting, high fashion editorial, sexy minimalism, slim figure, sheer stockings, ankle bracelet, minimalist heels, full-body composition, complete legs`
- **港风复古明艳**: `1990s Hong Kong glamour style, bold red lips, voluminous wavy hair, warm film grain, high-slit qipao, backless design, golden hour lighting, nostalgic cinematic mood, sultry elegance, slim curvy figure, sheer black stockings, jeweled anklet, vintage heels, full-body composition, complete legs`
- **翡翠珠韵千金**: `Chinese jade maiden, elegant new Chinese style, sheer fabric layers, jade hairpin and pearl earrings, soft garden courtyard, gentle warm lighting, refined traditional beauty, subtle sensual, slim figure, lace stockings, delicate leg chain, elegant shoes, full-body composition, complete legs`
- **异域风情**: `Indian bridal style, rich silk sari, colorful gemstone jewelry, intricate henna details, warm golden lighting, bare midriff, exotic elegant atmosphere, captivating beauty, slim curvy figure, patterned stockings, ankle bracelet, traditional sandals, full-body composition, complete legs`
- **黑金古风**: `black and crimson ancient Chinese dress, golden shoulder ornaments, floating petals, dramatic cinematic lighting, backless design, mysterious elegant mood, dark sensual, slim figure, sheer black stockings, thigh garter, platform heels, full-body composition, complete legs`
- **Old Money老钱**: `quiet luxury aesthetic, neutral cream and sand tones, cashmere sweater, natural window light, form-fitting silhouette, understated elegance, timeless sophisticated portrait, subtle sexy, slim figure, sheer nude stockings, delicate ankle chain, elegant pumps, full-body composition, complete legs`
- **希腊神话女神**: `Greek mythology goddess, flowing white silk robes, golden hour backlighting, cherry blossom petals, marble columns, ethereal divine glow, Botticelli inspired, translucent fabric, sensual divine beauty, slim curvy figure, sheer white stockings, crystal ankle ornament, sandals, full-body composition, complete legs`
- **日系胶片少女**: `Japanese film photography style, natural outdoor setting, soft film grain, fresh natural makeup, gentle breeze, summer outfit, nostalgic summer vibe, fresh yet alluring, slim figure, lace trim stockings, delicate leg chain, casual shoes, full-body composition, complete legs`
- **国风傣族**: `Dai ethnic minority costume, colorful floral patterns, beaded jewelry, flower basket, tropical garden, vibrant ethnic aesthetic, form-fitting skirt, alluring traditional beauty, slim figure, patterned stockings, ankle bracelet, traditional shoes, full-body composition, complete legs`
- **西域琵琶精**: `red dancing costume, pipa instrument, exotic Western Regions style, dark mystical cave background, dramatic lighting, mysterious beautiful aura, seductive performance, slim curvy figure, sheer black stockings, jeweled ankle chain, dance shoes, full-body composition, complete legs`
- **史诗仙侠·性感**: `epic xianxia immortal beauty, unrestrained fantasy aesthetic, sheer silk short dress, high-slit thigh-length skirt, flowing ribbons, floating clouds, natural skin texture, matte finish, dramatic cinematic lighting, alluring pose, slim golden ratio figure, sensual yet powerful, thigh-high stockings, delicate leg chain, elegant heels, full-body composition, complete legs`
- **职场精英·性感**: `urban professional beauty, modern corporate fashion, short business skirt, high-slit design, exposed collarbones, natural skin texture, matte finish, confident alluring pose, office lighting, sexy career woman, slim figure, sheer black stockings, thigh garter, pointed-toe stilettos, full-body composition, complete legs`
- **内衣模特·性感**: `lingerie model aesthetic, modern corporate background, intimate apparel, sheer fabric, natural skin texture, matte finish, alluring pose, professional lighting, sexy yet sophisticated, slim curvy figure, lace stockings, thigh chain, high heels, full-body composition, complete legs`
- **仙侠白领·融合**: `xianxia immortal in modern workplace, ethereal short dress, high-slit design, natural skin texture, matte finish, floating clouds meets office building, alluring pose, fantasy meets reality, sexy corporate fairy, slim figure, sheer stockings, delicate anklet, elegant heels, full-body composition, complete legs`

---

## 五、视频 Prompt 模板
```
[风格关键词], [性感主题描述], [动作/动态], [镜头运动描述],
sexy, alluring, viral video style, 720p
```

---

## 六、执行流程

### 第一步：确认风格
如果用户没有指定风格，展示上面的风格列表让用户选择。如果用户指定了风格，直接进入对应流程。

### 第二步：构建 Prompt
根据选定的风格和用户描述，生成详细的英文 prompt。
**重要：必须包含**
- `full-body composition, complete legs, visible shoes, head-to-toe`
- 丝袜/腿链/脚链元素

### 第三步：生成

**生成图片**：
- 调用 `agnes_aigc__text_to_image`，ratio 用 `9:16`（抖音竖屏）
- 画质默认 quality tier
- **必须使用 full-body composition，不能裁剪头部或脚部**

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

---

## 七、关键注意事项

1. **抖音竖屏优先**：ratio 统一使用 `9:16`
2. **视频不超过 10 秒**：num_frames 控制
3. **写实真人风格**：必须使用 `realistic photography style`，非3D动漫
4. **肤质控制**：必须使用 `matte finish` 或 `satin finish`，**禁止** `oily, greasy, shiny, wet skin`
5. **网红级肤质**：必须包含 `flawless porcelain skin, smooth complexion, natural skin texture`
6. **年龄控制**：18-30岁年轻女性
7. **身材控制**：苗条/黄金比例（slim, golden ratio），禁止 overweight/obese/fat
8. **性感核心**：强调展露肌肤、突出身材曲线
9. **全身构图要求**：必须包含 `full-body composition, complete legs, visible shoes, head-to-toe`，禁止裁剪头部或脚部
10. **丝袜/腿链/脚链**：必须完整展示腿部丝袜和饰品
11. **Prompt 用英文**：Agnes 模型对英文 prompt 理解更好
12. **内容合规**：保持平台规范，性感但不违规
13. **无过度磨皮**：始终保留自然皮肤质感
