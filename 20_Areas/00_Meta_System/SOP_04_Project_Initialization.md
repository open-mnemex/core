# SOP 04: The Genesis Protocol (Project Initialization)
**Philosophy:** A project well-defined is half-done. Never start with an empty folder.

-----

## 1\. The Decision Gate (决策门)

Before creating a folder, ask:

  - [ ] **Is it Finite?** Does it have a clear end state? (If "No" -\> It belongs in `20_Areas`)
  - [ ] **Is it Complex?** Does it require multiple files/steps? (If "No" -\> Just do it or put in a temporary list)
  - [ ] **Is it Worthy?** Does it deserve to occupy mental RAM?

## 2\. Naming & Location (命名与定位)

**Location:** `~/Documents/10_Projects/`
**Format:** `YYYY_Category_ProjectName`

**Category Vocab:**

  - `Admin` (Bureaucracy, logistics)
  - `Sale` (Selling assets)
  - `Claim` (Legal/Insurance claims)
  - `Dev` (Coding, Engineering)
  - `Research` (Academic, Learning)
  - `Creation` (Writing, Design, Video)

*Example:* `2025_Sale_iPhone17`

## 3\. Structural Skeleton (骨架搭建)

Manually create these 5 items. This topology is non-negotiable.

```text
Project_Root/
├── 00_PLAN.md           # [Control Center] The brain of the project.
├── 01_Input/            # [ReadOnly] Reference materials, Client requirements.
├── 02_Drafts/           # [Workbench] WIP files, multiple versions.
├── 03_Output/           # [Showroom] Final deliverables only.
└── 99_Admin/            # [Paperwork] Receipts, Contracts, Screenshots.
```

## 4\. The Context Seed (00\_PLAN.md)

Create `00_PLAN.md` immediately. Paste this seed content:

```markdown
# Project Plan: [Project Name]

**Created:** YYYY-MM-DD
**Status:** Active
**Tags:** #Category

---

## 1. Definition of Done (以终为始)
> Specifically, what does "Success" look like?
> (e.g., Money received in bank, PDF uploaded to portal)

## 2. Deliverables (交付物)
- [ ] Final Output 1:
- [ ] Final Output 2:

## 3. Vault Linkage (事实链接)
> Are there files in 00_Vault needed here? (Use Symlinks `ln -s`)
> Example: Receipt for the item being sold.
-

## 4. Log & Next Actions (日志与行动)
- [ ] Project Structure Initialized @date(today)
```

## 5\. The Linkage Ritual (链接仪式)

**Goal:** Connect Fiction (Project) with Fact (Vault).

1.  Identify necessary "Evidence" from `00_Vault`.
2.  **Do NOT copy.** Use Symlinks (软链接) to `01_Input` or `99_Admin`.
      * *Terminal:* `ln -s ~/Documents/00_Vault/Path/To/File ./01_Input/`
      * *Why:* Keeps `00_Vault` as the Single Source of Truth.

-----

### 立即行动建议

请立刻使用这个 SOP，手动建立刚才讨论的 **“卖掉 iPhone 17”** 项目：

1.  **新建文件夹：** `2025_Sale_iPhone17`
2.  **建立骨架：** `01_Input`, `02_Drafts`, `03_Output`, `99_Admin`。
3.  **创建 `00_PLAN.md`：**
      * **Goal:** 既然是长期主义，你的目标不仅仅是“卖掉”，而是“以最高市场价卖掉，并且**无风险**（数据清除彻底、留存交易证据防止买家欺诈）”。
4.  **建立链接：** 去 `00_Vault` 找到当年买 iPhone 17 的原始发票（如果有的话），做一个软链接到 `99_Admin`。

这就是把简单的“卖东西”变成“资产管理”的过程。