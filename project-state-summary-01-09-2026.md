## Project State Summary: Metalsmith Component Builder Skill

**Date**: January 9, 2026

**Goal**: Enable users to build Metalsmith websites through conversation with Claude, without learning Metalsmith internals.

### Key Decisions Made

**Target audience**: VS Code users comfortable with terminal basics. Not complete novices (that requires a hosted solution), not expert developers (they don't need this).

**Tooling**: Claude Code, not Claude Desktop with MCP. Claude Code has native filesystem access, integrates with VS Code workflow, no MCP configuration needed.

**Workflow**: Single streamlined path. Removed the three-path approach (novice/MCP/local dev) from original skill. User runs Claude Code in an empty folder, Claude handles everything from there.

**Skill installation**: User clones skill repo to `~/.claude/skills/` before starting. Blogpost walks them through this as part of setup.

**Project setup**: Claude clones microStarter directly into current directory, runs npm install, starts dev server. No ZIP files, no manual downloads.

**Git/deployment**: User handles git through normal workflow (not via PAT token in chat). Claude guides the commands but user runs them or Claude runs them via bash. Netlify connected through web UI.

### Files Updated

**Skill files** at `/Users/wernerglinka/Projects/metalsmith-component-builder-skill/`:

- `SKILL.md` - Complete rewrite, single workflow, 6 phases
- `README.md` - Updated for Claude Code approach
- `references/learning-resources.md` - Cleaned up, removed Path A references
- `references/starter-files.md` - Simplified to reference only, no ZIP building

**Blogpost** at `/Users/wernerglinka/Projects/+++Blogposts/build-website-with-claude.md`:

- Prerequisites: Node.js, Git, Claude Code, GitHub account, Netlify account
- Skill installation: single git clone command
- Usage: create folder → run claude → describe what you want
- Deployment: standard git push, Netlify auto-deploys

### Starter Repository

Using: `https://github.com/wernerglinka/microStarter`

### Component Source

Components downloaded from: `https://metalsmith-components.com/downloads/sections/[name].zip`

### Next Step

Test the workflow end-to-end following the blogpost as a user would. Identify friction points and revise.

### Future Consideration

After validation, explore "hosted builder" option for true non-technical users. Web app that handles Claude + Metalsmith + deployment behind a simple chat/form interface.
