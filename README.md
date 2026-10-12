# AI News Skill — a daily AI news digest inside Claude Code, Codex & OpenClaw

<p align="center">
  <img src="./assets/logo.png" alt="AI Intelligence Skill" width="600">
</p>

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://github.com/frankzch/ai-news-skill/blob/main/LICENSE)
[![Agent Skills](https://img.shields.io/badge/AgentSkills-compatible-blue)](https://agentskills.io/)

[English](./README.md) | [中文](./README.zh-CN.md)

---

Ask your coding agent *"what happened in AI today?"* and get a deduplicated, summarized digest from **370+ curated sources**: official AI lab blogs, ~310 top AI builders on X (Karpathy, Sam Altman, Simon Willison…), Reddit and Hacker News discussions, 13 AI YouTube channels, Hugging Face papers and GitHub Trending. Summaries in English or Chinese. **Free, no API key, one `git clone` to install.**

```bash
git clone https://github.com/frankzch/ai-news-skill.git ~/.claude/skills/ai-news-skill
```

Works with Claude Code, Codex, OpenClaw and Antigravity (see [Quick Start](#-quick-start) for paths).

📊 The **370+ sources** (and growing — contributions of new sources are welcome!):
- **16 News Sources** — mainstream AI/ML media like TechReview, TheVerge, Venturebeat, artificialintelligence-news, TechCrunch, Machine Learning Mastery, MarkTechPost, plus official blogs from Nvidia, Apple ML, Microsoft AI, Google DeepMind, OpenAI, Google Research, Hugging Face — and **Hugging Face daily papers** for the latest research highlights
- **340+ Discussion Sources** — Hacker News, 16 Reddit sources (subreddits + keyword searches) and 320+ X sources: ~310 top AI builders (an auto-expanding list), 12 keyword searches and 2 site-wide high-engagement searches that catch viral AI posts from any account. X builders include: Andrej Karpathy, Sam Altman, Simon Willison, Peter Steinberger, Aditya Agarwal, Dan Shipper, Nikunj Kothari, Ryo Lu, Matt Turck, Aaron Levie, Alex Albert, Guillermo Rauch, Amjad Masad, Amanda Askell, Kevin Weil, etc.
- **13 YouTube Channels** — leading AI creators, summarized from transcripts: Matt Wolfe, Dwarkesh Patel, DataDrivenNYC, Latent Space, Sequoia Capital, Yannic Kilcher, NoPriorsPodcast, RedpointAI, EveryInc, Fireship, Lex Fridman, Wes Roth, Two Minute Papers
- **GitHub Trending** — weekly hot AI repositories

> 🔄 All sources are automatically refreshed every **2 hours**

### 🌟 Powered by InBrief.info
The data processing behind this Agent Skill is powered for free by **[InBrief.info](https://inbrief.info)**. If you just want to browse the latest, highest-quality AI news directly via a web page, we highly recommend visiting **[InBrief.info](https://inbrief.info)** for your personalized daily briefing — no Agent setup needed!

> 🔑 **Register to unlock more results**
> Per-request result caps by tier:
> - **No / invalid API Key** (guest): up to **3 items** per request
> - **Logged-in, non-member**: up to **6 items** per request
> - **Member**: up to **100 items** per request
>
> To unlock higher tiers:
> 1. Sign up for free at **[InBrief.info](https://inbrief.info)**
> 2. Open **Settings → PulseAI Agent Skill** and copy your API Key
> 3. Paste it into the `api_key` field of `config.yaml` at the skill root (copy the template from [`assets/config.default.yaml`](./assets/config.default.yaml))

<p align="center">
  <img src="./assets/screenshot_news_en.png" alt="News" width="48%">
  <img src="./assets/screenshot_social_en.png" alt="Social" width="48%">
</p>
<p align="center">
  <img src="./assets/screenshot_video_en.png" alt="Video" width="48%">
  <img src="./assets/screenshot_opensource_en.png" alt="Open Source" width="48%">
</p>

### ⚡ Quick Start
Install this skill into your AI agent (supports OpenClaw, Claude Code, Antigravity, Codex)

**OpenClaw**
```bash
# Currently manual installation, will be submitted to ClawHub later
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

### 🎛️ Modifying Settings & Filters
No complex configuration needed — just control your Agent through natural conversation. For example:
- "Show me AI videos released by top KOLs in the past 5 days"
- "Give me today's AI news, but exclude TechReview"
- "Fetch Reddit AI discussions from the past 3 days"

The agent automatically understands your intent and translates it into precise filtering conditions. You can control:

- 📂 **Filter by Category** — Include or exclude content types: News, Open Source, Social Discussions, KOL Insights
- 📡 **Filter by Source** — Include or exclude specific platforms (e.g., Reddit, TechCrunch, etc.)
- ⏰ **Time Range** — Customize how far back to fetch (default: past 24 hours)
- 🔢 **Result Limit** — Control the number of items returned (effective cap depends on tier: guest 3 / logged-in 6 / member 100)
- 📝 **Summary Display** — Choose whether to show short summaries, long summaries
- 🔗 **Link Display** — Choose whether to show original article links
- 🌐 **Language** — Choose output language (English or Chinese). Defaults to your system language; falls back to English if neither
- 💾 **Output Format** — Results can be printed directly to the terminal or exported as a JSON file

### 🔧 AgentSkills Compatible
This skill follows the [AgentSkills](https://agentskills.io/) open standard. The `SKILL.md` file contains all metadata and instructions needed for any compatible agent to discover, activate, and execute this skill automatically.

### ❓ FAQ

**How do I get the latest AI news inside Claude Code or Codex?**
Install this skill (one `git clone`), then ask in plain language, e.g. "AI news from the past 24 hours, news only, long summaries". The agent turns it into category / source / time-range filters.

**Can I follow AI builders and KOLs on X without scrolling X?**
Yes. High-engagement posts from ~310 AI builders are collected and summarized; ask for "KOL insights from the past 3 days".

**Is it free?**
Yes. Without an account each request returns up to 3 items; a free InBrief.info account raises it to 6; members get up to 100.

**Can I get the digest in Chinese?**
Yes. Every item is summarized in both English and Chinese; ask for Chinese, or it follows your system language.

**Can I self-host the pipeline instead?**
Yes — the collection and curation engine is open source: [ai-news-brief](https://github.com/frankzch/ai-news-brief) (MIT).

### 🤝 Contributing
We welcome contributions! Please see [CONTRIBUTING.md](./CONTRIBUTING.md) for guidelines.

### 📄 License
This project is licensed under the [MIT License](./LICENSE).
