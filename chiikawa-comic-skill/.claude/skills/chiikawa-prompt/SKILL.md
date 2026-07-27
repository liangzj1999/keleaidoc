---
name: chiikawa-prompt
description: 将中文分镜脚本翻译成英文文生图提示词（气泡文字保留中文）
user_invocable: true
---

# Chiikawa 生图提示词生成器

将中文分镜脚本翻译成英文文生图提示词，用于 AI 绘图工具（Midjourney、Stable Diffusion 等）。

## 核心原则

1. **气泡文字用中文**：有对白的分镜，提示词中要包含 `speech bubble with text: "[中文台词]"`
2. **画面描述用英文**：场景、动作、表情等描述翻译成英文
3. **画面比例**：统一使用 3:4 比例
4. **画风一致**：所有提示词都必须包含 `style of Nagano (Chiikawa)`

## 输出格式

请严格按照以下格式输出，每个提示词用代码块包裹：

**[Cover Image Prompt]**

```text
[Subject: 封面内容的英文描述], style of Nagano (Chiikawa), high impact, emotive close-up, poster design, soft pastel colors, simple background, kawaii aesthetic, aspect ratio 3:4
```

**[Comic Strip A Prompt]**

```text
style of Nagano (Chiikawa)
4-panel comic strip, 2x2 grid layout, divided into 4 distinct frames, manga page structure
Panel 1: [Panel 1画面英文描述], speech bubble with text: "[中文对白]"
Panel 2: [Panel 2画面英文描述],
Panel 3: [Panel 3画面英文描述], speech bubble with text: "[中文对白]"
Panel 4: [Panel 4画面英文描述],
soft pastel colors, simple clean lines, kawaii aesthetic, aspect ratio 3:4
```

**[Comic Strip B Prompt]**

```text
style of Nagano (Chiikawa)
4-panel comic strip, 2x2 grid layout, divided into 4 distinct frames, manga page structure
Panel 1: [Panel 1画面英文描述], speech bubble with text: "[中文对白]"
Panel 2: [Panel 2画面英文描述],
Panel 3: [Panel 3画面英文描述],
Panel 4: [Panel 4画面英文描述], speech bubble with text: "[中文对白]"
soft pastel colors, simple clean lines, kawaii aesthetic, aspect ratio 3:4
```

**[Comic Strip C Prompt]**

```text
style of Nagano (Chiikawa)
4-panel comic strip, 2x2 grid layout, divided into 4 distinct frames, manga page structure
Panel 1: [Panel 1画面英文描述],
Panel 2: [Panel 2画面英文描述], speech bubble with text: "[中文对白]"
Panel 3: [Panel 3画面英文描述], speech bubble with text: "[中文对白]"
Panel 4: [Panel 4画面英文描述],
soft pastel colors, simple clean lines, kawaii aesthetic, aspect ratio 3:4
```

**[Comic Strip D Prompt]**

```text
style of Nagano (Chiikawa)
4-panel comic strip, 2x2 grid layout, divided into 4 distinct frames, manga page structure
Panel 1: [Panel 1画面英文描述], speech bubble with text: "[中文对白]"
Panel 2: [Panel 2画面英文描述],
Panel 3: [Panel 3画面英文描述],
Panel 4: [Panel 4画面英文描述], speech bubble with text: "[中文对白]"
soft pastel colors, simple clean lines, kawaii aesthetic, aspect ratio 3:4
```

**[Comic Strip E Prompt]**

```text
style of Nagano (Chiikawa)
4-panel comic strip, 2x2 grid layout, divided into 4 distinct frames, manga page structure
Panel 1: [Panel 1画面英文描述],
Panel 2: [Panel 2画面英文描述], speech bubble with text: "[中文对白]"
Panel 3: [Panel 3画面英文描述], speech bubble with text: "[中文对白]"
Panel 4: [Panel 4画面英文描述],
soft pastel colors, simple clean lines, kawaii aesthetic, aspect ratio 3:4
```

**[Comic Strip F Prompt]**

```text
style of Nagano (Chiikawa)
4-panel comic strip, 2x2 grid layout, divided into 4 distinct frames, manga page structure
Panel 1: [Panel 1画面英文描述], speech bubble with text: "[中文对白]"
Panel 2: [Panel 2画面英文描述],
Panel 3: [Panel 3画面英文描述], speech bubble with text: "[中文对白]"
Panel 4: [Panel 4画面英文描述],
soft pastel colors, simple clean lines, kawaii aesthetic, aspect ratio 3:4
```

## 翻译参考

**角色名称（画面描述用英文）**：
- 吉伊 → Chiikawa
- 小八 → Hachiware
- 乌萨奇 → Usagi

**表情翻译（画面描述用英文）**：
- 豆豆眼 → small dot eyes, blank stare
- 死鱼眼 → tired eyes, dead fish eyes
- 流汗 → sweating, nervous
- 星星眼 → starry eyes, sparkling eyes

**气泡文字（保留中文原样）**：
- speech bubble with text: "看起来好好吃..."
- speech bubble with text: "我的！"
- speech bubble with text: "等等我！"
