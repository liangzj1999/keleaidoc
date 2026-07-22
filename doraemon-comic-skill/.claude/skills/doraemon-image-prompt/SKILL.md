---
name: doraemon-image-prompt
description: 为每一幕生成一张哆啦A梦画风四格漫画的 AI 生图提示词，一幕=一张图=四个格子(panel1-4)，人物严格保持哆啦A梦原作形象，每格带气泡对白。当需要「生图提示词/画图 prompt/画四格漫画」，或作为四格漫画流水线的第三步时使用。
---

# 哆啦A梦四格漫画生图提示词（每幕一张图）

把分镜脚本转化为可直接喂给 AI 绘图模型（Midjourney / 即梦 / Nano Banana / SD 等）的**生图提示词**。

> **产出数量 = 幕数**：有 N 幕就生成 **N 段提示词**，每一段画**一张四格漫画**（该张图内部含 Panel 1-4 四个格子）。
> 核心目标：**画风与人物 100% 贴近哆啦A梦原作，同一张图内四格连贯、跨张之间人物一致，气泡对白清晰**。

## 工作目录

本篇所有文件都在同一个工作目录 `output/<主题>-<日期>/` 下。命令指定了就用指定的；否则默认选 `output/` 下**最近修改**的那个子文件夹继续写。

## 输入

优先读取 `<工作目录>/02-分幕.md`（已含 N 幕、每幕 Panel 1-4）。若不存在，尝试 `<工作目录>/01-剧本.md` 并先在心里完成分幕+四格切分；都没有则提示用户。

## 提示词格式：画面英文 + 气泡中文（重要）

采用**混合写法**，实测对生图模型最友好：

- **画面描述用英文**（场景、动作、表情、景别、背景）。
- **气泡台词保留中文原样**，写成 `speech bubble with text: "中文台词"`，模型会画出带该中文的气泡框。
- 每张图用一个 ` ```text ` 代码块包裹，方便一键复制。

## 统一风格后缀（每张图都带，保证跨张一致）

```
style of Fujiko F. Fujio (Doraemon), retro anime manga, clean bold black outlines, bright flat cel colors, 1970s-80s Japanese cartoon look, cute and rounded, aspect ratio 3:4
```

## 人物形象基准（写画面时按此翻译，保证跨张一致）

| 角色 | 英文名 | 固定外观（英文关键词） |
|---|---|---|
| 哆啦A梦 | Doraemon | round chubby blue robot cat, white round face, red nose, red collar with golden bell, white belly pouch, no ears, short limbs |
| 大雄 | Nobita | little boy, black short hair, round black-framed glasses, yellow polo shirt, blue shorts |
| 静香 | Shizuka | girl, brown short bob hair, pink dress, gentle face |
| 胖虎 | Gian | big burly boy, black buzz cut, orange shirt, angry face |
| 小夫 | Suneo | skinny boy, pointy mouth, side-parted hair, blue/green shirt, smug face |

## 表情 / 状态翻译参考

| 中文 | 英文关键词 |
|---|---|
| 惊讶 / 震惊 | shocked, wide eyes, jaw drop |
| 哭 / 爆哭 | crying, streams of tears |
| 得意 / 坏笑 | smug grin, proud smirk |
| 生气 / 暴怒 | angry, furious, veins popping |
| 冒汗 / 紧张 | sweat drop, nervous |
| 兴奋 / 星星眼 | sparkling starry eyes, excited |
| 无奈 / 呆滞 | blank stare, exasperated |
| 得意掏道具 | Doraemon pulling gadget from belly pouch, proud |

音效字（可选）：`Japanese onomatopoeia SFX text` + 中文/日文拟声词，如「叮！」「砰！」。

## 版式约定

一张图 = four-panel comic strip, 2x2 grid layout, divided into 4 distinct frames, white gutters, black panel borders。

## 输出格式（重要：每个代码块必须自包含、复制即用）

写入 `<工作目录>/03-生图提示词.md`，并在对话展示。**每张四格漫画的代码块要能单独复制去生图，无需再拼接其它内容**，因此每块内部都要完整包含：① 统一风格前缀，② 本幕出场角色的外观锁定（`Characters:` 行，只列出现的角色），③ 版式，④ Panel 1-4，⑤ 比例。

```markdown
# 生图提示词：《标题》（共 N 张四格漫画）

## 四格漫画 1（第 1 幕）

​```text
style of Fujiko F. Fujio (Doraemon), retro anime manga, clean bold black outlines, bright flat cel colors, 1970s-80s Japanese cartoon look, cute and rounded
Characters: Nobita = little boy, black short hair, round black-framed glasses, yellow polo shirt, blue shorts; Doraemon = round chubby blue robot cat, white round face, red nose, red collar with golden bell, white belly pouch, no ears, short limbs
four-panel comic strip, 2x2 grid layout, divided into 4 distinct frames, white gutters, black panel borders
Panel 1: [英文画面描述], speech bubble with text: "中文台词"
Panel 2: [英文画面描述],
Panel 3: [英文画面描述], speech bubble with text: "中文台词"
Panel 4: [英文画面描述], speech bubble with text: "中文台词"
aspect ratio 3:4
​```

## 四格漫画 2（第 2 幕）
...（同格式，后续每幕一张，Characters 行只列该幕出现的角色）

## 出图参数建议
- 比例：3:4（竖版适合小红书）
- 负向提示词：no extra fingers, no realistic photo style, no messy garbled text, no distorted faces
```

说明：
- **`Characters:` 行只列出该幕真正出现的角色**，避免模型多画没出场的人。
- 没有对白的格子就不写 `speech bubble`。
- 顶部可保留一段总的风格/角色说明作导览，但**正式提示词以每块内自包含的代码块为准**。

完成后提示用户：可继续用 `xiaohongshu-post` 生成小红书文案。
