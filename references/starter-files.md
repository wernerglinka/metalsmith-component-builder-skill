# Starter Files Reference

This file contains the essential file contents Claude needs to build a complete micro starter project from scratch for Path A users.

**For Path A (Complete Novice)**: Claude recreates the entire micro starter structure with the user's content, then provides it as a downloadable ZIP. The user's only technical tasks are uploading to GitHub (drag and drop via web) and connecting Netlify (a few clicks).

For the complete starter as reference, see: https://github.com/wernerglinka/microStarter

## Critical Configuration Files

### package.json

```json
{
  "name": "my-website",
  "version": "1.0.0",
  "description": "A component-based website built with Metalsmith",
  "type": "module",
  "scripts": {
    "dev": "metalsmith -c metalsmith.js --env NODE_ENV=development",
    "build": "metalsmith -c metalsmith.js --env NODE_ENV=production",
    "start": "NODE_ENV=development node metalsmith.js --watch",
    "serve": "browser-sync start --server 'build'",
    "format": "prettier --write \"**/*.{js,json,njk,css}\"",
    "lint": "eslint --fix .",
    "fix": "npm run format && npm run lint"
  },
  "devDependencies": {
    "browser-sync": "^3.0.4",
    "eslint": "^9.33.0",
    "prettier": "^3.6.2"
  },
  "dependencies": {
    "@metalsmith/drafts": "^1.3.0",
    "@metalsmith/layouts": "^3.0.0",
    "@metalsmith/permalinks": "^3.2.0",
    "autoprefixer": "^10.4.21",
    "cssnano": "^7.1.0",
    "jstransformer-nunjucks": "^1.2.0",
    "marked": "^16.2.0",
    "metalsmith": "^2.6.3",
    "metalsmith-bundled-components": "^0.4.1",
    "metalsmith-optimize-html": "^0.7.0",
    "metalsmith-safe-links": "^2.1.0",
    "metalsmith-static-files": "^2.0.0",
    "postcss": "^8.5.6"
  },
  "engines": {
    "node": ">=18.0.0"
  }
}
```

### metalsmith-components.config.json

```json
{
  "componentsBasePath": "lib/layouts/components",
  "sectionsDir": "sections",
  "partialsDir": "_partials"
}
```

### .gitignore

```
node_modules/
build/
.DS_Store
*.log
```

### lib/data/site.json

```json
{
  "title": "My Website",
  "description": "A website built with Metalsmith components",
  "url": "https://example.com/",
  "locale": "en_US",
  "defaultImage": "/assets/images/social.png",
  "siteOwner": "Site Owner Name"
}
```

## Page Template Example

### src/index.md (Homepage)

```yaml
---
layout: pages/sections.njk
bodyClasses: home-page

navigation:
  navLabel: Home
  navIndex: 0

seo:
  title: Welcome to My Website
  description: A brief description of the website

sections:
  - sectionType: text-only
    containerTag: section
    containerFields:
      inContainer: true
      isAnimated: true
      noMargin:
        top: true
        bottom: false
      noPadding:
        top: false
        bottom: false
      background:
        color: ''
        image: ''
        imageScreen: none
    text:
      leadIn: ''
      title: Welcome
      titleTag: h1
      subTitle: ''
      prose: |-
        This is the homepage content. You can write multiple paragraphs here using markdown.
        
        Add more sections below to build out the page.
    ctas:
      - url: /about
        label: Learn More
        isButton: true
        buttonStyle: primary
---
```

## Building for Path A

When a Path A user needs a website, Claude must:

1. **Clone or fetch the complete micro starter** from https://github.com/wernerglinka/microStarter
2. **Modify content files** based on the discovery dialog:
   - `lib/data/site.json` - site title, description, owner
   - `src/index.md` - homepage content
   - `src/*.md` - additional pages as needed
3. **Add images** to `lib/assets/images/` if the user provides them
4. **Package everything as a ZIP** for download

The micro starter includes all the complex infrastructure:
- `metalsmith.js` - complete build configuration
- `nunjucks-filters/` - all template filters (markdown, dates, validation, etc.)
- `lib/layouts/components/_helpers/` - section renderer, container attributes
- `lib/layouts/components/_partials/` - text, ctas, button, image, navigation, etc.
- `lib/layouts/components/sections/` - text-only, header, footer, commons
- `lib/layouts/pages/` - default.njk, sections.njk
- `lib/assets/` - global CSS, JS, icons

Claude should NOT attempt to recreate these files from memory - they are interconnected and require exact implementations. Instead, Claude should work from the actual starter repository.

## If Additional Components Are Needed

If the user needs components beyond text-only (hero, banner, etc.):

**For Path A users**: Claude downloads the required components from metalsmith-components.com, extracts them, and includes them in the ZIP before giving it to the user. The user receives a complete, ready-to-deploy site with all needed components already installed.

Component download URLs follow this pattern:
- Sections: `https://metalsmith-components.com/downloads/sections/[name].zip`
- Partials: `https://metalsmith-components.com/downloads/partials/[name].zip`

Claude should check each component's manifest.json for required dependencies (partials) and include those as well.

**For Path B/C users**: Download and install components directly using the install.sh scripts.
