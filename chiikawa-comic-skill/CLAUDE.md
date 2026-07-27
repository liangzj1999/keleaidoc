# Chiikawa 脑洞漫画工作室

这是一个用于创作 Chiikawa（吉伊卡哇）风格漫画的 Claude Code 技能集合。

## 🚀 快速开始

### 一键生成（推荐）

```
/chiikawa [主题或联名IP]
```

系统会自动判断并执行相应流程！

**示例：**
- `/chiikawa 露营` → 普通主题流程
- `/chiikawa 名侦探柯南` → 联名IP流程

---

## 可用技能

### 🚀 `/chiikawa` — 一键生成（自动判断）
输入主题或联名IP，自动完成整个流程。

**智能判断：**
- 普通主题（露营、减肥、失眠...）→ script → prompt → xiaohongshu
- 联名IP（柯南、哈利波特、原神...）→ crossover → prompt → xiaohongshu

---

### 📝 `/chiikawa-script` — 剧本生成器
根据主题创作 Chiikawa 风格的四格漫画分镜脚本。

**输入**：任意主题/关键词
**输出**：1封面 + 6四格漫画分镜脚本（含对白）

---

### 🤝 `/chiikawa-crossover` — 跨界联名编剧
创作 Chiikawa 三小只与指定 IP 互动的短漫剧本。

**输入**：联名IP名称
**输出**：8-12个分镜的短漫剧本（含对白）

---

### 🎨 `/chiikawa-prompt` — 生图提示词生成器
将中文分镜脚本翻译成英文文生图提示词。

**输入**：分镜脚本
**输出**：英文提示词（含气泡和文字）

**特点**：
- 有对白的分镜会生成 `speech bubble with text: "[台词]"`
- AI 生图时会自动生成带文字的气泡框

---

### 📱 `/chiikawa-xiaohongshu` — 小红书文案生成器
生成小红书平台的爆款发布方案。

**输入**：主题/IP名称
**输出**：标题 + 正文 + 标签 + BGM + 投票

---

## 角色设定

| 角色 | 性格 |
|------|------|
| 吉伊 | 胆小爱哭，善良 |
| 小八 | 天真活泼，爱解说 |
| 乌萨奇 | 混沌不可控 |

## 使用方式

### 方式一：一键生成（最简单）
```
/chiikawa 露营           # 自动走普通主题流程
/chiikawa 名侦探柯南     # 自动走联名IP流程
```

### 方式二：分步执行（更灵活）
```
/chiikawa-script 露营           # 1. 生成剧本
/chiikawa-prompt                # 2. 生成提示词（含气泡文字）
/chiikawa-xiaohongshu           # 3. 生成文案
```

## 项目结构

```
.claude/
  commands/
    chiikawa.md                          # 一键生成 command（自动判断）
  skills/
    chiikawa-script/
      SKILL.md                           # 普通主题剧本
    chiikawa-crossover/
      SKILL.md                           # 联名剧本
    chiikawa-prompt/
      SKILL.md                           # 生图提示词（含气泡文字）
    chiikawa-xiaohongshu/
      SKILL.md                           # 小红书文案
```

## 输出示例

### 剧本输出
```
### 【四格漫画 A】
* *Panel 1:* 吉伊坐在桌前，面前放着一碗拉面，眼睛变成星星眼
  > 吉伊："看起来好好吃..."
* *Panel 2:* 小八在旁边解说
* *Panel 3:* 乌萨奇突然出现
  > 乌萨奇："我的！"
* *Panel 4:* 三小只争抢拉面的混乱场面
```

### 提示词输出
```text
style of Nagano (Chiikawa)
4-panel comic strip, 2x2 grid layout, divided into 4 distinct frames
Panel 1: Chiikawa sitting at table with ramen, starry eyes, speech bubble with text: "看起来好好吃..."
Panel 2: Hachiware watching and explaining,
Panel 3: Usagi suddenly appears, speech bubble with text: "我的！"
Panel 4: three creatures fighting over ramen, chaotic scene,
soft pastel colors, simple clean lines, kawaii aesthetic, aspect ratio 3:4
```

**注意**：画面描述用英文，气泡文字保留中文原样！
