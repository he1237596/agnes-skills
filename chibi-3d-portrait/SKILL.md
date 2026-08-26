---
name: chibi-3d-portrait
description: '当用户需要将人物照片转换为3D Q版萌化风格时使用，支持上传照片图生图或纯文字文生图两种模式，输出竖屏9:16可爱卡通形象，保留面部特征和关键细节，Pixar/Disney 3D动画风格，大眼萌化。'
---

# 人物Q版萌化技能 (3D版本)

## 触发条件
当用户需要将人物照片转换为Q版萌化风格时使用，特别是：
- 用户上传照片并要求萌化、Q版、卡通化
- 用户提到"Q版"、"萌化"、"可爱"、"chibi"、"3D可爱"、"Pixar风格"
- 用户要求将真人照片变成可爱3D卡通形象

## 执行流程

### 第一步：判断输入类型
- 如果用户上传了照片 → 使用 image_to_image
- 如果只有文字描述 → 使用 text_to_image

### 第二步：收集必要信息
**图生图**：
- 获取用户上传的图片路径
- 确认萌化程度（轻度/中度/重度Q版）
- 询问是否保留特定细节（发型、眼镜、配饰等）

**文生图**：
- 询问性别（默认女性）
- 询问发型/发色偏好
- 询问表情/姿态偏好

### 第三步：构建 Prompt

**图生图 Prompt 模板**：
```
Transform this [人物描述] into an adorable 3D chibi style character while preserving their facial features and key details. 
Big cute head with small body, super deformed proportions, large sparkling eyes, 
soft rounded features with 3D volume and depth, kawaii aesthetic, simplified but recognizable details. 
Keep their [发型/发色] and [眼镜/配饰 if any]. 
Wear [服装描述 if visible in original photo, otherwise casual cute outfit]. 
Pixar/Disney 3D animation style, soft studio lighting, subsurface scattering on skin, 
Octane render quality, clean 3D render lines. 
Expression: [happy/cute/neutral]. 
Background: [simple/gradient/blurred or remove background]. 
High quality, detailed face, 720p
```

**文生图 Prompt 模板**：
```
Adorable 3D chibi style [性别] character, super deformed big head small body, 
Pixar/Disney 3D animation style, large sparkling cute eyes, soft rounded features with 3D volume and depth, 
kawaii aesthetic, simplified but detailed face, [发型/发色描述], wearing [服装描述 or casual cute outfit], 
happy cute expression, soft pastel colors, gentle studio lighting, subsurface scattering on skin, 
clean 3D render lines, Octane render style, high quality, 720p, TikTok viral aesthetic
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
- 本地路径
- 使用的萌化风格说明（轻度/中度/重度Q版）
- 保留的细节列表

## 关键注意事项
1. **3D风格**：使用Pixar/Disney 3D动画风格，强调体积感和深度
2. **面部特征保留**：图生图时尽量保留原图人物面部特征，即使Q版也要可辨认
3. **细节保留**：询问并保留重要细节（眼镜、发型、标志性配饰）
4. **萌化程度**：根据用户要求调整Q版程度，默认中度
5. **竖屏比例**：统一使用9:16
6. **可爱风格**：大眼睛、小身体、圆润线条、柔和色彩
7. **渲染质量**：使用Octane render、subsurface scattering等专业渲染术语
8. **高清输出**：确保面部细节清晰可辨

## 示例用法
- "把我这张照片萌化成Q版"（附带照片）→ 图生图
- "生成一个Q版女生" → 文生图（默认女性）
- "把我变成可爱的3D卡通风格"（附带照片）→ 图生图
- "生成一个Q版男生" → 文生图（指定性别）
- "生成Pixar风格的Q版人物" → 文生图

## 文件路径规范
生成的图片保存在：
`<workspace>/.agnes/artifacts/images/<timestamp>-<hash>.png`
