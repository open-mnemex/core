# Capture Registry (内容捕获注册表)

This file defines all content types the `/capture` command can handle.
To add a new type, simply add a new section following the template below.

> **Progressive Disclosure:** This registry is the single source of truth
> for all capture types. The `/capture` SKILL.md only has a quick-reference
> table. Each destination folder has its own `CLAUDE.md` with local rules.

---

# Vault Types (00_Vault)

These types create immutable records. They trigger project linkage updates.

---

## letter

**Keywords:** letter, 信, 家书, 口信, correspondence, 通信, 会见
**Destination:** `00_Vault/07_Personal/{folder}/`
**Mode:** new_file
**Naming:** `YYYY-MM-DD_Letter_{Recipient}_description_source.md`
**Linkage:** Yes — search `10_Projects/` + append to `Vault_Filing_Log.md`
**Folder Logic:**
See `~/Documents/00_Vault/README.md` for actual entity folder names
and letter routing rules.
**Template:**
~~~markdown
# {寄件人}致{收件人}{方式}

**日期：** YYYY-MM-DD
**寄件人：** [Name]
**收件人：** [Name]
**方式：** [书信 / 律师会见口信 / 电话记录]

---

[Full content, preserving original wording]
~~~
**Notes:**
- Follow Dual-File Archival (Section 7 of CLAUDE.md):
  `_source.md` = searchable text, `_sent.pdf` = artifact
- If conveyed via lawyer, note the lawyer's name and date
- Preserve exact wording — do not summarize or edit

---

## legal_note

**Keywords:** 法律, legal, 备忘, memo, 记录, 笔记
**Destination:** `00_Vault/07_Personal/{Owner}/`
**Mode:** new_file
**Naming:** `YYYY-MM-DD_Record_{Entity}_description_source.md`
**Linkage:** Yes
**Template:**
~~~markdown
# [Title]

**日期：** YYYY-MM-DD
**来源：** [Lawyer / Court / Self]
**关联案件：** [Case number if applicable]

---

[Content]
~~~

---

# Areas Types (20_Areas)

These types update living reference documents. No linkage needed.

---

## account

**Keywords:** account, 账号, 银行, bank, 卡号, 户名
**Destination:** `20_Areas/Finance_Planning/accounts_registry.md`
**Mode:** append
**Template:**
~~~markdown

### [银行名] — [支行名]
- 户名: [Name]
- 账号: [Number]
- 用途: [Purpose]
~~~
**Notes:**
- Group by person, then by bank
- If person section doesn't exist, create it with `## [Name]`

---

# Resources Types (30_Resources)

These types collect external materials. No linkage needed.

---

## quote

**Keywords:** quote, wisdom, 语录, 名言
**Destination:** `30_Resources/Quotes/Quotes.md`
**Mode:** append
**Search:** Always search English first for original source
**Template:**
~~~markdown
---

## [Topic]

> [Original text, English preferred, line width <= 80 chars]
>
> —— **[Author]**, [Title/Credentials]
>
> Source: [Link](URL) (Date)

**中文概括：** [Summary if screenshot was in Chinese]
~~~

---

## book

**Keywords:** book, 书, reading, 阅读
**Destination:** `30_Resources/Lists/Reading_List.md`
**Mode:** append
**Template:**
~~~markdown
- [ ] **[Title]** by [Author] — [Brief reason/note]
  - Recommended by: [Source/Person]
  - Link: [URL if available]
~~~

---

## show

**Keywords:** show, movie, tv, 电视剧, 电影, watch
**Destination:** `30_Resources/Lists/Watch_List.md`
**Mode:** append
**Template:**
~~~markdown
- [ ] **[Title]** ([Year]) — [Platform: Netflix/HBO/etc]
  - [Brief note: why interested, who recommended]
  - Watch: [Link title](URL) — YouTube/official link if available
~~~
**Notes:**
- Always search for YouTube or official streaming link
- If specific episode/clip mentioned, link to that clip

---

## article

**Keywords:** article, 文章, blog, post
**Destination:** `30_Resources/Articles/`
**Mode:** new_file (YYYY-MM-DD_title.md)
**Template:**
~~~markdown
# [Article Title]

**Source:** [URL]
**Author:** [Name]
**Captured:** YYYY-MM-DD

---

## 原文 (Original Text)

[Full original text of the article, preserving all paragraphs]

---

## Key Takeaways

- [Point 1]
- [Point 2]
~~~
**Notes:**
- ALWAYS preserve the full original text — do NOT just summarize
- Original wording is the primary value; takeaways are supplementary
- Line width <= 80 chars for readability

---

## tool

**Keywords:** tool, app, software, 工具, 软件
**Destination:** `30_Resources/Lists/Tools.md`
**Mode:** append
**Template:**
~~~markdown
- **[Tool Name]** — [One-line description]
  - URL: [Link]
  - Why: [Reason for interest]
~~~

---

## music

**Keywords:** music, song, album, podcast, 音乐, 播客
**Destination:** `30_Resources/Lists/Music_Podcasts.md`
**Mode:** append
**Template:**
~~~markdown
- [ ] **[Title]** by [Artist/Host]
  - Platform: [Spotify/Apple Music/etc]
  - Note: [Why interested]
~~~

---

## course

**Keywords:** course, tutorial, 课程, 教程, learn
**Destination:** `30_Resources/Lists/Courses.md`
**Mode:** append
**Template:**
~~~markdown
- [ ] **[Course Name]** — [Platform: Coursera/Udemy/etc]
  - Instructor: [Name]
  - Topic: [Subject area]
  - Note: [Why interested]
~~~

---

## travel

**Keywords:** travel, destination, place, visit, 旅行, 景点, 打卡, architecture
**Destination:** `30_Resources/Lists/Travel_List.md`
**Mode:** append
**Template:**
~~~markdown
- [ ] **[Place Name]** — [City/Region, Country]
  - Type: [Architecture / Nature / Museum / Food / etc.]
  - Why: [reason for interest]
  - Official: [website if available]
  - Map: [Google Maps link]
  - Tips: [best time to visit, tickets, etc.]
~~~

---

## wishlist

**Keywords:** wishlist, shopping, buy, 购物, 想买, 种草, EDC
**Destination:** `30_Resources/Lists/Wishlist.md`
**Mode:** append
**Template:**
~~~markdown
- [ ] **[Product Name]** — [Brand/Type]
  - Price: $XX (as of YYYY-MM-DD)
  - Why: [reason for interest]
  - Official: [product page URL]
  - Amazon: [amazon link]
~~~
**Notes:**
- Always include TWO links: official product page + Amazon
- Always include price WITH date (prices change over time)

---

## puzzle

**Keywords:** puzzle, riddle, brain teaser, 谜题, 逻辑题, 智力题
**Destination:** `30_Resources/Lists/Puzzles.md`
**Mode:** append
**Template:**
~~~markdown
---

## [Puzzle Name]

**Type:** [Logic / Math / Lateral Thinking / etc.]

**Problem:**
[Description of the puzzle]

**Solution:**
[The answer and reasoning]

**Key Insight:** [The "aha" moment or core principle]
~~~

---

## concept

**Keywords:** concept, definition, 概念, 术语, term, framework
**Destination:** `30_Resources/Concepts/`
**Mode:** new_file (concept_name.md)
**Template:**
~~~markdown
# [Concept Name]

**Origin:** [Who coined it / Where it came from]
**Domain:** [Business / Tech / AI / Finance / etc.]

---

## Definition

[Clear, concise definition - 2-3 sentences]

## Core Principle

[The key insight or mechanism]

## Real-World Examples

- **[Company/Case]:** [How they apply it]

## Key Takeaways

- [Point 1]
- [Point 2]

---

**Sources:**
- [Link 1](URL)
- [Link 2](URL)

**中文概括：** [Chinese summary if applicable]
~~~

---

## How to Add New Types

1. Add a new section with `## type_name`
2. Define: Keywords, Destination, Mode, Template
3. The `/capture` command will automatically recognize it

**Example - Adding "recipe" type:**

```markdown
## recipe

**Keywords:** recipe, 食谱, cooking, 菜谱
**Destination:** `30_Resources/Recipes.md`
**Mode:** append
**Template:**
~~~markdown
- **[Dish Name]** — [Cuisine]
  - Source: [URL]
  - Note: [Why save]
~~~
```
