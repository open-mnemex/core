# Digital Life System: The PhD Architecture

---

Critial: Only use pdf-analyzer agent to read PDF
Critial: Only use pdf-analyzer agent to read PDF
Critial: Only use pdf-analyzer agent to read PDF

Critical: Python 必须使用 `uv run --with <package>` 执行，禁止使用系统 Python
Critical: Python 必须使用 `uv run --with <package>` 执行，禁止使用系统 Python
Critical: Python 必须使用 `uv run --with <package>` 执行，禁止使用系统 Python

```bash
# 正确示例
uv run --with pandas --with numpy script.py
uv run --with requests -c "import requests; print(requests.get('...'))"

# 错误示例 - 禁止！
python script.py
pip install pandas
```


## Style Guide

### 0. Language-Aware Naming

- **Filename language must match the document's primary language.**
  Date prefixes and type tags (e.g. `Contract`, `Receipt`) stay in
  English; the descriptive portion follows the document's language.
  Filing Log descriptions follow the same rule.
- Example: `2026-02-06_Contract_Vendor_服务协议.pdf`

### 1. Line Length & Line Structure

- **Soft limit:** Keep source lines **<= 98 characters**.
- **One sentence per line** (for English text):

```text
This is the first sentence.
This is the second sentence.
This is the third sentence, which is a bit longer.
```

---

## System Philosophy (系统哲学)

### Separation of Fact and Fiction (事实与创造分离)

- **Facts (`00_Vault`):** Immutable, single source of truth (SSOT).
  Example: Diplomas, Tax Returns.
- **Creation (`10_Projects`):** Volatile, iterative work.
  Example: Drafts, Code, LaTeX builds.

### Capability vs. Collection (能力与收藏分离)

- **Capability (`20_Areas`):** Your skills, knowledge, and systems you
  actively maintain.
- **Collection (`30_Resources`):** External materials you've gathered
  for reference.

### Flow (流动性)

1. Files enter via `~/Downloads`.
2. Active work happens in `Projects`.
3. Final artifacts move to `Vault`.
4. Dead projects move to `Archives`.

---

## 1. Global Architecture (全局架构)

The root directory (`~/Documents`) consists of 6 top-level domains:

```text
~/Downloads             # [The Inbox] Entry point for all new files.
~/Documents
├── 00_Vault              # [The Museum] Immutable facts. SSOT.
├── 10_Projects           # [The Workshop] Active tasks with deadlines.
├── 20_Areas              # [The Skill Tree] Capabilities & systems.
├── 30_Resources          # [The Library] External collected materials.
└── 99_Archives           # [The Cold Storage] Completed projects.
```

---

## 2. Document Index (文档导航)

| Document | Location | Content |
|----------|----------|---------|
| Architecture Overview | `20_Areas/00_Meta_System/Architecture_Overview.md` | Human-readable system map |
| Vault Guide | `00_Vault/CLAUDE.md` | VNS naming, structure, philosophy |
| Legal Protocol | `00_Vault/04_Legal/CLAUDE.md` | Path rules, entity naming |
| Personal Letters | `00_Vault/07_Personal/CLAUDE.md` | Letter naming, dual-file |
| Projects Guide | `10_Projects/CLAUDE.md` | Naming, skeleton, lifecycle |
| Areas Guide | `20_Areas/CLAUDE.md` | Areas philosophy & guidelines |
| Resources Guide | `30_Resources/CLAUDE.md` | Capture types, folders |
| Archives Guide | `99_Archives/CLAUDE.md` | 3R Protocol, retrieval |
| Inbox Processing | `20_Areas/00_Meta_System/SOP_01_Inbox_Processing.md` | Filing workflow |
| Project Closeout | `20_Areas/00_Meta_System/SOP_02_Project_Closeout.md` | 3R methodology |
| Backup & Restore | `20_Areas/00_Meta_System/SOP_03_Backup_Restore.md` | Recovery procedures |
| Project Init | `20_Areas/00_Meta_System/SOP_04_Project_Initialization.md` | Genesis Protocol |
| Filing Log | `20_Areas/00_Meta_System/Vault_Filing_Log.md` | Complete filing history |
| Category Vocab | `20_Areas/00_Meta_System/Reference_Project_Category_Controlled_Vocabulary.md` | 7 Pillars |
| Capture Registry | `30_Resources/_capture_registry.md` | `/capture` definitions |

---

## 3. The Core: 00_Vault (核心：事实库)

Immutable facts with strict VNS naming.
**Full guide:** `00_Vault/CLAUDE.md` (structure, naming, vocabulary).

---

## 4. Working Directories Guidelines (工作区指南)

### 10_Projects (项目)

**Definition:** Active efforts with a deadline.

**Structure:** `YYYY_Category_SubType_Entity_Description`

**Active Projects:** See `10_Projects/README.md` for current inventory.

**Vault Connection:** Use Symlinks to reference evidence files from
`00_Vault`.

### 20_Areas (领域)

**Definition:** Your capabilities and systems. Living documents you
actively maintain.
**Key Question:** 「這是我的能力/技能嗎？」
**Full guide:** `20_Areas/CLAUDE.md`

### 30_Resources (资源)

**Definition:** External materials you've collected. Read-only library.
**Key Question:** 「這是外部收藏品嗎？」
**Full guide:** `30_Resources/CLAUDE.md`

### 99_Archives (档案馆)

**Definition:** Completed projects and inactive areas.
**Action:** Move `10_Projects` folders here once finished.
**Full guide:** `99_Archives/CLAUDE.md`

### Documentation Maintenance (文档维护)

> **Note:** When creating new top-level subfolders in any domain,
> update the corresponding domain `CLAUDE.md` to keep documentation
> current.

---

## 5. Environment Variables (环境变量)

API keys are stored in `~/Documents/.env`.
Before running skills that need API keys, source it:

```bash
set -a && source ~/Documents/.env && set +a
```

| Variable         | Used by              |
|------------------|----------------------|
| `GEMINI_API_KEY` | nano-banana-pro skill |

---

## 6. Security & Automation Protocol

- **No PII in CLAUDE.md:** CLAUDE.md files are checked into version
  control. Never include personal information (names, addresses,
  ID numbers, phone numbers, account numbers) in any CLAUDE.md.
  Use generic placeholders in examples instead.

- **Backup Strategy:** Time Machine + iCloud (no Git tracking in
  Documents). See `20_Areas/00_Meta_System/SOP_03_Backup_Restore.md`.
- **Identity Protection:** Treat folders as if they belong to a client.
  No "Family" labels.
- **Access Control:** `00_Vault` should reside in an encrypted volume
  if possible.
- **Symlink Usage:** Use `ln -s` to reference Vault files in Projects.
- **No Deletion Policy:** Scripts must NEVER `rm` files from Inbox.
  Move to `__To_Review` instead.
- **CRITICAL - No Destructive Commands:**
  - NEVER use `rm -rf` on any folder containing user files.
  - NEVER use `rm` to delete files. Always move to Trash instead.
  - To move files to Trash, use: `mv <file> ~/.Trash/`
  - When reorganizing files, use `cp` first, verify, then trash
    original.
  - This rule exists because `rm` bypasses Time Machine recovery.
  - **Incident:** Trip files were permanently lost due to `rm -rf`.

---

## 7. Special Protocol: Legal Cases (04_Legal)

**Full guide:** `00_Vault/04_Legal/CLAUDE.md`
(path rules, matter types, entity naming, legal VNS categories).

---

## 8. Special Protocol: Dual-File Archival (双文件归档法)

**Purpose:** For documents that are both "historical facts" (immutable)
and need to be searchable/reusable (grep-friendly), use the dual-file
approach.

**When to Apply:**

- Personal correspondence with legal context (family letters during
  litigation)
- Important communications that may serve as evidence
- Any document where both "exact appearance" and "text searchability"
  matter

**File Pair:**

| Suffix    | Format | Role                          | Use Case                |
|-----------|--------|-------------------------------|-------------------------|
| `_sent`   | PDF    | **Artifact / Evidence**       | Immutable snapshot      |
| `_source` | MD     | **Data / Searchable Text**    | grep-friendly, reusable |

**Naming Rule:** Keep prefixes identical so files sort together.

```text
YYYY-MM-DD_Letter_{Entity}_description_sent.pdf
YYYY-MM-DD_Letter_{Entity}_description_source.md
```

**Generation Command:**

```bash
pandoc input.md -o output.pdf --pdf-engine=xelatex \
  -V mainfont="PingFang SC" -V geometry:margin=1in
```

**Image Handling:**

- PDF: Images are "burned in" — no broken links.
- Markdown: Keep text only. If images are critical, archive them
  separately in `02_Assets/` or `30_Resources/`.

**Philosophy:**

- PDF = "The letter itself" (what was actually sent/received)
- Markdown = "The digital draft" (for future text search and
  copy-paste)

---

## 9. Vault-to-Project Linkage (保险库项目联动)

**Purpose:** When a file is saved to Vault, automatically find and
update related active projects via **dynamic search** (no static
mapping table).

### A. Dynamic Search Method

When filing to Vault, extract identifiers and search `10_Projects/`:

```bash
# Search for matching projects
grep -rl "IDENTIFIER" ~/Documents/10_Projects/ --include="*.md" \
  2>/dev/null
```

**Identifiers to extract:**
- Claim/Case numbers (e.g., `#12345678`, `25XXXX01234`)
- Entity names (match `01_Identity/*/` folder names)
- Vendor/Company names (e.g., `Chase`, `Acme`, `StateU`)

### B. Linkage Actions

1. **If match found:** Update the matched project's `00_PLAN.md`:
   - **Section 5 (项目结构):** Add file to reference list with
     Vault symlink
   - **Section 8 (Log & Next Actions):** Add dated entry for
     the filing
2. **If no match:** Just file to Vault, record "(no active project)"
   in Section 9

> **Important:** Filing is incomplete until BOTH
> `20_Areas/00_Meta_System/Vault_Filing_Log.md` AND the linked
> project's `00_PLAN.md` are updated.
> This is a bidirectional relationship.

### C. Identifier Patterns (for extraction)

| Type         | Regex / Pattern                    | Example          |
|--------------|------------------------------------|------------------|
| Case Number  | `\d{2}[A-Z]{2,4}\d{5}`             | `25XXXX01234`    |
| Claim Number | `#?\d{6,10}`                       | `#12345678`      |
| Form Code    | `[A-Z]{1,3}-\d{2,4}[A-Z]?`         | `SC-120`, `I-797`|
| Entity Name  | Match `01_Identity/*/` folder names | `Last_First`    |

---

## 10. Vault Filing Log (归档记录)

All vault filings are recorded in
`20_Areas/00_Meta_System/Vault_Filing_Log.md`.

---
