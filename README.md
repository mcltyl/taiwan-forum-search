# Taiwan Forum Search 🇹🇼

**Search Taiwan's online communities for local opinions, reviews, and discussions.**

PTT, Dcard, Mobile01, 巴哈姆特, and more — the information that doesn't show up in regular web search.

Works with Claude Code, Codex CLI, OpenClaw, and any Agent Skills-compatible tool.

---

## Why This Skill?

Taiwan has a rich forum culture. Locals discuss everything:
- 🏢 Company reviews & interview experiences
- 📱 Product reviews & disaster reports
- 💼 Salary benchmarks
- 🍜 Restaurant recommendations
- 🎮 Game strategies
- 📰 Current events sentiment

**This knowledge doesn't appear in regular search.** You need to know where to look and how to search.

---

## Installation

### npx skills

```bash
npx skills add git@github.com:mcltyl/taiwan-forum-search.git
```

### Manually

```bash
# OpenClaw
git clone https://github.com/mcltyl/taiwan-forum-search.git ~/.openclaw/skills/taiwan-forum-search

# OpenCode  
git clone https://github.com/mcltyl/taiwan-forum-search.git ~/.opencode/skills/taiwan-forum-search

# Claude Code
# Add to /.claude folder in your project
```

---

## Forums Covered

| Forum | Demographic | Best For |
|-------|-------------|----------|
| **PTT** | Tech-savvy, 25-45 | Jobs, stocks, news, deep discussions |
| **Dcard** | Students, 18-30 | Career, relationships, lifestyle |
| **Mobile01** | Consumers, 25-50 | Product reviews, cars, home |
| **巴哈姆特** | Gamers, 15-35 | Games, anime, ACG |
| **BackPackers** | Travelers | Travel planning |
| **ePrice** | Phone buyers | Phone specs, comparisons |

---

## Quick Start

Use `web_search` with `site:` operator:

```
# Company research
site:ptt.cc "[公司名]" 面試
site:dcard.tw "[公司名]" 薪水

# Product research
site:mobile01.com "[產品]" 開箱 心得
site:mobile01.com "[產品]" 災情

# Game research
site:forum.gamer.com.tw "[遊戲名]" 攻略
```

### Narrow by Board

```
# PTT specific boards
site:ptt.cc/bbs/Tech_Job [keyword]
site:ptt.cc/bbs/Stock [keyword]
site:ptt.cc/bbs/MobileComm [keyword]

# Dcard specific forums
site:dcard.tw/f/job [keyword]
site:dcard.tw/f/food [keyword]
```

---

## What's Inside

This skill includes:

### Search Patterns
- Career research (interviews, salary, culture)
- Product research (reviews, problems, comparisons)
- Food & restaurant recommendations
- Current events & sentiment
- Gaming discussions

### Result Interpretation
- How to read PTT 推/噓 metrics
- Credibility assessment framework
- Cross-referencing strategies

### Board References
- PTT popular boards with descriptions
- Dcard forum list
- Mobile01 forum IDs
- 巴哈姆特 game IDs

### Workflow Templates
- Company research before interview
- Product purchase decision
- Breaking news context
- Restaurant evaluation

---

## Credibility Tips

### Trust More
✅ Detailed personal experience  
✅ Photos/screenshots  
✅ Balanced pros & cons  
✅ High engagement  
✅ Multiple sources agree  

### Trust Less
🚩 Vague claims  
🚩 New account  
🚩 Sounds like PR  
🚩 No negatives mentioned  
🚩 Old post (check date!)  

---

## Limitations

| Issue | Solution |
|-------|----------|
| PTT 18+ boards | Use `site:` search instead of direct fetch |
| Dcard blocked | Use `site:` search only, no direct fetch |
| Old results | Add year to search: `[keyword] 2024` |

---

## Related

This skill is also included in [Taiwan Skills](https://github.com/mcltyl/taiwan-guide-skills), a comprehensive Taiwan collection with 8 skills.

---

## License

MIT

---

## Support

If you find this useful, consider buying me a coffee ☕

[![Buy Me A Coffee](https://img.shields.io/badge/Buy%20Me%20A%20Coffee-support-yellow?style=flat&logo=buy-me-a-coffee)](https://buymeacoffee.com/mclty)
