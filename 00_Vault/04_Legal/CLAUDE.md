# Legal Cases (法务文件)

Rights, obligations, and legal proceedings.

---

## Path Rules

`/00_Vault/04_Legal/<MatterType>/<Entity>/`

---

## MatterType

| MatterType | Description |
|------------|-------------|
| `Immigration` | I-20, H1B, Green Card, Change of Status |
| `Litigation` | Active lawsuits, court filings |
| `Incidents` | One-off incidents (police reports, accidents) |
| `Housing` | Tenant/landlord issues |
| `Contracts` | Leases, agreements, service contracts |

---

## Entity Naming

> See `~/Documents/00_Vault/README.md` for actual entity folder names.

- **Person:** `Last_First` (legal name, PascalCase)
- **Case (Joint):** `Case_<CaseNumber>_<ShortName>`

Use case-based entity for complex multi-party litigation.
Use person-based entity for individual matters.

---

## Legal-Specific VNS Categories

| Category | Usage |
|----------|-------|
| `Contract` | Signed agreements |
| `Notice` | Court/government notices |
| `Affidavit` | Sworn statements |
| `Evidence` | Supporting documentation |
| `Correspondence` | Letters between parties |
| `Letter` | Formal letters (sent/received) |
| `Response` | Replies to notices or filings |
| `Application` | Petitions, motions, filings |
| `Record` | Transcripts, logs, meeting notes |

---

## Example Structure

```text
04_Legal/
├── Immigration/
│   └── {Person}/
│       └── YYYY-MM-DD_Application_USCIS_description.pdf
├── Litigation/
│   ├── {Person}/
│   │   └── YYYY-MM-DD_Contract_{Firm}_description.pdf
│   └── Case_{Number}_{ShortName}/
│       ├── YYYY-MM-DD_Notice_Court_description.pdf
│       └── YYYY-MM-DD_Notice_{Issuer}_description.pdf
└── Contracts/
    └── YYYY-MM-DD_Contract_{Entity}_description.pdf
```

---

## General VNS Rules

See parent: `00_Vault/CLAUDE.md` for full naming convention
and controlled vocabulary.
