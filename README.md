# Metalsmith Component Builder Skill

A Claude Desktop skill for building static websites using Metalsmith's component-based architecture. This skill guides users through creating professional websites without needing to know Metalsmith internals.

## What This Skill Does

- Helps users build websites using structured content and reusable components
- Adapts to three technical comfort levels:
  - **Path A**: Complete novices (Claude builds everything as downloadable ZIP)
  - **Path B**: Claude Desktop with MCP (Claude writes directly to local files)
  - **Path C**: Local development (full dev workflow with live reload)
- Downloads and installs components from [metalsmith-components.com](https://metalsmith-components.com)
- Guides deployment to GitHub and Netlify

## Installation

Clone this repository to your Claude Desktop skills directory:

**macOS:**
```bash
git clone https://github.com/wernerglinka/metalsmith-component-builder-skill.git ~/.claude/skills/metalsmith-component-builder-skill
```

**Windows:**
```bash
git clone https://github.com/wernerglinka/metalsmith-component-builder-skill.git %USERPROFILE%\.claude\skills\metalsmith-component-builder-skill
```

Restart Claude Desktop after installation.

## Usage

Start a conversation with Claude and say something like:

- "Build me a website"
- "Create a landing page for my business"
- "Help me set up a portfolio site"
- "Add a new page to my Metalsmith site"

Claude will determine your technical comfort level and guide you through the appropriate workflow.

## Related Resources

- [Metalsmith Components Library](https://metalsmith-components.com) - Downloadable components and documentation
- [Metalsmith Micro Starter](https://github.com/wernerglinka/microStarter) - Minimal starter template
- [Metalsmith Redux Blog Series](https://glinka.co/blog/) - In-depth tutorials

## Skill Contents

```
metalsmith-component-builder-skill/
├── SKILL.md                         # Main skill file
└── references/
    ├── learning-resources.md        # Educational resources
    └── starter-files.md             # Starter file reference
```

## License

MIT
