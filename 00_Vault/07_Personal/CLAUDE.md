# Personal Correspondence (个人通信)

Letters, family correspondence, and lawyer meeting notes.

---

## Folder Structure

> See `~/Documents/00_Vault/README.md` for actual entity folder names.

| Folder | Contents |
|--------|----------|
| `{Owner}/` | Letters sent by or received by the owner |
| `{Family_Member}/` | Letters written by family member (originals) |

---

## Naming Convention

`YYYY-MM-DD_Letter_{Entity}_description_{suffix}.ext`

| Suffix | Format | Purpose |
|--------|--------|---------|
| `_source` | `.md` | Searchable text (grep-friendly) |
| `_sent` | `.pdf` | Immutable artifact (exact appearance) |
| `_received` | `.pdf` | Scanned/received original |

---

## Filing Rules

> See `~/Documents/00_Vault/README.md` for actual entity routing.

1. **Letters FROM owner** → `{Owner}/`
2. **Letters TO owner** (received) → `{Owner}/`
3. **Lawyer meeting notes** (口信) → `{Owner}/`
4. Always create `_source.md` first; PDF generated later if needed
5. **Linkage required**: update related project +
   `20_Areas/00_Meta_System/Vault_Filing_Log.md`

---

## Entity in Filename

Use the **other party's** name as Entity:
- Owner writes to Family Member → `_Letter_{FamilyMember}_`
- Family Member writes to Owner → `_Letter_{FamilyMember}_`
  (Entity = the correspondent, not the folder owner)

---

## Related Protocols

- **Dual-File Archival (root CLAUDE.md S7):** PDF `_sent` + MD `_source`
  pairs for letters that may serve as evidence.
- **Vault-to-Project Linkage (root CLAUDE.md S8):** After filing,
  search `10_Projects/` for related cases and update `00_PLAN.md`.
- **Filing Log:** Record every filing in
  `20_Areas/00_Meta_System/Vault_Filing_Log.md`.
