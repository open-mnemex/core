# Digital Life System: Architecture Overview

A personal information architecture built on progressive disclosure.
This document is the human-readable entry point to the entire system.

---

## System at a Glance

| Domain | Metaphor | Purpose | Mutability |
|--------|----------|---------|------------|
| `00_Vault` | The Museum | Immutable facts, SSOT | Read-only |
| `10_Projects` | The Workshop | Active tasks with deadlines | Read-write |
| `20_Areas` | The Skill Tree | Capabilities & living systems | Evolving |
| `30_Resources` | The Library | External collected materials | Read-only |
| `99_Archives` | Cold Storage | Completed projects | Frozen |

**Inbox:** `~/Downloads` — entry point for all new files.

---

## Core Philosophies

1. **Fact vs. Fiction:** Facts live in `00_Vault` (immutable).
   Creative/iterative work lives in `10_Projects` (volatile).
2. **Capability vs. Collection:** Your skills go in `20_Areas`.
   External materials go in `30_Resources`.
3. **Flow:** Downloads → Projects → Vault → Archives.

---

## Where to Find Things

| I need to... | Go to |
|--------------|-------|
| Find an official document (receipt, contract, ID) | `00_Vault/` |
| Work on something with a deadline | `10_Projects/` |
| Check my skills, configs, or systems | `20_Areas/` |
| Look up a saved article, book, or quote | `30_Resources/` |
| Dig up a finished project | `99_Archives/` |
| Understand system rules | `20_Areas/00_Meta_System/` |
| Process new files | `~/Downloads` → `/process-inbox` |

---

## Document Index

### Layer 0 — Orientation

| File | Role |
|------|------|
| `CLAUDE.md` (root) | Agent instructions + operational state |
| This file | Human-readable system map |

### Layer 1 — Domain Guides

| File | Domain |
|------|--------|
| `00_Vault/CLAUDE.md` | Vault philosophy, VNS naming, structure |
| `10_Projects/CLAUDE.md` | Project naming, skeleton, lifecycle |
| `20_Areas/CLAUDE.md` | Active areas inventory |
| `30_Resources/CLAUDE.md` | Capture types, folder structure |
| `99_Archives/CLAUDE.md` | 3R Protocol, retrieval rules |

### Layer 2 — Subdomain Guides

| File | Scope |
|------|-------|
| `00_Vault/04_Legal/CLAUDE.md` | Legal path rules, entity naming |
| `00_Vault/07_Personal/CLAUDE.md` | Letter naming, dual-file protocol |
| `20_Areas/macOS_Automation/CLAUDE.md` | AppleScript conventions |
| `20_Areas/Finance_Planning/CLAUDE.md` | Financial tracking rules |
| `30_Resources/Lists/CLAUDE.md` | List capture templates |
| `30_Resources/Articles/CLAUDE.md` | Article capture format |
| `30_Resources/Quotes/CLAUDE.md` | Quote capture format |
| `30_Resources/Concepts/CLAUDE.md` | Concept capture format |

### Layer 3 — Full Specifications

| File | Content |
|------|---------|
| `30_Resources/_capture_registry.md` | All `/capture` type definitions |
| `20_Areas/00_Meta_System/SOP_01_Inbox_Processing.md` | Inbox → system workflow |
| `20_Areas/00_Meta_System/SOP_02_Project_Closeout.md` | 3R closeout methodology |
| `20_Areas/00_Meta_System/SOP_03_Backup_Restore.md` | Backup & recovery |
| `20_Areas/00_Meta_System/SOP_04_Project_Initialization.md` | Genesis Protocol |
| `20_Areas/00_Meta_System/Vault_Filing_Log.md` | Complete filing history |
| `20_Areas/00_Meta_System/Reference_*.md` | Controlled vocabularies |
| `20_Areas/00_Meta_System/Style_*.md` | Style guides |

---

## Progressive Disclosure Pattern

```
Root CLAUDE.md         → "What rules does the agent follow?"
Domain CLAUDE.md       → "How does this folder work?"
Subdomain CLAUDE.md    → "What are the specific conventions here?"
SOPs / Registries      → "Give me the full specification."
```

Each layer links down to more detail, and up to its parent.
Agents load only the layers they need for the current task.
