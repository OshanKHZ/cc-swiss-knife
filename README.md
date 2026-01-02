<p align="center">
  <img src="https://imgur.com/73Iyp7u.png" alt="CC Swiss Knife - Claude Code Plugin Marketplace" />
</p>

<p align="center">
  <a href="CHANGELOG.md"><img src="https://img.shields.io/badge/version-1.2.0-white" alt="Version" /></a>
  <a href="plugins/"><img src="https://img.shields.io/badge/Commands-2-brightgreen" alt="Commands" /></a>
  <a href="plugins/"><img src="https://img.shields.io/badge/Skills-7-orange" alt="Skills" /></a>
  <a href="plugins/"><img src="https://img.shields.io/badge/Commands-2-blue" alt="Commands" /></a>
  <a href="https://github.com/OshanKHZ/cc-swiss-knife"><img src="https://img.shields.io/github/stars/OshanKHZ/cc-swiss-knife?style=social" alt="GitHub Stars" /></a>
</p>

<h1 align="center">Claude Code - Swiss Knife</h1>

<p align="center">
  <strong>Swiss army knife plugin marketplace for Claude Code</strong><br>
  Commands, skills, agents, workflows - validated & ready to use.
</p>

<p align="center">
  <a href="#installation">Installation</a> •
  <a href="#plugins">Plugins</a> •
  <a href="#contributing">Contributing</a>
</p>

---

## Installation

Run inside Claude Code (not in your terminal):

```bash
# Add the marketplace
/plugin marketplace add OshanKHZ/cc-swiss-knife
```

Then install the plugin(s) you want:

```bash
# Core tools (everyone)
/plugin install cc-swiss-knife

# Plugin development (developers)
/plugin install claude-code-forge
```

## Updating

```
/plugin → Manage marketplaces → cc-swiss-knife → Update
```

---

<p align="center">
  <img src="https://imgur.com/ajch7a7.png" alt="CC Swiss Knife - Claude Code Plugin Marketplace" />
</p>

## Whats's Included

### 🧩 Plugin: cc-swiss-knife (Core)

Essential toolkit for everyday use.

```bash
/plugin install cc-swiss-knife
```

**Commands:**

| Command | Purpose | Flags/Args |
|---------|---------|------------|
| `/commit` | Quick conventional commit with auto-generated or custom message | `--push` `--amend` `--all` |
| `/changelog` | Generate or update CHANGELOG.md with smart version detection | `[version]` |

**Skills:**

| Skill | Purpose |
|-------|---------|
| `documentation-standards` | Diataxis-based templates for READMEs, APIs, tutorials, and ADRs |

[View all →](./plugins/core/)

---

### 🧩 Plugin: claude-code-forge (Development)

Skills and resources for building Claude Code plugins, commands, agents, and hooks.

```bash
/plugin install claude-code-forge
```

**Skills:**

| Skill | Purpose |
|-------|---------|
| `skill-development` | Create and validate skills with proper structure and frontmatter |
| `command-development` | Build slash commands with dynamic arguments and bash execution |
| `hook-development` | Event-driven automation with prompt and command hooks |
| `agent-development` | Design autonomous agents with system prompts and tool restrictions |
| `instructions-development` | Initialize and organize CLAUDE.md with codebase patterns |

[View all →](./plugins/claude-code-forge/)

---

## Local Development

```bash
git clone https://github.com/OshanKHZ/cc-swiss-knife.git
cd cc-swiss-knife
```

Inside Claude Code:

```bash
/plugin marketplace add ./
/plugin install cc-swiss-knife
/plugin install claude-code-forge
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
