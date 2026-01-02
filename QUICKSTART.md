# Quick Start

Get cc-swiss-knife running in **under 2 minutes**.

## 📋 Prerequisites

- [ ] Claude Code CLI installed and configured
- [ ] An active Claude Code session

## 🚀 Installation (~1 min)

Run these commands **inside Claude Code** (not in your terminal):

### 1. Add the Marketplace

```bash
/plugin marketplace add OshanKHZ/cc-swiss-knife
```

### 2. Install Plugin(s)

```bash
# Core tools (recommended for everyone)
/plugin install cc-swiss-knife

# Plugin development (for developers building plugins)
/plugin install claude-code-forge
```

## ✅ Verify It Works

### Test cc-swiss-knife:

```bash
/commit --help
```

Or stage some changes and run:

```bash
/commit
```

### Test claude-code-forge:

Ask Claude:

```
Create a skill for me
```

If the skill-development skill activates and Claude starts guiding you, it works!

## 🔧 Troubleshooting

### "Marketplace not found" error

Ensure you typed the marketplace name correctly:

```bash
/plugin marketplace add OshanKHZ/cc-swiss-knife
```

### Plugin doesn't appear after install

Try restarting your Claude Code session or run:

```bash
/plugin → Manage marketplaces → cc-swiss-knife → Update
```

### Skills not activating

Skills activate based on natural language triggers. Try being specific:

- "Create a new skill for my plugin"
- "Help me write a slash command"
- "I need to create a hook"

## 🆘 Need Help?

- [README](./README.md) - Full list of included plugins
- [CONTRIBUTING](./CONTRIBUTING.md) - How to contribute
- [GitHub Issues](https://github.com/OshanKHZ/cc-swiss-knife/issues) - Report bugs
