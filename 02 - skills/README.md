# Skills Reference

Quick lookup for available skills and when to use each.

## 📦 Dev Skills (`dev-skills/`)

Skills for building Claude Code plugin components.

| Skill | Use When | What It Does |
|-------|----------|--------------|
| `skill-development` | Creating or modifying skills | Templates, examples, validation for skill creation |
| `command-development` | Creating custom commands | Frontmatter reference, interactive patterns, marketplace prep |
| `hook-development` | Creating hook scripts | Patterns for bash/load/write/validate hooks |
| `agent-development` | Creating specialized agents | System prompts, triggering, agent architecture |
| `instructions-development` | Setting up CLAUDE.md | Modular organization, initialization, sync workflows |

## 📝 Documentation (`documentation-standards/`)

| Skill | Use When | What It Does |
|-------|----------|--------------|
| `documentation-standards` | Writing any documentation | Templates and checklists for README, API docs, ADRs, tutorials |

## 🎯 Usage

Skills are automatically available when this plugin is installed. Claude Code loads them from this directory.

**To use a skill:** Reference it in your request (e.g., "use the skill-development skill to create a new skill").

**To verify a skill:** Check its `SKILL.md` for usage instructions and examples.
