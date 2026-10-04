# Project Overview
Shared agent rules (`rules/*.md`) consumed by other repositories via [agent-rules-nix](https://github.com/Hol1kgmg/agent-rules-nix). One file = one rule; the file name is the rule ID. Frontmatter is distributed as-is.

# Setup and Basic Usage
Setup instructions and basic usage are documented in [README.md](./README.md).

# Work Rules
1. Propose implementation plan
2. Wait for approval
3. Start implementation

# Tool Usage Policy
**Prefer dedicated tools for file operations by default** (not enforced via `permissions.deny` — occasional Bash use is fine when it's genuinely more convenient):
- `ls`, `find` → `Glob` tool
- `cat`, `head`, `tail` → `Read` tool
- `grep` → `Grep` tool
- `sed`, `awk` → `Edit` tool
- File writing → `Write` tool
- `curl` → `WebFetch` tool

# Language Settings
- Responses: `.claude/settings.json` - `language`
- Thinking: English (for token reduction)
