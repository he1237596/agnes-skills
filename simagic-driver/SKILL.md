---
name: simagic-driver
description: '将用户上传的人物照片转换为酷飒赛车手风格，保留面部特征，身着印有SIMAGIC标识的赛车服，可添加运动品牌logo和KEEP RACING红色标识，手拿头盔'
---

# SIMAGIC 赛车手风格生成技能

## 触发条件
当用户需要生成赛车手风格图片时使用，特别是：
- 图生图：将用户上传的人物照片转换为赛车手风格
- 文生图：直接生成赛车手形象

## 执行流程

### 第一步：确认需求
- 如果用户上传了照片，使用 image_to_image 生成
- 如果没有照片，使用 text_to_image 生成

### 第二步：构建 Prompt

**图生图 Prompt 模板**：
```
Transform this [人物描述] into a cool and fierce racing driver while preserving their facial features. 
They wear a professional racing suit with SIMAGIC brand logo prominently displayed on the chest. 
Add sport brand logos on the sleeves and sides. 
Include "KEEP RACING" text in bold red color on the suit. 
They [hold a racing helmet / pose confidently]. 
Their hair is [style description]. 
Background shows a racing track or pit lane with dynamic motorsport atmosphere. 
Dramatic lighting, high contrast, professional motorsport photography style, 
sharp focus on face, cinematic quality, 720p
```

**文生图 Prompt 模板**：
```
Cool and fierce [性别] racing driver, wearing professional racing suit with SIMAGIC brand logo 
prominently on chest, sport brand logos on sleeves and sides, bold red "KEEP RACING" text on suit, 
holding racing helmet confidently, [发型/妆容描述], determined cool expression, 
sharp facial features, background shows racing track or pit lane with dynamic motorsport atmosphere, 
dramatic cinematic lighting, high contrast, professional motorsport photography style, 
sharp focus on face, 720p, TikTok viral aesthetic
```

### 第三步：生成图片
- 图生图：调用 `agnes_aigc__image_to_image`
  - reference_image: 用户上传的图片路径
  - ratio: "9:16"（抖音竖屏）
  - 保留用户提供的original_prompt和enhanced_prompt
  
- 文生图：调用 `agnes_aigc__text_to_image`
  - ratio: "9:16"
  - 使用enhanced_prompt

### 第四步：输出结果
返回生成的图片，并附带：
- 本地路径（从 structured_content 的 local_path 获取）
- 使用的风格说明
- 生成的关键元素列表

## 关键注意事项
1. **面部特征保留**：图生图时尽量保留原图人物面部特征
2. **SIMAGIC标识**：必须醒目显示在赛车服上
3. **KEEP RACING文字**：红色醒目字体
4. **竖屏比例**：统一使用9:16
5. **职业风格**：专业赛车手形象，赛道背景
6. **手拿头盔**：增加赛车手专业感

## 示例用法
- "帮我生成一个赛车手图片" → 文生图
- "把我这张照片变成赛车手"（附带照片）→ 图生图
- "生成SIMAGIC赛车手形象" → 文生图

## 文件路径规范
生成的图片保存在：
`<workspace>/.agnes/artifacts/images/<timestamp>-<hash>.png`
