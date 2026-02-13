# Projects (项目工作区)

Active efforts with a deadline.
Once finished, move to `99_Archives/`.

---

## Naming Format

`YYYY_Category_SubType_Entity_Description`

**Category Vocabulary:** See
`20_Areas/00_Meta_System/Reference_Project_Category_Controlled_Vocabulary.md`

Quick reference:

| Category | Trigger |
|----------|---------|
| `Legal` | Law, contracts, immigration |
| `Asset` | Buy/sell/maintain valuables |
| `Admin` | Forms, compliance, bureaucracy |
| `Research` | Papers, experiments, discovery |
| `Dev` | Code, systems, engineering |
| `Academic` | Courses with grades |
| `Event` | Travel, conferences, gatherings |
| `Course` | Variant of Academic (university courses) |
| `Litigation` | Variant of Legal (active lawsuits) |

---

## Project Skeleton

Every project MUST have this structure:

```text
Project_Root/
├── 00_PLAN.md           # [Control Center] Project brain
├── 01_Input/            # [ReadOnly] Reference materials
├── 02_Drafts/           # [Workbench] WIP files
├── 03_Output/           # [Showroom] Final deliverables only
└── 99_Admin/            # [Paperwork] Receipts, contracts
```

See `20_Areas/00_Meta_System/SOP_04_Project_Initialization.md` for the
full Genesis Protocol including the `00_PLAN.md` seed template.

---

## Vault Connection

Use **symlinks** (`ln -s`) to reference evidence files from `00_Vault`.
Never copy Vault files into Projects.

---

## Lifecycle

1. **Init:** Follow SOP_04 (Genesis Protocol)
2. **Active:** Work in `02_Drafts/`, deliver to `03_Output/`
3. **Close:** Follow SOP_02 (3R Protocol: Refine, Reduce, Record)
4. **Archive:** Move entire folder to `99_Archives/`

---

## Active Projects Table

The active projects table is maintained in `README.md`
(in this folder). Skills read it on demand for project context.
