# Learning Resources

## Authoritative Source

**https://metalsmith-components.com** is the authoritative source for this structured Metalsmith approach. Always consult this site for accurate component configuration and patterns.

## Metalsmith Components Documentation

### Reference Pages

Each component has a dedicated reference page at metalsmith-components.com:

- **Sections**: https://metalsmith-components.com/references/sections/
- **Partials**: https://metalsmith-components.com/references/partials/

Reference pages include:
- Live examples with different configurations
- Complete YAML configuration options
- Data structure requirements
- Download button for the component package

### Key Blog Posts

Fetch these when questions arise:

- `/blog/installing-metalsmith-components/` - Download and install component packages
- `/section-anatomy/` - How components are structured internally
- `/yaml-to-html/` - The rendering process from frontmatter to final output
- `/blog/building-pages-with-components/` - Page construction patterns
- `/blog/building-interactive-components/` - Adding JavaScript behavior

## Metalsmith Redux Blog Series

The Metalsmith Redux series at glinka.co/blog/ provides in-depth tutorials:

**Foundation**
- Templating with Nunjucks
- Adding Structured Components with Metalsmith MDN

**Structured Content**
- Building Sectioned Webpages
- Introducing the Structured Content Starter
- The Anatomy of Section Components

**Advanced**
- How the Bundled Components Plugin Works
- Metalsmith Redux: Conclusion

## Key Concepts

### Sectioned Pages

Traditional static sites use markdown body content. Sectioned pages define all content in frontmatter as structured data:

```yaml
---
sections:
  - sectionType: hero
    text:
      title: Welcome
  - sectionType: text-only
    text:
      title: About
      prose: Content here.
---
```

This enables reusable components, consistent styling, and build-time optimization.

### Component Dependency Bundler

The `metalsmith-bundled-components` plugin:

1. Scans pages to identify used sections
2. Reads component manifests for dependencies
3. Bundles only required CSS/JS
4. Applies PostCSS processing

### Manifest Files

Each component declares its dependencies:

```json
{
  "name": "hero",
  "type": "section",
  "styles": ["hero.css"],
  "scripts": ["hero.js"],
  "requires": ["text", "image", "ctas", "commons"]
}
```

### Container Fields Pattern

All sections support common wrapper configuration:

```yaml
containerFields:
  inContainer: true
  isAnimated: true
  background:
    color: "#f5f5f5"
    image: /path/to/image.jpg
    imageScreen: none
  noMargin:
    top: false
    bottom: false
  noPadding:
    top: false
    bottom: false
```

## Starter Repository

**Micro Starter**: https://github.com/wernerglinka/microStarter

A minimal foundation with:
- text-only section
- Core partials (text, ctas, button, image)
- Complete build infrastructure
- Ready for component additions
