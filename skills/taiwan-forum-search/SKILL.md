---
name: taiwan-forum-search
description: Search Taiwan forums (PTT, Dcard, Mobile01, 巴哈姆特) for local discussions. Uses Brave site search + direct scraping.
---

# Taiwan Forum Search Skill

## Purpose

Search Taiwan's major online communities for discussions, opinions, and information that may not appear well in general web search. Great for:
- Local opinions and sentiment
- Product reviews (3C, cars)
- Career/interview experiences
- Gaming discussions
- Political discourse
- Real-time reactions to events

## Supported Forums

| Forum | Domain | Best For | Method |
|-------|--------|----------|--------|
| **PTT** | ptt.cc | News, politics, tech jobs, stock | `site:ptt.cc` search or direct fetch |
| **Dcard** | dcard.tw | Career, relationships, campus life | `site:dcard.tw` search |
| **Mobile01** | mobile01.com | 3C reviews, cars, home improvement | Direct fetch or `site:mobile01.com` |
| **巴哈姆特** | forum.gamer.com.tw | Games, anime, ACG culture | `site:forum.gamer.com.tw` or direct fetch |

## How to Use

### Quick Search (Brave site: operator)

For most searches, use `web_search` with `site:` operator:

```
Query: "site:ptt.cc 面試 [公司名]"
Query: "site:dcard.tw 薪水 [職位]"
Query: "site:mobile01.com [產品] 開箱"
Query: "site:forum.gamer.com.tw [遊戲名]"
```

### Direct Fetch (for browsing latest posts)

For PTT boards (non-18+ content):
```
URL: https://www.ptt.cc/bbs/{BoardName}/index.html

Popular boards:
- Stock (股票)
- Tech_Job (科技業)
- Gossiping (八卦) - requires 18+ cookie
- job (工作)
- Salary (薪資)
- Soft_Job (軟體工作)
- studyabroad (留學)
```

For Mobile01:
```
URL: https://www.mobile01.com/topiclist.php?f={forum_id}

Popular forums:
- f=568 (Samsung)
- f=566 (HTC)
- f=634 (小米)
- f=423 (Android軟體)
```

For 巴哈姆特:
```
URL: https://forum.gamer.com.tw/B.php?bsn={game_id}
```

## Search Patterns

### Job/Career Research
```
# Company interview experiences
site:ptt.cc OR site:dcard.tw "[公司名]" 面試

# Salary benchmarks
site:ptt.cc Tech_Job OR Salary "[職位]" 年薪

# Work culture
site:dcard.tw "[公司名]" 工作環境 OR 加班
```

### Product Research
```
# Product reviews
site:mobile01.com "[產品名]" 開箱 OR 心得

# Comparison
site:mobile01.com "[產品A]" vs "[產品B]"

# Problems/issues
site:mobile01.com "[產品名]" 災情 OR 問題
```

### Gaming/ACG
```
# Game discussions
site:forum.gamer.com.tw "[遊戲名]" 攻略

# Reviews
site:forum.gamer.com.tw "[遊戲名]" 心得 OR 評價
```

### Sentiment/Opinion
```
# Political discussions (PTT Gossiping equivalent topics appear in other boards)
site:ptt.cc "[話題]" 看法 OR 怎麼看

# Hot topics
site:ptt.cc "[事件]" 爆卦 OR 新聞
```

## Limitations

1. **PTT Gossiping Board**: Requires 18+ cookie verification - use `site:ptt.cc Gossiping` search instead of direct fetch
2. **Dcard Direct Fetch**: Blocked by Cloudflare - use `site:dcard.tw` search only
3. **Rate Limits**: Space out requests to avoid being blocked
4. **Content Age**: Search results may include older content; check dates

## Board Name Reference

### PTT Popular Boards
| Board | Topic |
|-------|-------|
| Stock | 股票投資 |
| Tech_Job | 科技業工作 |
| Soft_Job | 軟體工程師 |
| job | 一般工作 |
| Salary | 薪資討論 |
| studyabroad | 留學 |
| car | 汽車 |
| MobileComm | 手機通訊 |
| PC_Shopping | 電腦採購 |
| NBA | NBA |
| Baseball | 棒球 |
| C_Chat | ACG閒聊 |

### Dcard Popular Forums
| Forum | Topic |
|-------|-------|
| job | 工作 |
| softwareengineer | 軟體工程師 |
| interview | 面試 |
| relationship | 感情 |
| graduate | 研究所 |
| salary | 薪資 |

### Mobile01 Forum IDs
| ID | Topic |
|----|-------|
| 568 | Samsung |
| 566 | HTC |
| 634 | 小米 |
| 588 | Asus |
| 423 | Android軟體 |
| 7 | 汽車 |
| 37 | 居家 |

## Example Workflows

### Research a company before interview
```
1. web_search: "site:ptt.cc [公司名] 面試"
2. web_search: "site:dcard.tw [公司名] 面試心得"
3. web_search: "site:ptt.cc [公司名] 薪水 年終"
4. Summarize findings
```

### Product purchase decision
```
1. web_search: "site:mobile01.com [產品] 開箱 心得"
2. web_search: "site:mobile01.com [產品] 災情 問題"
3. web_search: "site:ptt.cc [產品] 推薦"
4. Compare pros/cons
```

### Track breaking news sentiment
```
1. web_search: "site:ptt.cc [事件關鍵字]" (sort by freshness if available)
2. web_fetch PTT board directly for latest
3. Summarize discussion themes
```

## Tips

1. **Use Traditional Chinese** for search queries (繁體中文)
2. **Add board name** for PTT to narrow results: `site:ptt.cc/bbs/Tech_Job`
3. **Combine sources** for comprehensive view
4. **Check post dates** - forum content ages quickly
5. **PTT jargon**: 推 = upvote/agree, 噓 = downvote/disagree, 爆 = popular thread

---

*Made for Taiwan local context research 🇹🇼*
