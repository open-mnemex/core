# SOP 01: Inbox Processing (收件箱处理)

**Philosophy:** Files enter through one gate and are routed
to their permanent home. Nothing lives in Downloads forever.

---

## Decision Tree

For each file in `~/Downloads`, ask:

```
Is this an immutable fact (receipt, ID, contract)?
  └─ YES → 00_Vault (follow VNS naming)

Is this related to an active project?
  └─ YES → 10_Projects/<project>/01_Input/ or 99_Admin/

Is this my own knowledge, config, or system doc?
  └─ YES → 20_Areas/<area>/

Is this external reference material?
  └─ YES → 30_Resources/<type>/

None of the above?
  └─ Move to __To_Review/ for later triage
```

---

## Filing Checklist

For each file routed to a destination:

- [ ] **Rename** using VNS format:
      `YYYY-MM-DD_Category_Entity_Description.ext`
- [ ] **Place** in the correct 2nd-level subfolder
- [ ] **Update Section 9** in root `CLAUDE.md` (recent 10 entries)
- [ ] **Update Filing Log:**
      `20_Areas/00_Meta_System/Vault_Filing_Log.md`
- [ ] **Search for project linkage:**
      Extract identifiers → search `10_Projects/`
      If match found → update project's `00_PLAN.md`
- [ ] **Dual-file check:** Does this document need both PDF + MD?
      (See root CLAUDE.md Section 7)

---

## Safety Rules

- **NEVER** use `rm` to delete files from Inbox.
  Move unneeded files to `__To_Review/` or `~/.Trash/`.
- **NEVER** modify original files in-place.
  Copy first, then rename/move the copy.
- Use `mv <file> ~/.Trash/` instead of `rm` for cleanup.

---

## Automation

Use the `/process-inbox` skill to automate this workflow.
The skill follows this SOP and handles VNS naming,
destination routing, and linkage updates.

---

## VNS Quick Reference

**Format:** `YYYY-MM-DD_Category_Entity_Description.ext`

See `00_Vault/CLAUDE.md` for the full controlled vocabulary
and naming rules.
