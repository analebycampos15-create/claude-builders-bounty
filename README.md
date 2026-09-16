# Generate Changelog Tool & Skill

> Automatically generate structured `CHANGELOG.md` files from Git commit history following Keep a Changelog standards.

## Features

- 🏷️ **Tag-Aware**: Automatically computes commits since the most recent Git release tag.
- 📂 **Auto-Categorization**: Groups commits by conventional commit prefixes (`feat:` → **Added**, `fix:` → **Fixed**, `refactor:`/`docs:`/`chore:` → **Changed**, `remove:` → **Removed**, `security:` → **Security**).
- 🔄 **Safe Incremental Updates**: Prepends new versions directly under `# Changelog` preserving past releases.
- ⚡ **Zero Dependencies**: Pure standard Python (Python 3.8+).

---

## 3-Step Setup & Usage

### 1. Place in your project
Copy `generate_changelog.py` (and `changelog.sh`) to your project root or scripts directory.

### 2. Run
```bash
# Generate / update CHANGELOG.md for unreleased commits
python generate_changelog.py
```

### 3. Specify release versions (Optional)
```bash
# Tag a new release version
python generate_changelog.py --version "v1.2.0" --tag "v1.1.0"
```

---

## Claude Code Skill Usage

Add `skills/generate-changelog/SKILL.md` to your Claude Code skills directory. Claude Code will automatically invoke the skill when you ask to draft or update release notes.

---

## Sample Generated Output

```markdown
# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/).

## [v1.2.0] - 2026-03-27

### Added
- User authentication and session management (`a1b2c3d`)
- Export data to CSV and JSON formats (`e4f5a6b`)

### Fixed
- Timeout error on slow database connections (`7c8d9e0`)
- Mobile responsive layout padding (`1f2a3b4`)

### Changed
- Refactor authentication middleware for speed (`5d6e7f8`)
- Update documentation and setup guide (`9a0b1c2`)
```

---

## Running Tests

```bash
python -m unittest discover -s tests
```
