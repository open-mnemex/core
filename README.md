# mnemex

**AI-powered digital life management framework for Claude Code.**

mnemex turns `~/Documents` into a structured, AI-navigable system
for managing your entire digital life — legal documents, finances,
projects, research, and personal archives — with Claude Code as
your intelligent file clerk.

## Architecture

```text
~/Documents
├── 00_Vault/       # Immutable facts (IDs, receipts, contracts)
├── 10_Projects/    # Active work with deadlines
├── 20_Areas/       # Capabilities & systems you maintain
├── 30_Resources/   # External collected materials
├── 99_Archives/    # Completed projects (cold storage)
└── __To_Review/    # Staging area (safe landing zone)
```

## Philosophy

### Fact vs Fiction (事实与创造分离)

- **Facts** (`00_Vault`) are immutable.
  A tax return, once filed, never changes.
- **Creations** (`10_Projects`) are volatile.
  Drafts evolve until they ship.

### Capability vs Collection (能力与收藏分离)

- **Capabilities** (`20_Areas`) are skills you maintain.
- **Collections** (`30_Resources`) are things you've gathered.

### Flow (流动性)

Files enter via `~/Downloads` → active work in `Projects` →
final artifacts to `Vault` → dead projects to `Archives`.

## The CLAUDE.md / README.md Pattern

This is the core design pattern of mnemex:

| File | Contains | Tracked in Git? |
|------|----------|-----------------|
| `CLAUDE.md` | Rules, protocols, naming conventions | Yes |
| `README.md` | Your personal data, entity names, inventories | **No** |
| `README.example.md` | Template showing expected structure | Yes |

**Why?** `CLAUDE.md` files are the framework — reusable by anyone.
`README.md` files hold your personal context — entity names,
active project lists, folder inventories. Claude Code auto-loads
both, giving you a system that's both shareable and personalized.

## Plugins

Skills and agents live in a separate repo:
[**mnemex-plugins**](https://github.com/open-mnemex/mnemex-plugins)

```bash
# Add the marketplace
/plugin marketplace add open-mnemex/mnemex-plugins

# Install what you need
/plugin install mnemex-core@mnemex-plugins
/plugin install macos-automation@mnemex-plugins
/plugin install dev-tools@mnemex-plugins
```

See the [mnemex-plugins README](https://github.com/open-mnemex/mnemex-plugins)
for the full plugin catalog.

## Getting Started

### Prerequisites

- [Claude Code](https://docs.anthropic.com/en/docs/claude-code)
  (Anthropic's CLI)
- macOS (required for `macos-automation` plugin)

### Setup

1. Clone this repo into `~/Documents`:
   ```bash
   git clone https://github.com/open-mnemex/core.git ~/Documents
   ```

2. Copy each `README.example.md` to `README.md` in the same folder:
   ```bash
   cd ~/Documents
   for f in $(find . -name "README.example.md"); do
     cp "$f" "$(dirname "$f")/README.md"
   done
   ```

3. Fill in your personal data in each `README.md`
   (entity names, project lists, area inventories).

4. Start using skills:
   ```
   /processing-inbox   # File documents from Downloads
   /capture quote      # Save a quote to Resources
   /project init       # Start a new project
   ```

## Customization

### Adding Areas

Create subdirectories under `20_Areas/` based on your life domains.
The SOPs and CLAUDE.md files describe recommended structures as
examples — adapt them to your needs.

### Adding Vault Subdomains

The Vault structure in `00_Vault/CLAUDE.md` shows the recommended
taxonomy. Create only the folders you need.

### Project Categories

See `20_Areas/00_Meta_System/Reference_Project_Category_Controlled_Vocabulary.md`
for the 7-pillar category system (Legal, Asset, Admin, Research,
Dev, Academic, Event).

## Key Documents

| Document | Location |
|----------|----------|
| System Architecture | `CLAUDE.md` (root) |
| Vault Guide & VNS Naming | `00_Vault/CLAUDE.md` |
| Project Lifecycle | `10_Projects/CLAUDE.md` |
| Areas Philosophy | `20_Areas/CLAUDE.md` |
| Resources Guide | `30_Resources/CLAUDE.md` |
| Archives & 3R Protocol | `99_Archives/CLAUDE.md` |
| Inbox Processing SOP | `20_Areas/00_Meta_System/SOP_01_Inbox_Processing.md` |
| Project Closeout SOP | `20_Areas/00_Meta_System/SOP_02_Project_Closeout.md` |
| Backup & Restore SOP | `20_Areas/00_Meta_System/SOP_03_Backup_Restore.md` |
| Project Init SOP | `20_Areas/00_Meta_System/SOP_04_Project_Initialization.md` |
| Category Vocabulary | `20_Areas/00_Meta_System/Reference_Project_Category_Controlled_Vocabulary.md` |

## License

[MIT](LICENSE)
