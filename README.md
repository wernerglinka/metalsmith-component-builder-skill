# Metalsmith Component Builder Skill

A Claude Code skill for building static websites using Metalsmith's component-based architecture. Users describe what they want, Claude handles the implementation.

## What This Skill Does

- Sets up a Metalsmith project from the micro starter
- Guides users through a discovery conversation to understand their needs
- Downloads and installs components from metalsmith-components.com
- Creates pages with proper YAML frontmatter structure
- Helps iterate based on live preview feedback
- Assists with Git setup and deployment to Netlify

## Prerequisites

Before using this skill, users should have:

- VS Code (or similar editor)
- Node.js 18+
- Git installed and configured
- GitHub account
- Netlify account (connected to GitHub)

## Installation

Clone this repository to your Claude Code skills directory:

```bash
git clone https://github.com/wernerglinka/metalsmith-component-builder-skill ~/.claude/skills/metalsmith-component-builder-skill
```

## Usage

1. Create an empty folder for your website
2. Open that folder in VS Code
3. Open the terminal and run `claude`
4. Tell Claude what you want:

```
I want to build a website for my photography business
```

Claude will:
- Clone the micro starter
- Install dependencies
- Start the dev server
- Ask questions about your site
- Build pages based on your answers
- Help you deploy when ready

## Workflow

1. **Project Setup** - Clone starter, install deps, start dev server
2. **Discovery Dialog** - Understand what the website needs
3. **Component Selection** - Download required components
4. **Page Building** - Create pages with live preview
5. **Review & Refine** - Iterate based on feedback
6. **Publish** - Push to GitHub, Netlify auto-deploys

## Related Resources

- [Metalsmith Components Library](https://metalsmith-components.com) - Component reference and downloads
- [Metalsmith Micro Starter](https://github.com/wernerglinka/microStarter) - The starter template
- [Metalsmith Redux Blog Series](https://glinka.co/blog/) - In-depth tutorials

## Skill Contents

```
metalsmith-component-builder-skill/
├── SKILL.md                      # Main skill file
├── README.md                     # This file
└── references/
    ├── learning-resources.md     # Documentation links
    └── starter-files.md          # Starter structure reference
```

## License

MIT
