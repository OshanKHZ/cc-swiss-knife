# Commands Reference

Quick-access slash commands for common workflows.

## 📌 Available Commands

### `/commit` - Quick Conventional Commit

Create git commits with conventional format and optional auto-generation.

**Usage:**
```
/commit [flags] [type: message]
```

**Flags:**

| Flag | Effect |
|------|--------|
| `--push` | Push to remote after commit |
| `--amend` | Amend last commit (use with caution) |
| `--all` | Stage all changes before commit (`git add -A`) |

**Examples:**

```bash
# Auto-generate message from staged changes
/commit

# With custom message
/commit feat: add user authentication

# With scope
/commit fix(api): handle null response

# Commit and push
/commit --push docs: update README

# Stage all, commit, and push
/commit --all --push feat: add login page

# Amend last commit
/commit --amend fix: correct typo
```

**Conventional Commit Format:**
- `feat:` new feature
- `fix:` bug fix
- `docs:` documentation
- `refactor:` code change (no feat/fix)
- `test:` tests
- `chore:` maintenance
- Add `(scope)` for area: `feat(auth):`
- Add `!` for breaking: `feat!:`

**Message Rules:**
- Use imperative mood: "add" not "added"
- Max 72 chars first line
- Think: "If applied, this commit will [message]"

## 🎯 Usage Tips

**Auto-staging:** If nothing is staged, command will ask what to stage.

**Security:** Command blocks commits of `.env`, secrets, and credential files.

**Message generation:** When no message provided, analyzes git diff and recent commits to generate appropriate conventional commit.
