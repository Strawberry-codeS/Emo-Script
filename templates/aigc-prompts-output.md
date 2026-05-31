# AIGC提示词输出模板

> 本模板定义从「制作圣经」到「可直接输入AIGC工具」的提示词格式。
> 适配工具：Midjourney / Kling / Sora / Runway / ComfyUI

---

## 提示词层级结构

```
全局风格基底（必须，每次都加）
    +
角色一致性描述（有人物时加）
    +
场景道具描述（环境/物件单独出图时用）
    +
单镜头提示词（分镜头逐一对应）
    +
负面提示词（全程排除的风格）
```

---

## 全局风格基底模板

**英文版（Midjourney/Sora/Runway）：**
```
cinematic short film still, [时长]-second narrative film aesthetic,
color palette: [主色调] dominant with isolated [点缀色调] accents,
film grain subtle, anamorphic lens, shallow depth of field,
lighting: motivated practical sources only, no fill light,
atmosphere: [氛围关键词],
production design: [空间设定],
mood reference: [参考影片] + [情感参考],
aspect ratio [比例], --ar [比例] --style raw --q 2
```

**中文版（Kling/即梦/可灵）：**
```
电影短片画面感，[比例]，
色调：[主色调] + [点缀色调]，
胶片颗粒感轻微，变形镜头，浅景深，
打光：仅自然动机光源，无补光，
氛围：[氛围关键词]，
场景：[空间设定]，
风格参考：[参考影片]，
避免：[排除内容]
```

---

## 角色提示词模板

```
[年龄]岁[国籍][性别]，
外貌特征：[头发/面容/眼神]，
关键气质词：[3个情绪关键词]，
服装：[材质/颜色/年代感]，
手部特征：[动作习惯]，
当下状态：[这个镜头里的情绪位置]，
避免：[不要的表演风格]
```

---

## 单镜头提示词模板

```
镜头 XX｜时间区间

景别：[极近景/近景/中景/全景/俯拍/仰拍]

英文提示词：
[描述主体] [核心动作/状态] [环境设定]
[光线描述] [色温说明] [情绪词]
[特殊视觉效果] [景深设置]
[角色参考：add character reference]

打光：[色温] + [光源位置] + [光质描述]

氛围：[这一帧对观众意味着什么]

AIGC制作注意：
· [重点1]
· [重点2]
· [难点/需要多出几版的地方]
```

---

## 负面提示词通用模板

**英文：**
```
--no neon lights, lens flare, holographic blue,
generic sci-fi aesthetics, clean corporate future,
[根据故事调整],
cartoon style, anime, illustration,
flat lighting, even lighting, studio lighting,
over-saturated colors, HDR processing
```

**中文：**
```
排除：霓虹灯，镜头眩光，全息蓝光，
通用科幻美学，[根据故事调整]，
卡通风格，动漫风格，插画风格，
均匀打光，棚拍感，过饱和色彩
```

---

## 出图优先级建议模板

```
第一优先级（定风格·定角色）：
1. 主空间全景    → 确认整体视觉调性
2. 核心道具特写  → 确认物件美术质感
3. 主角角色参考  → 锁定人物一致性

第二优先级（定核心镜头）：
4. 情感破防镜头  → 最难，最重要，多出几版
5. 视觉语言首次出现的镜头 → 比如AI颜色渗透的第一次
6. 人物表演最核心的镜头

第三优先级（补全其余）：
7+. 按分镜头顺序逐一出图
```

---

## AIGC工具选择建议

| 用途 | 推荐工具 |
|------|---------|
| 静帧参考图 | Midjourney（质量最稳定）|
| 视频生成 | Kling / Runway（中文场景友好）|
| 特效合成 | ComfyUI（色温变化/投影叠加）|
| 最终剪辑 | CapCut / Premiere |
| 音乐生成 | Suno / Udio |

