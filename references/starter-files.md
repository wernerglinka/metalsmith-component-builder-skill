# Starter Files Reference

Reference for the micro starter structure. Claude clones this directly from GitHub rather than recreating it.

## Starter Repository

**URL**: https://github.com/wernerglinka/microStarter

Clone into current directory:
```bash
git clone https://github.com/wernerglinka/microStarter.git .
```

## Directory Structure

```
my-website/
├── src/                          # Content pages (markdown with YAML frontmatter)
│   └── index.md                  # Homepage
├── lib/
│   ├── assets/                   # Static files copied to build
│   │   ├── images/
│   │   ├── styles/
│   │   │   └── global.css        # Global styles
│   │   └── scripts/
│   │       └── global.js         # Global scripts
│   ├── data/
│   │   └── site.json             # Site-wide configuration
│   └── layouts/
│       ├── components/
│       │   ├── sections/         # Section components
│       │   │   ├── text-only/
│       │   │   ├── header/
│       │   │   ├── footer/
│       │   │   └── commons/
│       │   ├── _partials/        # Shared partial templates
│       │   │   ├── text.njk
│       │   │   ├── ctas.njk
│       │   │   ├── button.njk
│       │   │   └── image.njk
│       │   └── _helpers/         # Rendering utilities
│       │       ├── render-section.njk
│       │       └── container-attributes.njk
│       └── pages/
│           ├── default.njk       # Base page template
│           └── sections.njk      # Sectioned page template
├── nunjucks-filters/             # Custom Nunjucks filters
├── metalsmith.js                 # Build configuration
├── metalsmith-components.config.json
├── package.json
└── .gitignore
```

## Key Configuration Files

### lib/data/site.json

```json
{
  "title": "Site Name",
  "description": "Site description for SEO",
  "url": "https://example.com/",
  "locale": "en_US",
  "defaultImage": "/assets/images/social.png",
  "siteOwner": "Owner Name"
}
```

### Page Template (src/index.md)

```yaml
---
layout: pages/sections.njk
bodyClasses: home-page

navigation:
  navLabel: Home
  navIndex: 0

seo:
  title: Page Title
  description: Page description

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
        color: ""
        image: ""
        imageScreen: none
    text:
      leadIn: ""
      title: Welcome
      titleTag: h1
      subTitle: ""
      prose: |-
        Content goes here.
    ctas:
      - url: /about
        label: Learn More
        isButton: true
        buttonStyle: primary
---
```

## Adding Components

Download from metalsmith-components.com:

```bash
curl -L https://metalsmith-components.com/downloads/sections/[name].zip -o [name].zip
unzip [name].zip
cd [name]
./install.sh
cd ..
rm -rf [name] [name].zip
```

Restart dev server after adding components.

## Build Commands

```bash
npm start          # Dev server with live reload (localhost:3000)
npm run build      # Production build to ./build/
npm run serve      # Preview production build
npm run fix        # Format and lint code
```
