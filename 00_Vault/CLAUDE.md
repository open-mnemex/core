# The Vault (事实库)

Immutable facts. Single Source of Truth. Strict naming (VNS).

---

## Vault Philosophy

- **Immutability:** Files are artifacts. Do not edit them.
- **Identity Neutrality:** Use Legal Names only. No "Dad/Mom".
- **No Root Clutter:** Files MUST be in 2nd-level subfolders.
- **MECE:** Mutually Exclusive, Collectively Exhaustive.
- **SSOT:** Single Source of Truth.
- **Non-Destructive Import:** Never `rm` — move to Trash.

---

## Directory Structure

> Actual folder names: see `README.md`

```text
/00_Vault
├── 01_Identity/          # Passports, IDs, Vital Records (by Name)
│   ├── {person_1}/
│   ├── {person_2}/
│   └── .../
│
├── 02_Assets/            # Ownership proofs
│   ├── Real_Estate/      # Deeds, Titles
│   ├── Vehicles/         # Registration, Titles
│   └── Equipment/        # High-value tech warranties/receipts
│
├── 03_Financial/         # Money flow
│   ├── Tax_Records/      # W2, 1099, Tax Returns
│   ├── Banking/          # Monthly Statements
│   ├── Bills/            # Utility, Telecom, Insurance
│   └── Receipts/         # One-off purchases
│
├── 04_Legal/             # Rights & Obligations
│   ├── Immigration/      # I-20, H1B, Green Card
│   ├── Contracts/        # Leases, Agreements
│   ├── Notices/          # Official notices
│   ├── Litigation/       # Active lawsuits
│   └── Incidents/        # One-off incidents
│
├── 05_Academic/          # Education
│   ├── {university_1}/
│   ├── {university_2}/
│   └── Publications/     # Published Papers
│
├── 06_Medical/           # Health Records
│   ├── {person_1}/
│   └── {person_2}/
│
└── 07_Personal/          # Personal correspondence
    ├── {person_1}/
    └── {person_2}/
```

---

## Naming Convention (VNS)

**Format:** `YYYY-MM-DD_Category_Entity_Description_Status.ext`

**Rules:**

- **No Relationships:** Use Legal Names (`Last_First`), NEVER titles.
- **No Spaces:** Use underscores `_`.
- **Case Logic:** `PascalCase` for Category/Entity;
  `snake_case` for Description.

**Controlled Vocabulary (Category):**

| Domain     | Categories                                             |
|------------|--------------------------------------------------------|
| Identity   | `ID`, `Passport`, `Visa`, `Vital`                      |
| Assets     | `Deed`, `Title`, `Registration`, `Warranty`            |
| Financial  | `Invoice` (Owe), `Receipt` (Paid), `Statement` (Log), |
|            | `TaxForm`                                              |
| Legal      | `Contract`, `Notice`, `Affidavit`, `Evidence`,         |
|            | `Correspondence`, `Letter`, `Response`,                |
|            | `Application`, `Record`                                |
| Medical    | `Report`, `Prescription`, `Record`                     |
| Personal   | `Letter` (Sent/Received), `Diary`, `Note`              |

---

## Subdomain Guides

| Subdomain | CLAUDE.md | Key Rules |
|-----------|-----------|-----------|
| `04_Legal/` | `04_Legal/CLAUDE.md` | Matter-based path rules, entity naming |
| `07_Personal/` | `07_Personal/CLAUDE.md` | Dual-file archival, letter naming |

---

## Related Protocols (in root CLAUDE.md)

- **Section 7 — Dual-File Archival:** PDF `_sent` + MD `_source` pairs.
- **Section 8 — Vault-to-Project Linkage:** Dynamic search + bidirectional
  updates when filing to Vault.
- **Filing Log:** `20_Areas/00_Meta_System/Vault_Filing_Log.md`
