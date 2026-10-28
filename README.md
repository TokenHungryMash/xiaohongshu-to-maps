# 小红书收藏转 Google Maps · Xiaohongshu to Google Maps

**2.0 · v2.0.0** | 中文 & English

把收藏夹里的旅行灵感，整理成看得懂、查得到、出门用得上的地图清单。

Turn saved travel inspiration into organized Google Maps lists, with useful notes and traceable sources.

## 中文介绍

这是一个 AI 助手 Skill：通过小红书点点读取收藏笔记，由执行助手提取地点、合并重复推荐、区分分店，先交付分类清单和完整 Markdown 知识库，再按你的确认保存到 Google Maps 原生清单。

### 2.0 的重点

- **先看完整清单，再决定导入。** 对话中展示分类表格，同时保存更详细的 Markdown 知识库，保留具体评价、推荐单品、重要分歧与来源。
- **地点和商品分开整理。** 菜名、商品不会直接变成地图地点；不明确的归属和店铺身份会单独标记。
- **分店贴近旅行范围。** 保留笔记明确推荐的门店；只有品牌线索时，按目的地主城区精选适合的分店，并区分作者到访与同品牌参考。
- **分类保存地图清单。** 正餐与小吃、咖啡与烘焙甜点、购物、景点与街区分别整理，设置对应图标并核对保存结果。住宿留在知识库中供规划参考。
- **备注简洁，来源可回查。** 地图备注使用“小红书观点＋来源”两段，保留推荐单品和必要缺点，使用稳定编号对应原笔记标题。
- **支持继续未完成的任务。** 保留轻量进度，沿用已有清单，减少重复读取和重复添加。

### 使用条件

需要支持本地 Skill 和浏览器操作的 AI 助手，以及可使用的小红书点点和 Google Maps。登录、扫码或账号验证可能需要你完成。仅整理预览时，无需提前登录 Google Maps。

本仓库提供执行说明和参考模板，不包含独立爬虫或后台自动同步程序。读取范围取决于当前网站和助手环境；遗漏与无法确认的地点会如实说明，不保证全媒介零遗漏。历史价格、营业时间和作者观点不会当作当前已核实事实。

### 使用示例

```text
使用 $xiaohongshu-to-maps，整理我的“福冈旅行”收藏专辑。
先给我完整的分类清单和 Markdown 知识库，保留推荐单品、评价和来源。
我确认后，再保存到 Google Maps 分类清单。
```

```text
继续上次的地图导入，沿用已有清单，只补未完成的地点和备注。
```

默认先预览再确认；已明确授权直接导入时沿用授权。新建清单默认私人，已有清单保留分享设置和你的备注。未匹配地点单独列出原因，不用猜测结果填充地图。

## English

An AI agent skill that turns saved Xiaohongshu (RED) travel posts into native Google Maps lists. Diandian reads the available posts; the executing agent extracts places, merges duplicate mentions, distinguishes branches, and prepares a categorized preview plus a detailed Markdown knowledge base before importing approved places.

### What's in 2.0

- **Preview before import.** Get a full categorized overview in chat and a richer Markdown reference with recommendations, useful details, differing opinions, and sources.
- **Separate places from products.** Dishes and products are not treated as map locations. Unclear attribution and uncertain place identities remain explicitly marked.
- **Handle branches within your travel area.** Keep explicitly recommended locations; for brand-only recommendations, select suitable central branches and distinguish them from places the author actually visited.
- **Create categorized map lists.** Organize food, cafés and bakeries, shopping, and sights into native lists with category icons where available. Accommodation stays in the knowledge base for planning.
- **Keep notes practical and traceable.** Each map note separates the post's recommendations from its source, using stable reference numbers and original post titles.
- **Resume unfinished imports.** Lightweight progress records help reuse existing lists and avoid duplicate work.

### Requirements

Use an AI assistant with local skill support and browser interaction, plus access to Xiaohongshu's Diandian workflow and Google Maps. You may need to sign in or complete account verification. Google Maps sign-in is only needed at the import stage.

This repository contains instructions and templates, not a standalone scraper or background synchronization service. Reading coverage depends on the websites and assistant environment. Gaps are reported; complete coverage across every media type is not guaranteed. Historical prices, opening hours, and authors' opinions are not presented as current verified facts. The execution instructions and templates are in Chinese; this introduction is bilingual.

### Example

```text
Use $xiaohongshu-to-maps to organize my saved Fukuoka travel collection.
Show me the full categorized preview and save a detailed Markdown knowledge base,
including recommended dishes, opinions, and sources.
After I confirm, save the places into categorized Google Maps lists.
```

```text
Continue the previous import in the same Google Maps lists.
Use the saved progress and add only unfinished places and notes.
```

New lists are private by default. Existing sharing settings and personal notes are preserved. Explicit authorization to import is reused. Unmatched places are reported with reasons instead of being guessed.

## 安装 / Installation

macOS / Linux:

```bash
git clone https://github.com/TokenHungryMash/xiaohongshu-to-maps.git ~/.codex/skills/xiaohongshu-to-maps
```

Windows PowerShell:

```powershell
git clone https://github.com/TokenHungryMash/xiaohongshu-to-maps.git "$env:USERPROFILE\.codex\skills\xiaohongshu-to-maps"
```

已有安装时，更新原仓库或将发布包中的文件复制到原 Skill 目录，保留自己的本地修改。必要时重新打开助手会话。

For an existing installation, update its checkout or copy the release files into the skill directory while preserving local changes. Reload the assistant session if necessary.

## 文件 / Repository contents

| Path | 用途 / Purpose |
|---|---|
| SKILL.md | 执行流程与完成标准 / Workflow and completion criteria |
| agents/openai.yaml | 展示信息与默认提示词 / Display metadata and default prompt |
| assets/icon.svg | Skill 图标 / Skill icon |
| references/diandian-prompts.md | 点点读取模板 / Reading prompts |
| references/pre-import-preview.md | 导入前预览格式 / Preview guidance |
| references/place-data.md | 进度与恢复记录 / Progress and recovery records |
| references/first-list-delivery.md | 导入完成说明示例 / Import delivery example |
| references/capability-observations.md | 有限测试观察 / Limited capability observations |

个人收藏内容、账号凭据和实际运行记录请留在本地。

Keep personal collections, credentials, and actual run records out of this repository.
