# Learning Resources

## Authoritative Source

**https://metalsmith-components.com** is the authoritative source for this structured Metalsmith approach. Always consult this site for accurate component configuration and patterns.

## Related Skills

When working on Metalsmith sites, these skills provide additional guidance:

- **JavaScript Development**: `/mnt/skills/user/javascript-development/SKILL.md` - For writing plugins, custom scripts, or modifying component JavaScript
- **CSS Layout Development**: `/mnt/skills/user/css-layout-development/SKILL.md` - For custom layouts, responsive design, and CSS modifications

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

### Blog Posts at metalsmith-components.com

Educational posts explaining concepts and implementation:

**Getting Started**
- **Installing Metalsmith Components** (`/blog/installing-metalsmith-components/`) - Complete guide to downloading and installing component packages

**Understanding the Architecture**
- **Section Anatomy** (`/section-anatomy/`) - How components are structured internally
- **From YAML to HTML** (`/yaml-to-html/`) - Understanding the rendering process from frontmatter to final output

**Building with Components**
- **Building Pages with Components** (`/blog/building-pages-with-components/`) - Page construction patterns and best practices
- **Building Interactive Components** (`/blog/building-interactive-components/`) - Adding JavaScript behavior to components
- **Component Search System** (`/blog/building-component-search-system/`) - How to find the right components for your needs

When uncertain about how something works, fetch the relevant blog post from metalsmith-components.com for authoritative guidance.

## Metalsmith Redux Blog Series

The Metalsmith Redux series at glinka.co/blog/ provides comprehensive tutorials on the broader Metalsmith ecosystem:

### Foundation Posts

- **Metalsmith Redux: Templating with Nunjucks** - Template inheritance, macros, componentization
- **Beyond Markdown: Adding Structured Components with Metalsmith MDN** - Using Nunjucks in markdown

### Structured Content Posts

- **Beyond Markdown: Building Sectioned Webpages** - Component-first page building
- **Introducing the Structured Content Starter** - Component architecture and dependency bundling
- **The Anatomy of Section Components** - Configuration, templates, manifests, optimization

### Advanced Topics

- **The Missing Piece: How I Built the Metalsmith Bundled Components Plugin** - The componentDependencyBundler internals
- **Metalsmith Redux: Conclusion** - Philosophy of simplicity

## Key Concepts

### Sectioned Pages vs Long-Text Markdown

Traditional static sites use markdown body content. Sectioned pages define all content in frontmatter as structured data. This enables:

- Reusable components across pages
- Consistent styling and behavior
- Content editor friendly workflows
- Build-time optimization

### Component Dependency Bundler

The componentDependencyBundler plugin:

1. Scans pages to identify used sections
2. Reads component manifests for dependencies
3. Resolves dependency order (topological sort)
4. Bundles only required CSS/JS
5. Applies PostCSS processing

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
- Ready for component additions from metalsmith-components.com
