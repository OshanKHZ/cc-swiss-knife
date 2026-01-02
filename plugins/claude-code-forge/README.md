# Claude Code Forge

The forge for Claude Code plugin development - create skills, commands, agents, hooks, and more.

## Installation

```bash
/plugin install claude-code-forge
```

---

## Skills

All skills activate automatically based on context. Just describe what you need.

### `skill-development`

Create, edit, and validate skills with proper structure and frontmatter.

**Activates when you:**
- "Create a skill for..."
- "Help me build a skill"
- "I need a new skill that..."

**What it provides:**
- SKILL.md structure and frontmatter
- Progressive disclosure patterns
- Examples and references organization
- Validation scripts

---

### `command-development`

Build slash commands with dynamic arguments, file references, and bash execution.

**Activates when you:**
- "Create a slash command"
- "Build a command for..."
- "I need a /command that..."

**What it provides:**
- Command frontmatter (allowed-tools, argument-hint, model)
- Dynamic arguments with $ARGUMENTS
- Bash execution patterns
- Interactive commands with AskUserQuestion

---

### `hook-development`

Create event-driven automation with prompt-based and command hooks.

**Activates when you:**
- "Create a hook for..."
- "I need a PreToolUse hook"
- "Add validation before..."

**What it provides:**
- Hook events (PreToolUse, PostToolUse, Stop, etc.)
- Prompt-based hooks API
- Command hooks with matchers
- Validation and policy patterns

---

### `agent-development`

Design autonomous agents with system prompts and tool restrictions.

**Activates when you:**
- "Create an agent for..."
- "Build a subagent that..."
- "I need an autonomous agent"

**What it provides:**
- Agent frontmatter and structure
- System prompt design
- Triggering conditions and examples
- Tool restrictions

---

### `instructions-development`

Initialize, sync, and organize CLAUDE.md with codebase patterns.

**Activates when you:**
- "Create CLAUDE.md"
- "Initialize project instructions"
- "Organize my .claude/rules"

**What it provides:**
- CLAUDE.md templates
- Modular rules organization
- Sync with codebase patterns
- Best practices

---

### `plugin-development`

Create and structure complete Claude Code plugins.

**Activates when you:**
- "Create a plugin"
- "Build a new plugin for..."
- "I need a plugin that..."

**What it provides:**
- Plugin structure and plugin.json
- Marketplace configuration
- Component organization
- Distribution workflow

---

## Usage Examples

```
# Create a new skill
"Create a skill for code review that checks for security issues"

# Build a command
"Build a /deploy command that pushes to production"

# Add a hook
"Create a hook that validates all Write operations"

# Design an agent
"Create an agent that analyzes test coverage"
```

---

## Links

- [Marketplace](https://github.com/OshanKHZ/cc-swiss-knife)
- [Issues](https://github.com/OshanKHZ/cc-swiss-knife/issues)
- [Contributing](../../CONTRIBUTING.md)
