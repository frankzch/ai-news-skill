# AI News Skill：在 Claude Code / Codex / OpenClaw 里每天看 AI 资讯摘要

<p align="center">
  <img src="./assets/logo.png" alt="AI Intelligence Skill" width="600">
</p>

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://github.com/frankzch/ai-news-skill/blob/main/LICENSE)
[![Agent Skills](https://img.shields.io/badge/AgentSkills-compatible-blue)](https://agentskills.io/)

[English](./README.md) | [中文](./README.zh-CN.md)

---

每天把国外 AI 一手信息整理成中文摘要：在编程 Agent 里问一句“今天 AI 圈有什么新闻？”，就能拿到来自 **370+ 个精选信息源**、去重后的中英双语摘要——AI 大厂官方博客、X 上约 310 位顶尖 AI 从业者（Karpathy、Sam Altman、Simon Willison 等）、Reddit 与 Hacker News 讨论、13 个 AI YouTube 频道、Hugging Face 论文和 GitHub Trending。**完全免费，不需要 API Key，一条 `git clone` 即可安装。**

```bash
git clone https://github.com/frankzch/ai-news-skill.git ~/.claude/skills/ai-news-skill
```

支持 Claude Code、Codex、OpenClaw 和 Antigravity（各平台安装路径见[快速开始](#-快速开始)）。

📊 **370+ 个信息源**（持续增加中，欢迎提供更多信息源地址）：
- **16 个新闻资讯源** — TechReview、TheVerge、Venturebeat、artificialintelligence-news、TechCrunch、Machine Learning Mastery、MarkTechPost 等主流 AI/ML 媒体，以及 Nvidia、Apple ML、Microsoft AI、Google DeepMind、OpenAI、Google Research、Hugging Face 等官方博客，并包含 **Hugging Face 每日论文榜**，第一时间追踪前沿研究
- **340+ 个社区讨论源** — Hacker News、16 个 Reddit 源（板块热帖 + 关键词搜索）和 320+ 个 X 源：约 310 位顶尖 AI 从业者账号（名单自动扩充）+ 12 个关键词搜索 + 2 个全站高赞搜索（任何账号的爆款 AI 帖都能捕捉到）。X 账号包括：Andrej Karpathy、Sam Altman、Simon Willison、Peter Steinberger、Aditya Agarwal、Dan Shipper、Nikunj Kothari、Ryo Lu、Matt Turck、Aaron Levie、Alex Albert、Guillermo Rauch、Amjad Masad、Amanda Askell、Kevin Weil 等
- **13 个 YouTube 频道** — 基于字幕生成摘要：Matt Wolfe、Dwarkesh Patel、DataDrivenNYC、Latent Space、Sequoia Capital、Yannic Kilcher、NoPriorsPodcast、RedpointAI、EveryInc、Fireship、Lex Fridman、Wes Roth、Two Minute Papers
- **GitHub 开源趋势榜** — 每周热门 AI 仓库

> 🔄 所有信息源每 **2 小时** 自动更新一次

### 🌟 数据抓取由 InBrief.info 驱动
此 Agent Skill背后的全网AI信息数据处理由 **[InBrief.info](https://inbrief.info)** 免费驱动。如果你只想直接通过网页查阅最新、最优质的 AI 资讯，强烈推荐直接访问 **[InBrief.info](https://inbrief.info)** 获取个性化的专属简报，无需折腾任何 Agent！

> 🔑 **注册账户，获取更多返回结果**
> 按每次调用返回的条数分三档：
> - **未配置 / 无效 API Key**（访客）：每次最多返回 **3 条**
> - **已登录非会员**：每次最多返回 **6 条**
> - **会员**：每次最多返回 **100 条**
>
> 解锁步骤：
> 1. 前往 **[InBrief.info](https://inbrief.info)** 免费注册账户
> 2. 进入 **设置页 → PulseAI Agent Skill**，复制你的 API Key
> 3. 将 Key 粘贴到 skill 根目录下的 `config.yaml`（可从 [`assets/config.default.yaml`](./assets/config.default.yaml) 复制模板）的 `api_key` 字段

<p align="center">
  <img src="./assets/screenshot_news.png" alt="新闻" width="48%">
  <img src="./assets/screenshot_social.png" alt="社媒" width="48%">
</p>
<p align="center">
  <img src="./assets/screenshot_video.png" alt="视频" width="48%">
  <img src="./assets/screenshot_opensource.png" alt="开源" width="48%">
</p>

### ⚡ 快速开始
在你的 AI agent 中安装此 skill（支持 OpenClaw, Claude Code, Antigravity, Codex）

**OpenClaw**
```bash
# 目前为手动安装，后期会提交到 ClawHub
git clone https://github.com/frankzch/ai-news-skill.git ~/skills/ai-news-skill
```

**Claude Code**
```bash
git clone https://github.com/frankzch/ai-news-skill.git ~/.claude/skills/ai-news-skill
```

**Antigravity Agent**
```bash
git clone https://github.com/frankzch/ai-news-skill.git ~/.agents/skills/ai-news-skill
```

**Codex**
```bash
git clone https://github.com/frankzch/ai-news-skill.git ~/.codex/skills/ai-news-skill
```

### 🎛️ 修改设置与过滤
无需配置繁琐的参数，直接在对话中控制你的 Agent。例如：
- "最近5天有哪些大V发布的AI视频"
- "给我看看今天的AI新闻，但排除 TechReview 平台的"
- "获取过去 3天的 Reddit上关于AI的讨论"

Agent 会自动理解你的需求并转化为精确的过滤条件。你可以控制的维度包括：

- 📂 **按分类筛选** — 指定只看或排除某类内容：新闻资讯、开源项目、社交讨论、KOL 观点
- 📡 **按来源筛选** — 指定只看或排除特定平台（如 Reddit、TechCrunch等）
- ⏰ **时间范围** — 自定义获取过去多少小时的内容（默认 24 小时）
- 🔢 **数量限制** — 控制返回的条目数量（实际上限受会员等级约束：访客 3 / 已登录 6 / 会员 100）
- 📝 **摘要显示** — 选择是否显示短摘要、长摘要
- 🔗 **链接显示** — 选择是否显示原文链接
- 🌐 **输出语言** — 选择输出语言（英文或中文），默认跟随系统语言，若系统语言非中英文则回退为英文
- 💾 **输出方式** — 结果可直接打印到终端，也可导出为 JSON 文件

### 🔧 AgentSkills 标准兼容
本 Skill 遵循 [AgentSkills](https://agentskills.io/) 开放标准。`SKILL.md` 文件包含所有元数据和指令，任何兼容的 Agent 都可以自动发现、激活和执行此 Skill。

### ❓ 常见问题

**怎么在 Claude Code 或 Codex 里直接查最新 AI 资讯？**
安装本 skill（一条 `git clone`），然后直接用中文问，例如“过去 24 小时的 AI 新闻，只看新闻类，用长摘要”。Agent 会自动转成分类、来源、时间范围等过滤条件。

**不刷 X，也能跟踪 AI 大 V 的观点吗？**
可以。约 310 位 AI 从业者的高互动推文会被采集并总结，直接问“过去 3 天 KOL 的观点”即可。

**收费吗？**
免费。不注册每次最多返回 3 条；免费注册 InBrief.info 后每次 6 条；会员每次最多 100 条。

**能看中文摘要吗？**
能。每条内容都有中英双语摘要，要求用中文输出即可，默认跟随系统语言。

**想自己部署采集流水线怎么办？**
采集与精选引擎已开源：[ai-news-brief](https://github.com/frankzch/ai-news-brief)（MIT）。

### 🤝 参与贡献
欢迎贡献代码！请查看 [CONTRIBUTING.md](./CONTRIBUTING.md) 了解贡献指南。

### 📄 开源协议
本项目采用 [MIT 协议](./LICENSE) 开源。
