<p align="center">
  <img src="https://i.imgur.com/zHcwzra.png" alt="CC Swiss Knife - Claude Code Plugin Marketplace" />
</p>

<h1 align="center">CC Swiss Knife</h1>

<p align="center">
  <strong>Swiss army knife plugin marketplace for Claude Code</strong><br>
  Commands, skills, agents, workflows - validated & ready to use.
</p>

<p align="center">
  <a href="#installation">Installation</a> •
  <a href="#whats-included">What's Included</a> •
  <a href="#commands">Commands</a> •
  <a href="#skills">Skills</a> •
  <a href="#contributing">Contributing</a>
</p>

---

## Installation

Run inside Claude Code (not in your terminal):

```
# Add the marketplace
/plugin marketplace add OshanKHZ/cc-swiss-knife

# Install the plugin
/plugin install cc-swiss-knife
```

> **Note:** Skills activate automatically based on context. Try asking Claude to "create a skill" - the skill-development skill will kick in.

## Updating

```
/plugin → Manage marketplaces → cc-swiss-knife → Update
```

---

## What's Included

### 🔧 Commands (2)

| Command | Purpose | Flags/Args |
|---------|---------|------------|
| `/commit` | Quick conventional commit with auto-generated or custom message | `--push` `--amend` `--all` |
| `/changelog` | Generate or update CHANGELOG.md with smart version detection | `[version]` |

[View all commands →](./03%20-%20commands/)

### ⚡ Skills (6)

#### Plugin Development

| Skill | Purpose |
|-------|---------|
| `skill-development` | Create and validate skills with proper structure and frontmatter |
| `command-development` | Build slash commands with dynamic arguments and bash execution |
| `hook-development` | Event-driven automation with prompt and command hooks |
| `agent-development` | Design autonomous agents with system prompts and tool restrictions |
| `instructions-development` | Initialize and organize CLAUDE.md with codebase patterns |

#### Documentation

| Skill | Purpose |
|-------|---------|
| `documentation-standards` | Diataxis-based templates for READMEs, APIs, tutorials, and ADRs |

[View all skills →](./02%20-%20skills/)

---

## Commands

### `/commit` - Quick Conventional Commit

```bash
/commit                          # Auto-generate message
/commit feat: add login          # Custom message
/commit --push fix: typo         # Commit and push
/commit --all --push             # Stage all, commit, push
```

**Flags:** `--push` `--amend` `--all`

### `/changelog` - Changelog Generator

```bash
/changelog                       # Auto-detect version bump
/changelog 2.0.0                 # Specific version
```

**Features:**
- Smart version detection (package.json, Cargo.toml, any JSON/TOML with version)
- Conventional commits → changelog sections
- Respects existing changelog format
- Version sync across project files

---

## Skills

Skills activate automatically when relevant. No manual invocation needed.

**Plugin Development:**
- Ask Claude to "create a command" → `command-development` activates
- Ask to "build a skill" → `skill-development` activates
- Ask about "hooks" → `hook-development` activates

**Documentation:**
- Ask to "write documentation" → `documentation-standards` activates

---

## Local Development

```bash
git clone https://github.com/OshanKHZ/cc-swiss-knife.git
cd cc-swiss-knife
```

Inside Claude Code:

```
/plugin marketplace add ./
/plugin install cc-swiss-knife
```

After changes:

```
/plugin → Manage marketplaces → cc-swiss-knife → Update
```

---

## Contributing

Found a bug or have a suggestion?

- [Open an Issue](https://github.com/OshanKHZ/cc-swiss-knife/issues)
- [Submit a PR](https://github.com/OshanKHZ/cc-swiss-knife/pulls)

---

## License

MIT - Fork it, customize it, make it yours.
