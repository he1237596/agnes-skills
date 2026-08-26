---
name: simagic-driver-3d
description: '当用户需要生成3D Q版萌化的SIMAGIC赛车手风格图片时使用，支持上传照片图生图或纯文字文生图两种模式，输出竖屏9:16可爱卡通赛车手形象，保留面部特征（图生图）或生成全新角色（文生图），赛车服上醒目展示SIMAGIC标识和KEEP RACING红色字样，Pixar/Disney 3D动画风格。'
---

# SIMAGIC 赛车手风格生成技能 (3D Q版版本)

## 触发条件
当用户需要生成3D Q版萌化的SIMAGIC赛车手风格图片时使用，特别是：
- 用户上传照片并要求转换成Q版赛车手风格
- 用户要求直接生成3D Q版赛车手形象
- 用户提到"Q版赛车手"、"3D萌化赛车手"、"SIMAGIC"、"KEEP RACING"等关键词

## 执行流程

### 第一步：判断输入类型
- 如果用户上传了照片（有reference_image）→ 使用 image_to_image
- 如果只有文字描述 → 使用 text_to_image

### 第二步：收集必要信息
**图生图**：
- 获取用户上传的图片路径
- 询问或从对话中获取人物描述（发型、性别等）
- 询问是否有特殊要求

**文生图**：
- 询问或推断性别（默认女性）
- 询问发型/发色偏好（可选）
- 询问表情/姿态偏好（可选）

### 第三步：构建 Prompt

**图生图 Prompt 模板**：
```
Transform this [人物描述] into an adorable 3D chibi style racing driver while preserving their facial features. 
Big cute head with small body, super deformed proportions, large sparkling cute eyes, 
soft rounded features with 3D volume and depth, Pixar/Disney 3D animation style. 
They wear a professional racing suit with SIMAGIC brand logo prominently displayed on the chest. 
Add sport brand logos on the sleeves and sides. 
Include "KEEP RACING" text in bold red color on the suit. 
They [hold a mini racing helmet / pose confidently]. 
Keep their [发型/发色]. 
Kawaii aesthetic, simplified but recognizable details. 
Soft studio lighting, subsurface scattering on skin, Octane render quality, clean 3D render lines. 
Expression: happy cute. 
Background: [simple/gradient/blurred or racing track background]. 
High quality, detailed face, 720p
```

**文生图 Prompt 模板**：
```
Adorable 3D chibi style [性别] racing driver character, super deformed big head small body, 
Pixar/Disney 3D animation style, large sparkling cute eyes, soft rounded features with 3D volume and depth, 
kawaii aesthetic, simplified but detailed face, [发型/发色描述] with 3D rendering, 
wearing professional racing suit with SIMAGIC brand logo prominently on chest, 
sport brand logos on sleeves and sides, bold red "KEEP RACING" text on suit, 
holding mini racing helmet confidently, happy cute expression, 
soft pastel colors with racing theme accents, gentle studio lighting, 
subsurface scattering on skin, clean 3D render lines, Octane render style, 
high quality, 720p, TikTok viral aesthetic
```

### 第四步：生成图片
- 统一使用 ratio: "9:16"（抖音竖屏比例）
- 图生图：调用 `agnes_aigc__image_to_image`
  - reference_image: 用户上传的图片路径
  - original_prompt: 用户原始请求
  - enhanced_prompt: 构建的英文详细prompt
  
- 文生图：调用 `agnes_aigc__text_to_image`
  - original_prompt: 用户原始请求
  - enhanced_prompt: 构建的英文详细prompt

### 第五步：输出结果
返回生成的图片，并附带：
- 本地路径（从 structured_content 的 local_path 获取）
- 使用的风格说明（3D Q版萌化 + 赛车手风格）
- 生成的关键元素列表（SIMAGIC标识、KEEP RACING、赛车服、头盔等）

## 关键注意事项
1. **3D Q版风格**：使用Pixar/Disney 3D动画风格，强调体积感和深度，大眼睛、小身体
2. **面部特征保留**：图生图时尽量保留原图人物面部特征，即使Q版也要可辨认
3. **SIMAGIC标识**：必须醒目显示在赛车服胸部位置
4. **KEEP RACING文字**：红色醒目字体
5. **竖屏比例**：统一使用9:16
6. **职业风格**：专业赛车手形象，迷你头盔增加萌感
7. **渲染质量**：使用Octane render、subsurface scattering等专业渲染术语
8. **可爱风格**：大眼睛、小身体、圆润线条、柔和色彩

## 示例用法
- "把我这张照片萌化成Q版赛车手"（附带照片）→ 图生图
- "生成一个Q版赛车手" → 文生图（默认女性）
- "生成SIMAGIC 3D Q版赛车手形象" → 文生图
- "生成一个男性Q版赛车手" → 文生图（指定性别）

## 文件路径规范
生成的图片保存在：
`<workspace>/.agnes/artifacts/images/<timestamp>-<hash>.png`
