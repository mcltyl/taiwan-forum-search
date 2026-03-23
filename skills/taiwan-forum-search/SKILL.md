---
name: taiwan-forum-search
description: Search Taiwan forums (PTT, Dcard, Mobile01, 巴哈姆特, and more) for local discussions, opinions, and reviews. Includes search patterns, result interpretation, and credibility assessment.
---

# Taiwan Forum Search Skill

## Purpose

Search Taiwan's online communities for discussions, opinions, and local knowledge that doesn't appear in general web search.

## When to Activate

- User needs Taiwan-specific opinions or reviews
- User researches companies, products, or services in Taiwan
- User wants local sentiment on current events
- User needs information only locals would know

---

# FORUMS OVERVIEW

## Primary Forums

| Forum | Domain | Demographic | Best For |
|-------|--------|-------------|----------|
| **PTT** | ptt.cc | 25-45, tech-savvy | Tech jobs, stocks, news, in-depth discussion |
| **Dcard** | dcard.tw | 18-30, students/young professionals | Career, relationships, lifestyle, campus |
| **Mobile01** | mobile01.com | 25-50, consumers | 3C reviews, cars, home, detailed product research |
| **巴哈姆特** | forum.gamer.com.tw | 15-35, gamers | Games, anime, ACG culture |

## Secondary Forums

| Forum | Domain | Best For |
|-------|--------|----------|
| **低卡** | dcard.tw/f/food | Food reviews (Dcard subforum) |
| **批踢踢精華區** | ptt.cc/man/ | Historical discussions, curated content |
| **ePrice** | eprice.com.tw | Phone comparisons, specs |
| **T17** | t17.techbang.com | Tech discussions |
| **BackPackers** | backpackers.com.tw | Travel |
| **BabyHome** | babyhome.com.tw | Parenting |
| **Facebook Groups** | facebook.com | Community-specific, local groups |

---

# SEARCH METHODS

## Method 1: Brave Site Search (Recommended)

Use `web_search` with `site:` operator:

```
site:ptt.cc [關鍵字]
site:dcard.tw [關鍵字]
site:mobile01.com [關鍵字]
site:forum.gamer.com.tw [關鍵字]
```

### Advanced Operators

| Operator | Example | Effect |
|----------|---------|--------|
| `site:` | `site:ptt.cc` | Limit to domain |
| `""` | `"台積電 面試"` | Exact phrase |
| `OR` | `面試 OR 心得` | Either term |
| `-` | `手機 -iPhone` | Exclude term |
| `intitle:` | `intitle:開箱` | Term in title |

### Narrowing by Board/Forum

```
# PTT specific board
site:ptt.cc/bbs/Tech_Job [關鍵字]
site:ptt.cc/bbs/Stock [關鍵字]
site:ptt.cc/bbs/Gossiping [關鍵字]

# Dcard specific forum
site:dcard.tw/f/job [關鍵字]
site:dcard.tw/f/softwareengineer [關鍵字]
site:dcard.tw/f/relationship [關鍵字]

# Mobile01 (use forum name in search)
site:mobile01.com Samsung [關鍵字]
site:mobile01.com 汽車 [關鍵字]
```

## Method 2: Direct Fetch

Use `web_fetch` for latest posts (bypasses search indexing delay):

### PTT
```
https://www.ptt.cc/bbs/{BoardName}/index.html
```
**⚠️ Gossiping/Sex boards require 18+ cookie — use site search instead**

### Mobile01
```
https://www.mobile01.com/topiclist.php?f={forum_id}
```

### 巴哈姆特
```
https://forum.gamer.com.tw/B.php?bsn={game_id}
```

## Method 3: Google Site Search (Backup)

If Brave doesn't find enough:
```
site:ptt.cc [關鍵字] (use regular Google)
```

---

# SEARCH PATTERNS BY USE CASE

## 求職 / Career Research

### Company Research
```
# Interview experiences
site:ptt.cc "[公司名]" 面試
site:dcard.tw "[公司名]" 面試心得

# Salary
site:ptt.cc "[公司名]" 年薪 OR 薪水 OR package
site:ptt.cc/bbs/Tech_Job "[公司名]" offer

# Work culture
site:ptt.cc "[公司名]" 加班 OR 爆肝 OR WLB
site:dcard.tw "[公司名]" 工作環境

# Red flags
site:ptt.cc "[公司名]" 雷 OR 離職 OR 不推
```

### Industry Research
```
# Industry salary
site:ptt.cc/bbs/Salary [產業] 年薪
site:ptt.cc/bbs/Tech_Job [職位] package

# Career path
site:ptt.cc [職位] 職涯 OR 發展 OR 轉職
```

## 產品研究 / Product Research

### Before Buying
```
# Reviews
site:mobile01.com "[產品]" 開箱 OR 心得 OR 評測

# Comparisons
site:mobile01.com "[產品A]" "[產品B]" 比較 OR vs

# Problems
site:mobile01.com "[產品]" 災情 OR 問題 OR 故障
site:ptt.cc "[產品]" 雷 OR 不推

# Recommendations
site:ptt.cc "[產品類型]" 推薦 OR 請益
site:mobile01.com "[產品類型]" 推薦 2024
```

### Specific Categories
```
# Phones
site:mobile01.com OR site:eprice.com.tw "[手機型號]"
site:ptt.cc/bbs/MobileComm "[手機型號]"

# Cars
site:mobile01.com/topiclist.php?f=37 "[車款]"
site:ptt.cc/bbs/car "[車款]"

# Computers
site:ptt.cc/bbs/PC_Shopping "[配備]" 菜單
site:mobile01.com 電腦 "[零件]"
```

## 美食 / Food

```
# Restaurant reviews
site:dcard.tw/f/food "[餐廳名]"
site:google.com/maps "[餐廳名]" (for Google reviews)

# Area recommendations
site:ptt.cc "[地區]" 美食 推薦
site:dcard.tw "[地區]" 必吃

# Specific food
site:ptt.cc "[食物]" 推薦 哪裡
```

## 時事 / Current Events

```
# Breaking news sentiment
site:ptt.cc "[事件關鍵字]"
site:ptt.cc/bbs/Gossiping "[事件]"

# Political discussion
site:ptt.cc/bbs/HatePolitics "[議題]"

# Fact-checking
site:ptt.cc "[傳言]" 假 OR 闢謠
```

## 遊戲 / Gaming

```
# Game discussions
site:forum.gamer.com.tw "[遊戲名]" 攻略
site:forum.gamer.com.tw "[遊戲名]" 心得 OR 評價

# Should I buy?
site:forum.gamer.com.tw "[遊戲名]" 值得 OR 推薦 OR 勸退
site:ptt.cc/bbs/C_Chat "[遊戲名]"
```

## 旅遊 / Travel

```
# Destination research
site:backpackers.com.tw "[地點]" 行程
site:ptt.cc/bbs/Japan_Travel "[地點]"
site:ptt.cc/bbs/Korea_Travel "[地點]"

# Accommodation
site:ptt.cc "[飯店名]" 住宿 心得
```

---

# RESULT INTERPRETATION

## PTT Metrics

| Indicator | Meaning |
|-----------|---------|
| **推** | Upvote, agreement |
| **噓** | Downvote, disagreement |
| **→** | Neutral comment |
| **爆** | 100+ net pushes, very popular |
| **XX** | Heavily downvoted |
| **M** | Marked by moderator (important) |

### Reading Push/Boo Ratio
```
推 50 / 噓 5  = Strong consensus, trustworthy
推 30 / 噓 30 = Controversial, read both sides
推 5 / 噓 50  = Unpopular opinion or problematic post
```

## Dcard Metrics

| Indicator | Meaning |
|-----------|---------|
| **愛心數** | Likes |
| **留言數** | Comments (engagement) |
| **收藏** | Bookmarks |

## Credibility Assessment

### High Credibility Signals
- ✅ Detailed personal experience with specifics
- ✅ Photos/screenshots included
- ✅ Balanced pros/cons
- ✅ High engagement with substantive discussion
- ✅ Author has posting history
- ✅ Multiple sources confirm

### Low Credibility Signals
- 🚩 Vague claims without details
- 🚩 New account, first post
- 🚩 Sounds like marketing/PR
- 🚩 Too positive without any negatives
- 🚩 Contradicts multiple other sources
- 🚩 Old post (check date!)

### Verification Steps
1. Cross-reference across forums
2. Check post date
3. Read comments for corrections
4. Look for follow-up posts
5. Verify facts with official sources

---

# BOARD/FORUM REFERENCE

## PTT Boards (精選)

| Board | Chinese | Topic | Activity |
|-------|---------|-------|----------|
| Gossiping | 八卦 | General, news, politics | Very high |
| Stock | 股票 | Stock market | High |
| Tech_Job | 科技工作 | Tech industry jobs | High |
| Soft_Job | 軟工 | Software engineering | High |
| Salary | 薪資 | Salary discussions | Medium |
| job | 工作 | General employment | Medium |
| car | 汽車 | Cars | High |
| MobileComm | 手機 | Phones | High |
| PC_Shopping | 電蝦 | Computer hardware | High |
| Japan_Travel | 日旅 | Japan travel | Medium |
| Baseball | 棒球 | Baseball | High |
| NBA | NBA | NBA | High |
| C_Chat | 西洽 | ACG chat | Very high |
| movie | 電影 | Movies | Medium |
| studyabroad | 留學 | Study abroad | Medium |
| HatePolitics | 政黑 | Political discussion | High |

## Dcard Forums (精選)

| Forum | Topic |
|-------|-------|
| trending | 熱門 |
| job | 工作 |
| softwareengineer | 軟體工程師 |
| interview | 面試 |
| salary | 薪資 |
| graduate | 研究所 |
| relationship | 感情 |
| sex | 西斯 |
| food | 美食 |
| mood | 心情 |
| makeup | 美妝 |
| fitness | 健身 |

## Mobile01 Forum IDs

| ID | Topic |
|----|-------|
| 568 | Samsung |
| 566 | HTC |
| 634 | 小米 |
| 588 | Asus |
| 565 | Google Pixel |
| 423 | Android 軟體 |
| 7 | 汽車綜合 |
| 37 | 居家房事 |
| 34 | 相機 |
| 180 | 健康與養生 |

## 巴哈姆特 Popular Games

Search `site:forum.gamer.com.tw [遊戲名]` or browse:
- bsn=36730 (原神)
- bsn=71458 (崩壞：星穹鐵道)
- Find game ID from Bahamut homepage

---

# LIMITATIONS & WORKAROUNDS

| Issue | Workaround |
|-------|------------|
| **PTT 18+ boards blocked** | Use `site:ptt.cc/bbs/Gossiping` search |
| **Dcard Cloudflare block** | Use `site:dcard.tw` search only |
| **Old results** | Add year: `[關鍵字] 2024` |
| **Not enough results** | Try alternate keywords, check other forums |
| **Results in wrong language** | Use Traditional Chinese 繁體中文 |
| **Facebook Groups** | Must have account; use `site:facebook.com/groups [關鍵字]` |

---

# WORKFLOW TEMPLATES

## Template: Company Research (面試前)

```
1. web_search: site:ptt.cc "[公司名]" 面試
2. web_search: site:dcard.tw "[公司名]" 面試心得  
3. web_search: site:ptt.cc "[公司名]" 薪水 年終
4. web_search: site:ptt.cc "[公司名]" 加班 OR 離職
5. Synthesize: pros, cons, red flags, salary range
6. Ask user if they want deeper dive on any aspect
```

## Template: Product Purchase

```
1. web_search: site:mobile01.com "[產品]" 開箱
2. web_search: site:mobile01.com "[產品]" 災情 問題
3. web_search: site:ptt.cc "[產品]" 推薦 OR 雷
4. Compare: if alternatives, search those too
5. Summarize: verdict, known issues, recommendations
```

## Template: Breaking News Context

```
1. web_search: site:ptt.cc "[事件關鍵字]" 
2. web_fetch: PTT relevant board for latest
3. web_search: site:dcard.tw "[事件]" (younger demographic view)
4. Cross-reference: official news sources
5. Summarize: public sentiment, key debates, misinformation
```

## Template: Restaurant/Food

```
1. web_search: site:dcard.tw/f/food "[餐廳]"
2. web_search: site:ptt.cc "[餐廳]" 推薦 OR 雷
3. Check: Google Maps reviews (web_fetch)
4. Summarize: worth going, what to order, avoid
```

---

# TIPS

1. **Use Traditional Chinese** — 繁體中文 gets better results
2. **Check dates** — Forum content ages; 2020 info may be outdated
3. **Read comments** — Often more valuable than original post
4. **Cross-reference** — One source isn't enough
5. **Understand context** — PTT skews male/tech; Dcard skews young/female
6. **Verify critical info** — Forums are opinions, not facts

---

*台灣在地搜尋 🇹🇼*
