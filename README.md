# Taiwan Forum Search

**Search Taiwan's major online communities.** PTT, Dcard, Mobile01, 巴哈姆特.

Find local opinions, reviews, and discussions that don't appear in general web search. Great for:
- 🏢 Company/interview research
- 📱 Product reviews (3C, cars, home)
- 💼 Salary/career discussions
- 🎮 Gaming communities
- 📰 Real-time sentiment on news

Works with Claude Code, Codex CLI, OpenClaw, and any Agent Skills-compatible tool.

---

## Installation

### npx skills

```bash
npx skills add git@github.com:mcltyl/taiwan-forum-search.git
```

### Manually

#### Claude Code

Add the contents of this repo to a `/.claude` folder in your project.

#### OpenCode

```bash
git clone https://github.com/mcltyl/taiwan-forum-search.git ~/.opencode/skills/taiwan-forum-search
```

#### OpenClaw

```bash
git clone https://github.com/mcltyl/taiwan-forum-search.git ~/.openclaw/skills/taiwan-forum-search
```

## Skills

| Skill | Description |
|-------|-------------|
| [taiwan-forum-search](skills/taiwan-forum-search) | Search Taiwan forums using Brave site: operator and direct scraping |

---

## Supported Forums

| Forum | Domain | Best For |
|-------|--------|----------|
| **PTT** | ptt.cc | Politics, tech jobs, stock, news |
| **Dcard** | dcard.tw | Career, relationships, campus |
| **Mobile01** | mobile01.com | 3C reviews, cars, home |
| **巴哈姆特** | forum.gamer.com.tw | Games, anime, ACG |

---

## Quick Start

Use `web_search` with site operators:

```
# Company interview experiences
site:ptt.cc OR site:dcard.tw "台積電" 面試

# Product reviews
site:mobile01.com "iPhone 15" 開箱

# Salary discussions
site:ptt.cc Tech_Job "PM" 年薪

# Game discussions
site:forum.gamer.com.tw "原神" 攻略
```

---

## Popular PTT Boards

| Board | Topic |
|-------|-------|
| Stock | 股票 |
| Tech_Job | 科技業 |
| Soft_Job | 軟體業 |
| Salary | 薪資 |
| studyabroad | 留學 |
| car | 汽車 |

---

## Tips

1. **Use Traditional Chinese** (繁體中文)
2. **Combine sources** for comprehensive research
3. **Check dates** - forum content ages quickly
4. **PTT jargon**: 推=agree, 噓=disagree, 爆=popular

---

## License

MIT

---

## Support

If you find this useful, consider buying me a coffee ☕

[![Buy Me A Coffee](https://img.shields.io/badge/Buy%20Me%20A%20Coffee-support-yellow?style=flat&logo=buy-me-a-coffee)](https://buymeacoffee.com/mclty)
