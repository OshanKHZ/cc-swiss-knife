# Contributing

Thanks for your interest in contributing to cc-swiss-knife!

## 🤝 Ways to Contribute

- Report bugs
- Suggest new skills or commands
- Submit pull requests
- Improve documentation

## 🐛 Reporting Bugs

1. Check [existing issues](https://github.com/OshanKHZ/cc-swiss-knife/issues) first
2. Open a new issue with:
   - Clear title
   - Steps to reproduce
   - Expected vs actual behavior
   - Claude Code version

## 🛠️ Development Setup

```bash
# Clone the repo
git clone https://github.com/OshanKHZ/cc-swiss-knife.git
cd cc-swiss-knife
```

Then in Claude Code:

```bash
# Add local marketplace
/plugin marketplace add ./

# Install plugins
/plugin install cc-swiss-knife
/plugin install claude-code-forge
```

## 📁 Project Structure

```
cc-swiss-knife/
├── plugins/
│   ├── core/              # cc-swiss-knife plugin
│   │   ├── commands/
│   │   └── skills/
│   └── claude-code-forge/ # claude-code-forge plugin
│       └── skills/
└── .claude-plugin/
    └── marketplace.json
```

## ✅ Validation Scripts

Before submitting changes, run the relevant validation scripts:

```bash
# Validate commands
bash plugins/claude-code-forge/skills/command-development/scripts/validate-command.sh <file>

# Validate skills
bash plugins/claude-code-forge/skills/skill-development/scripts/validate-skill.sh <file>

# Validate agents
bash plugins/claude-code-forge/skills/agent-development/scripts/validate-agent.sh <file>

# Validate hooks
bash plugins/claude-code-forge/skills/hook-development/scripts/validate-hook-schema.sh <file>
```

## 🔀 Pull Request Process

1. Fork the repo
2. Create a branch: `git checkout -b feature/my-feature`
3. Make your changes
4. Run validation scripts
5. Commit with conventional format: `feat:`, `fix:`, `docs:`
6. Push and open PR

## 📜 Code of Conduct

- Be respectful and inclusive
- Accept constructive feedback
- Focus on what's best for the community

## ❓ Questions?

Open an issue with the `question` label.
