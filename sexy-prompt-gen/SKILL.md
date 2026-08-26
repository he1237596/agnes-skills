---
name: sexy-prompt-gen
description: '抖音/快手风格性感角色生图 Prompt 生成器，根据角色+职业/主题+性感程度+风格+服饰+配饰+摄影要求，生成可直接用于生图模型的结构化 Prompt，支持写实真人、国漫3D、游戏CG等多种风格。'
metadata:
  argument-hint: 角色 + 职业/主题 + 性感程度 + 风格 + 服饰 + 配饰 + 摄影
---

# Douyin AIGC 性感角色生图 Prompt Skill

## 目标
根据用户给出的"角色 + 职业/主题 + 性感程度 + 风格 + 服饰 + 配饰 + 摄影"要求，生成结构完整、视觉统一、可直接用于生图模型的 Prompt。

## 核心方向
- 所有角色默认为成年人
- 性感主要通过服装设计、露肤比例、身材轮廓、姿态、摄影和材质表现
- 保持服装覆盖私密部位
- 避免露点、裸体、露骨性行为或色情动作
- 优先生成高级时尚、角色设计、游戏CG、国漫3D或商业摄影质感

---

## 一、输入解析

将用户输入拆成：
- 角色身份
- 年龄气质
- 人物外貌
- 身材轮廓
- 服装主体
- 露肤区域
- 腿部元素
- 胸前/腰部/腿部/脚部/头部饰品
- 鞋履
- 姿态
- 场景
- 摄影构图
- 灯光
- 材质
- 艺术风格
- 生成模型

如果用户只给出少量关键词，自动补齐缺失项，但不要喧宾夺主。

---

## 二、人物系统

### 默认参数
- adult woman
- mature feminine appearance
- elegant facial features
- refined makeup
- proportional anatomy
- long legs
- defined waistline
- graceful shoulders
- visible collarbones

### 风格选项
| 风格 | Prompt 片段 |
|------|------------|
| 写实真人 | photorealistic adult woman, realistic skin texture, natural facial details, fashion photography |
| 国漫3D | adult female character, Chinese 3D animation aesthetic, polished 3D skin shader, expressive eyes, detailed hair, premium game cinematic quality |
| 真人×国漫3D | photorealistic facial structure combined with high-end Chinese 3D animation aesthetics, realistic skin materials, stylized yet believable proportions |
| 游戏CG | AAA game character rendering, cinematic character design, physically based materials, detailed costume, dramatic lighting |

---

## 三、性感服装系统

### 上装
off-shoulder top, elegant camisole, thin shoulder straps, fitted bodice, cropped jacket, fitted blouse, lace-trimmed top, semi-sheer outer layer, tasteful cutout details, open-back design

### 下装
mini skirt, fitted mini dress, high-slit skirt, thigh-high side slit, asymmetric skirt, fitted shorts, high-waisted skirt, flowing layered skirt

### 材质
lace, chiffon, silk, satin, velvet, translucent tulle outer layer, embroidered fabric, metallic fabric, crystal embellishments

### 露肤区域（优先选择多个组合）
shoulders, collarbones, upper back, waist, midriff, arms, thighs, calves, legs

通过多个区域组合形成性感轮廓，但保持服装完整覆盖私密部位。

---

## 四、丝袜与腿部系统

### 丝袜类型
sheer black stockings, sheer white stockings, lace stockings, thigh-high stockings, over-the-knee stockings, patterned stockings, elegant fishnet stockings, satin stockings

### 附加腿部饰品
decorative thigh garter, jeweled thigh chain, delicate leg chain, ankle bracelet, jeweled anklet

### 默认优先组合
thigh-high stockings + elegant thigh accessory + long legs

如果用户明确要求吊带袜：
black thigh-high stockings with refined garter details

---

## 五、胸饰与上身配饰
jeweled brooch, crystal chest ornament, elegant pendant, layered necklace, pearl necklace, ornamental chain, jeweled collar, embroidered chest detail

避免将胸饰描述成裸露身体上的色情装饰。

---

## 六、腰饰
jeweled waist chain, ornamental belt, corset-inspired waist belt, metallic waist ornament, silk sash, decorative chain belt, embroidered waist detail

重点：defined waistline + fitted costume + elegant waist ornament

---

## 七、脚饰
delicate anklet, jeweled ankle chain, pearl anklet, ornamental foot jewelry, crystal ankle ornament

与高跟鞋组合时：
delicate jeweled anklet paired with elegant stilettos

---

## 八、头饰

### 现代风格
elegant hair clip, pearl hairpin, crystal hair ornament, jeweled headband

### 东方风格
jade hairpin, ornamental hairpin, silk hair ribbon, traditional hair ornament

### 波斯/中东幻想
jeweled forehead chain, ornamental headpiece, delicate veil, gemstone hair ornament

### 舞台风格
crystal headpiece, dramatic stage hair ornament

---

## 九、高跟鞋系统
black stilettos, pointed-toe stilettos, strappy high heels, ankle-strap heels, crystal high heels, metallic high heels, lace-up heels, elegant platform heels

### 性感但高级的默认组合
pointed-toe black stilettos + delicate ankle bracelet

---

## 十、职业角色库
female doctor, nurse, secretary, teacher, lawyer, flight attendant, news anchor, streamer, dancer, fashion model, racing model, hotel concierge, classical dancer, Persian-inspired dancer, performer, actress, fantasy princess, noblewoman, female knight

职业服装不能简单套模板，应保留职业识别度，再加入时尚化设计。

例如：
adult female doctor + fitted white medical coat + elegant fitted skirt + black thigh-high stockings + pointed stilettos

---

## 十一、波斯舞服饰融合
当用户要求波斯元素时，可组合：
Persian-inspired costume, jeweled top details, flowing chiffon fabric, ornate embroidery, gold ornamental accessories, jeweled forehead chain, layered waist jewelry, delicate anklets, flowing translucent sleeves, rich jewel-tone fabrics

建议融合方式：
modern fashion silhouette + Persian-inspired ornamentation + Chinese 3D character aesthetics

---

## 十二、国漫3D融合规则

| 主题 | Prompt 片段 |
|------|------------|
| 东方幻想 | Chinese fantasy aesthetic, elegant Eastern facial features, ornate costume design, cinematic 3D rendering |
| 现代性感女主播 | adult female streamer, stylish modern outfit, premium Chinese 3D animation, realistic skin material, studio lighting |
| 波斯×国漫3D | adult female fantasy dancer, Persian-inspired costume elements, Chinese 3D animation aesthetic, realistic skin materials, ornate jewelry |
| 职业×国漫3D | adult female professional character, fashion-forward professional uniform, Chinese 3D game cinematic aesthetic |

---

## 十三、姿态系统
standing pose, elegant contrapposto, one leg slightly forward, relaxed shoulder, graceful arm position, looking over shoulder, subtle body turn, confident runway pose, seated fashion pose, walking pose, elegant crossed-leg pose

避免过度色情化动作。

---

## 十四、构图系统
- 全身：full-body fashion portrait, head-to-toe composition
- 三分之二身：three-quarter body fashion portrait
- 半身：medium fashion portrait
- 腿部强调：full-body composition emphasizing elegant leg lines
- 腰线强调：fashion composition emphasizing waistline and silhouette

镜头角度：
eye-level, slightly low angle, three-quarter angle, side angle, over-the-shoulder

---

## 十五、灯光系统

| 场景 | 灯光描述 |
|------|---------|
| 高级时尚 | soft studio lighting, subtle rim light, cinematic highlights, controlled shadows |
| 舞台 | dramatic stage lighting, volumetric light, soft rim light |
| 国漫3D | cinematic global illumination, soft rim lighting, realistic material response |
| 波斯幻想 | warm golden lighting, ornamental highlights, atmospheric cinematic lighting |

---

## 十六、Prompt 组装顺序

最终 Prompt 按以下顺序组织：

1. [角色]
2. + [外貌]
3. + [身材轮廓]
4. + [服装]
5. + [露肤区域]
6. + [丝袜/腿部]
7. + [胸饰/腰饰/脚饰/头饰]
8. + [鞋履]
9. + [姿态]
10. + [场景]
11. + [构图]
12. + [灯光]
13. + [材质]
14. + [艺术风格]
15. + [质量]

不要机械重复同义词。

---

## 十七、质量词
highly detailed, premium character design, intricate costume details, realistic skin texture, detailed fabric texture, physically based rendering, cinematic composition, professional fashion photography, high-end 3D rendering, sharp facial details, natural proportions

---

## 十八、Negative Prompt

### 默认版本
low quality, low resolution, blurry, bad anatomy, malformed hands, extra fingers, missing fingers, deformed limbs, duplicate body parts, bad proportions, distorted face, asymmetrical eyes, plastic skin, overexposed, underexposed, excessive artifacts, text, watermark, logo, cropped head, cropped feet, duplicate character

### 防裸露追加版
nudity, exposed nipples, exposed genitals, explicit sexual content, transparent clothing revealing private areas

---

## 十九、直接生成模板示例

用户输入：护士 + 黑色吊带袜 + 高跟鞋 + 国漫3D + 性感

生成：
```
adult female nurse, mature elegant appearance, refined facial features,
long dark hair, natural makeup, graceful shoulders, visible collarbones,
defined waistline, long legs,

fashion-forward fitted white nurse-inspired uniform, short fitted skirt,
tasteful high-slit design, elegant lace trim, subtle chiffon details,
black thigh-high stockings with refined garter details,
delicate jeweled chest brooch, slim ornamental waist belt,
crystal hair ornament, delicate ankle bracelet,
pointed-toe black stilettos,

confident elegant standing pose, one leg slightly forward,
graceful posture, professional fashion editorial composition,

modern premium medical studio interior,
full-body fashion portrait, slightly low camera angle,
soft studio lighting, subtle rim light,

realistic skin texture, detailed fabric texture,
Chinese 3D animation aesthetic, photorealistic material rendering,
high-end game cinematic quality, intricate costume details,
cinematic composition, highly detailed
```

---

## 二十、随机组合规则

如果用户说"随机来一个性感国漫3D女角色"，从以下维度各抽取 1~2 项：

| 维度 | 选项 |
|------|------|
| 职业/身份 | 职业角色或幻想角色 |
| 发型 | 2种 |
| 服装 | 2~4种 |
| 材质 | 1~2种 |
| 露肤 | 2~3个区域 |
| 丝袜 | 1种 |
| 腿饰 | 0~1种 |
| 胸饰 | 1种 |
| 腰饰 | 1种 |
| 头饰 | 1种 |
| 鞋 | 1种 |
| 姿态 | 1种 |
| 场景 | 1种 |
| 灯光 | 1种 |
| 风格 | 1~2种 |

随机时保持整体审美一致，不要出现明显冲突。

---

## 二十一、用户只说"更性感"时

不要只增加 sexy，优先按以下顺序增加性感程度：

1. 增加露肩/锁骨
2. 增加露腰
3. 增加腿部露肤
4. 缩短裙长
5. 增加高开叉
6. 增加贴身剪裁
7. 增加蕾丝/薄纱层
8. 增加丝袜
9. 增加腿饰
10. 增加高跟鞋
11. 调整姿态
12. 使用更强调轮廓的时尚摄影构图

始终保持服装完整覆盖私密部位。

---

## 二十二、输出格式

当用户要求生成 Prompt 时，默认输出：

1. **角色设定** - 一句话描述角色
2. **正向 Prompt** - 可直接复制到模型
3. **Negative Prompt** - 可直接复制
4. **参数建议** - 根据用户指定模型给出建议

如果用户没有指定模型：
- Flux：优先自然语言、少堆砌权重
- SDXL：可以使用更明确的关键词结构
- ComfyUI：给出节点/工作流方向
- 不确定模型：给出通用版本

---

## 二十三、重要一致性规则

如果用户要连续生成同一个角色：

**固定**：
- 脸部特征
- 发型
- 发色
- 瞳色
- 身材比例
- 主要服装颜色
- 核心饰品

**只改变**：
- 场景
- 姿态
- 镜头
- 次要服装
- 灯光

这样可以减少角色漂移。

---

## 二十四、默认风格

当用户没有指定风格时，默认：
premium fashion editorial + Chinese 3D animation + realistic skin materials + cinematic lighting

整体目标：
性感、精致、成熟、时尚、高级，而不是单纯堆砌裸露
