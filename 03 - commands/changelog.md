---
allowed-tools: Bash(git:*, date:*, head:*, test:*, cat:*, grep:*), Read, Write, AskUserQuestion
argument-hint: [version]
description: Generate or update CHANGELOG.md following Keep a Changelog format
---

# Changelog Generator

**Arguments received:** $ARGUMENTS

## Context Gathering (MANDATORY)

**CRITICAL: Always run these commands first:**

1. **Get today's date (MANDATORY - never assume):**
   ```bash
   date +%Y-%m-%d
   ```
   Store this result for the release date.

2. **Check for existing CHANGELOG.md:**
   ```bash
   test -f CHANGELOG.md && echo "EXISTS" || echo "MISSING"
   ```

3. **If CHANGELOG.md exists, read only the first 50 lines to detect format:**
   ```bash
   head -50 CHANGELOG.md
   ```
   From this header, detect:
   - Does it use dates? (e.g., `## [1.0.0] - 2024-01-15` vs `## [1.0.0]`)
   - Section order (Added, Changed, Fixed, etc.)
   - Any custom header text
   - Link format at bottom (if any)

4. **Detect version source (check in order):**
   - `test -f package.json && grep '"version"' package.json`
   - `test -f Cargo.toml && grep '^version' Cargo.toml`
   - `test -f pyproject.toml && grep 'version' pyproject.toml`
   - `test -f setup.py && grep 'version' setup.py`
   - Git tags fallback: `git describe --tags --abbrev=0 2>/dev/null`

5. **Get commits since last version:**
   - Find last tag: `git describe --tags --abbrev=0 2>/dev/null`
   - If tag exists: `git log [tag]..HEAD --oneline`
   - If no tags: `git log --oneline -30`

## Existing Changelog Format Detection

**IMPORTANT:** If CHANGELOG.md exists, follow its existing conventions:

| Detected Pattern | Action |
|------------------|--------|
| `## [X.Y.Z] - YYYY-MM-DD` | Include date in new entry |
| `## [X.Y.Z]` (no date) | Omit date in new entry |
| Custom header text | Preserve existing header |
| Specific section order | Follow same order |
| Link references at bottom | Add link for new version |

**Never change the existing changelog's style.** Match it exactly.

## Version Bump Logic

Analyze commits to suggest version bump:

| Commit Pattern | Suggested Bump |
|----------------|----------------|
| `BREAKING CHANGE:` in body | Major (X.0.0) |
| `feat!:` or `fix!:` (with !) | Major (X.0.0) |
| `feat:` (new feature) | Minor (x.X.0) |
| `fix:`, `docs:`, `refactor:`, etc. | Patch (x.x.X) |

**If $ARGUMENTS provided:** Use it as the new version directly.

**If empty:** Calculate suggested bump and ask user to confirm.

## User Confirmation for Version

If no version argument provided, use AskUserQuestion:

Show:
- Current version: [detected version]
- Commits analyzed: [count]
- Breaking changes: [yes/no]
- New features: [count]
- Bug fixes: [count]

Question: "What version should this release be?"
Header: "Version"
Options:
  - [suggested version] (Recommended based on commits)
  - Patch bump (x.x.X)
  - Minor bump (x.X.0)
  - Major bump (X.0.0)

User can also select "Other" to provide custom version.

## Commit Type to Section Mapping

| Conventional Commit | Changelog Section |
|---------------------|-------------------|
| `feat:` | Added |
| `fix:` | Fixed |
| `docs:` | (skip - not user-facing) |
| `refactor:` | Changed |
| `perf:` | Changed |
| `style:` | (skip - not user-facing) |
| `test:` | (skip - not user-facing) |
| `chore:` | (skip - not user-facing) |
| `ci:` | (skip - not user-facing) |
| `build:` | (skip - not user-facing) |
| `security:` or contains "security" | Security |
| `deprecate:` or contains "deprecate" | Deprecated |
| `remove:` or contains "remove" | Removed |

**Note:** Only include sections that have entries. Empty sections should be omitted.

## Execution Steps

### Step 1: Gather Context (CRITICAL)

Run bash commands to gather:
- **Today's date** (MANDATORY: `date +%Y-%m-%d`)
- Existing changelog header (first 50 lines only)
- Current version from project files
- Last git tag
- Commits since last tag

### Step 2: Detect Existing Format

If CHANGELOG.md exists:
- Parse header to detect date format usage
- Identify section ordering convention
- Note any custom header or link patterns

### Step 3: Parse Commits

Analyze each commit message:
- Extract type and scope from conventional format
- Group by changelog section
- Format as bullet points

### Step 4: Determine Version

If $ARGUMENTS has version:
- Use provided version

If no version provided:
- Calculate suggested bump based on commit types
- Ask user to confirm with AskUserQuestion

### Step 5: Generate Changelog Entry

Create new version section matching existing format:
- Use detected date format (with date or without)
- Follow detected section order
- Only non-empty sections included

### Step 6: Preview and Confirm

Show preview of the new changelog entry to user.

Use AskUserQuestion:

Question: "Ready to update CHANGELOG.md with this entry?"
Header: "Confirm"
Options:
  - Yes, update changelog (Write the changes)
  - No, cancel (Abort without changes)

### Step 7: Write Changelog

If CHANGELOG.md exists:
- Read existing content
- Insert new version section after header (before first ## [x.y.z] entry)
- Preserve all existing content exactly

If CHANGELOG.md doesn't exist:
- Create with Keep a Changelog header:
  ```markdown
  # Changelog

  All notable changes to this project will be documented in this file.

  The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
  and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

  ## [Unreleased]

  ## [X.Y.Z] - YYYY-MM-DD
  ...
  ```

### Step 8: Update Version in Project Files (Optional)

After writing changelog, ask:

Question: "Update version in project files?"
Header: "Update ver"
Options:
  - Yes (Update package.json/Cargo.toml/etc.)
  - No (Only update changelog)

If yes, update the detected version source file.

### Step 9: Show Result

After completion, show:
- Path to CHANGELOG.md
- New version number
- Number of changes documented
- Suggest next steps (commit, tag, release)

## Error Handling

**No commits found:**
- Inform user there are no new commits to document
- Suggest checking if there are unreleased changes

**No version source found:**
- Ask user to provide version manually
- Suggest creating package.json or similar

**Malformed commits:**
- Include them under "Changed" section with original message
- Note that conventional commit format is recommended

## Example Output (with dates)

```markdown
## [1.2.0] - 2025-01-15

### Added
- Add user authentication with OAuth2 support
- Add dark mode toggle to settings

### Changed
- Refactor database connection pooling for better performance

### Fixed
- Fix memory leak in event handler
- Fix incorrect date formatting in reports
```

## Example Output (without dates, following existing format)

```markdown
## [1.2.0]

### Added
- Add user authentication with OAuth2 support

### Fixed
- Fix memory leak in event handler
```
