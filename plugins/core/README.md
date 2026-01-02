# CC Swiss Knife

Essential commands, skills, and workflows for everyday development.

## Installation

```bash
/plugin install cc-swiss-knife
```

---

## Commands

### `/commit` - Quick Conventional Commit

Create git commits with conventional format and optional auto-generation.

```bash
/commit                          # Auto-generate message from staged changes
/commit feat: add login          # Custom message
/commit --push fix: typo         # Commit and push
/commit --all --push             # Stage all, commit, push
/commit --amend                  # Amend last commit
```

**Flags:**

| Flag | Effect |
|------|--------|
| `--push` | Push to remote after commit |
| `--amend` | Amend last commit |
| `--all` | Stage all changes before commit |

**Features:**
- Auto-generates message from staged changes
- Follows conventional commit format
- Blocks commits of sensitive files (.env, secrets)
- Validates commit message format

---

### `/changelog` - Changelog Generator

Generate or update CHANGELOG.md with smart version detection.

```bash
/changelog                       # Auto-detect version bump
/changelog 2.0.0                 # Specific version
```

**Features:**

| Feature | Description |
|---------|-------------|
| Smart versioning | Suggests patch/minor/major based on conventional commits |
| Format detection | Matches existing changelog style (dates, "v" prefix) |
| Tiered version detection | Finds version in package.json, Cargo.toml, or any JSON/TOML |
| Version sync | Updates project files when versions mismatch |

**Date format:** `December 25th, 2025`

**Commit mapping:**
- `feat:` → Added
- `fix:` → Fixed
- `refactor:`, `perf:` → Changed
- `security:` → Security

---

## Skills

### `documentation-standards`

Diataxis-based templates and guidelines for technical documentation.

**Activates when you ask to:**
- Write documentation
- Create a README
- Document an API
- Write a tutorial

**Includes templates for:**
- READMEs (root and module level)
- API documentation
- Tutorials and how-to guides
- ADRs (Architecture Decision Records)
- Contributing guides
- Quickstart guides

---

## Roadmap

Coming soon:
- `/release` - Automate release workflows
- `/test` - Smart test runner
- `/review` - Code review assistant
- More productivity skills

---

## Links

- [Marketplace](https://github.com/OshanKHZ/cc-swiss-knife)
- [Issues](https://github.com/OshanKHZ/cc-swiss-knife/issues)
- [Contributing](../../CONTRIBUTING.md)
