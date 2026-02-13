# Articles (文章收藏)

This folder stores captured articles with full original text.

---

## Naming Convention

`YYYY-MM-DD_title_in_snake_case.md`

- Date: Capture date (not publication date)
- Title: Lowercase, underscores, no special characters

---

## Required Fields (Obsidian YAML Frontmatter)

```yaml
---
title: "Article Title"
subtitle: "Subtitle if available"
source: "https://original-url.com"
author: "Author Name"
published: YYYY-MM-DD
captured: YYYY-MM-DD
tags:
  - article
  - topic1
  - topic2
---
```

| Field       | Required | Description                              |
|-------------|----------|------------------------------------------|
| `title`     | Yes      | Original article title                   |
| `subtitle`  | No       | Subtitle or tagline                      |
| `source`    | Yes      | Original URL                             |
| `author`    | Yes      | Author name                              |
| `published` | Yes      | Publication date (YYYY-MM-DD)            |
| `captured`  | Yes      | Date saved to system (YYYY-MM-DD)        |
| `tags`      | No       | Obsidian tags for search/filtering       |

---

## Content Structure

```markdown
---
title: "How to Gain New Skills"
subtitle: "Give yourself a gift this holiday season..."
source: "https://..."
author: "Andrew Ng"
published: 2025-12-26
captured: 2025-12-31
tags:
  - article
  - AI
  - learning
---

# Article Title

*Subtitle here (if available)*

---

[Full original article text with all links preserved]
```

---

## Guidelines

1. **Preserve original text** — Do not summarize unless user requests
2. **Keep all hyperlinks** — Inline links as `[text](url)`
3. **Use YAML frontmatter** — For Obsidian compatibility
4. **One sentence per line** — For better diffs and readability
5. **Line width <= 80 chars** — Per system style guide
