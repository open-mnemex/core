# SOP 03: Backup & Restore (备份与恢复)

**Philosophy:** Data exists in at least two places,
or it doesn't exist at all.

---

## Current Strategy

| Layer | Method | Coverage | Frequency |
|-------|--------|----------|-----------|
| Primary | Time Machine | Full `~/Documents` | Hourly |
| Secondary | iCloud Drive | Full `~/Documents` | Continuous |
| Tertiary | Manual export | Critical Vault items | Quarterly |

**Note:** No Git tracking in `~/Documents` (too many binary files).

---

## Priority Table

| Priority | Domain | Rationale |
|----------|--------|-----------|
| **P0** | `00_Vault` | Irreplaceable facts (IDs, legal docs) |
| **P1** | `10_Projects` | Active work with deadlines |
| **P2** | `20_Areas` | Living systems, configs, SOPs |
| **P3** | `30_Resources` | External materials (re-downloadable) |
| **P4** | `99_Archives` | Frozen, low urgency |

---

## Recovery Procedures

### Scenario 1: Accidental Deletion

1. Check `~/.Trash/` first (if moved via `mv`)
2. Time Machine → "Enter Time Machine" → navigate to date
3. iCloud Drive → check iCloud.com for recently deleted

### Scenario 2: File Corruption

1. Time Machine → restore previous version
2. Compare with iCloud version if available

### Scenario 3: Full System Restore

1. Boot into Recovery Mode
2. Restore from Time Machine backup
3. Verify `00_Vault` integrity first (P0)
4. Check `10_Projects` for any in-progress work

---

## Prevention Rules

- **NEVER** use `rm -rf` on folders containing user files.
- **NEVER** use `rm` to delete files. Use `mv <file> ~/.Trash/`.
- When reorganizing: `cp` first, verify, then trash original.
- `rm` bypasses Time Machine's "browse deleted files" feature.

---

## Incident Log

| Date | Incident | Impact | Lesson |
|------|----------|--------|--------|
| 2026-01-31 | `rm -rf` on vacation photo folder | Data lost | Added "No rm" rule to Security Protocol |
