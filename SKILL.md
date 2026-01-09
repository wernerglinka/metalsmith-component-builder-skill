---
name: metalsmith-component-builder
version: 1.0.0
description: Build static websites using Metalsmith's component-based architecture without knowing Metalsmith internals. Use when users want to create professional websites using sectioned pages and reusable components, including phrases like "build me a website", "create a landing page", "add a new page", "add a section", or when working with the Metalsmith Micro Starter or components from metalsmith-components.com. Supports three paths based on user's technical comfort level, from complete novice (Claude builds everything as downloadable ZIP) to Claude Desktop with MCP (direct filesystem access) to full local development.
---

# Metalsmith Component Website Builder

Build professional static websites using Metalsmith's component-based architecture through conversational guidance. This skill adapts to the user's technical comfort level.

## Authoritative Resource

**https://metalsmith-components.com is the authoritative source** for this structured Metalsmith approach. When answering questions about components, configuration, or best practices:

1. **Reference pages** (`/references/sections/` and `/references/partials/`) - Complete documentation for each component with live examples
2. **Blog posts** (`/blog/`) - Educational content explaining concepts and patterns
3. **Installation guide** (`/blog/installing-metalsmith-components/`) - How to add components

If uncertain about component configuration, search or fetch from metalsmith-components.com.

### Key Blog Posts at metalsmith-components.com

Fetch these posts when questions arise:

- `/blog/installing-metalsmith-components/` - Download and install component packages
- `/section-anatomy/` - How components are structured internally
- `/yaml-to-html/` - The rendering process from frontmatter to final output
- `/blog/building-pages-with-components/` - Page construction patterns
- `/blog/building-interactive-components/` - Adding JavaScript behavior
- `/blog/building-component-search-system/` - Finding the right components

**Related Skills**: For JavaScript code, read `/mnt/skills/user/javascript-development/SKILL.md`. For CSS layouts, read `/mnt/skills/user/css-layout-development/SKILL.md`.

---

## Phase 0: Path Selection (DO NOT SKIP)

Before anything else, determine which workflow path suits the user. Ask:

"Have you built websites before using command-line tools like Node.js, or would this be your first time working with code?"

Based on their response, select one of three paths:

### Path A: Complete Novice (Claude Builds Everything)

**For users who**: Have never used command line, are uncomfortable with technical setup, just want a website without learning development tools.

**How it works**: Claude creates the entire website as downloadable files. User uploads to GitHub via web interface, connects Netlify with a few clicks. No local tools required.

**Limitations**: Slower iteration (edit → download → upload → deploy → view). No live preview during development.

→ Go to [Path A Workflow](#path-a-workflow-claude-builds-everything)

### Path B: Claude Desktop with MCP

**For users who**: Have Claude Desktop installed with MCP servers configured, want Claude to work directly with their local files.

**How it works**: Claude reads/writes files directly to user's computer, can pull content from Google Drive, handles git operations. User just talks to Claude.

**Requirements**: Claude Desktop with filesystem MCP (and optionally git, Google Drive MCPs).

→ Go to [Path B Workflow](#path-b-workflow-claude-desktop-with-mcp)

### Path C: Local Development

**For users who**: Are comfortable with terminal/command line, want full development experience with live reload, may already have Node.js installed.

**How it works**: Traditional local development workflow with npm, live preview server, direct file editing.

→ Go to [Path C Workflow](#path-c-workflow-local-development)

---

## What to Expect (Explain to All Users)

Before starting any path, ensure the user understands what's involved:

"Building a website this way involves a few pieces:

**The Website Files** - I'll help you create the pages and content. These are just text files with a specific structure.

**GitHub (free account)** - This stores your website files online and tracks changes. Think of it as a save system for your site.

**Netlify (free account)** - This takes your files from GitHub and turns them into a live website anyone can visit. It automatically updates when you make changes.

**Your content** - Text, images, and information about what you want on the site.

No sensitive data is required. GitHub and Netlify accounts just need an email address."

---

# Path A Workflow: Claude Builds Everything

For complete novices. Claude creates all files, user uploads via web interfaces.

## A1: Account Setup

Guide user through creating accounts if needed:

**GitHub Account**
1. Go to github.com
2. Click "Sign up"
3. Enter email, create password, choose username
4. Verify email

**Netlify Account**
1. Go to netlify.com
2. Click "Sign up"
3. Choose "Sign up with GitHub" (recommended)
4. Authorize the connection

## A2: Discovery Dialog (DO NOT SKIP)

Before building, understand what the user needs through conversation.

### About the Website
- What is this website for? (business, portfolio, nonprofit, personal blog, event)
- Who is the audience?
- What should visitors do? (contact you, buy something, learn, sign up)

### Homepage
- What first impression should visitors get?
- What's the most important message or call to action?
- Any specific images or video in mind?

### Other Pages
- What pages beyond the homepage? (About, Services, Contact, Blog, Team, Pricing)
- How much content exists already vs. needs to be written?

### Content Sources
- Where is your content now? (Google Docs, Word files, written notes, nowhere yet)
- Do you have images ready? Where are they stored?
- Any logos or brand colors?

### Technical Needs
- Need a contact form?
- Blog with regular posts?
- Any special features? (search, image galleries, maps)

Document requirements before proceeding to build.

## A3: Component Selection

Based on discovery, determine which components are needed.

**Included in micro starter:**
- `text-only` - Text content with optional CTAs

**Download from metalsmith-components.com if needed:**

| Category | Components |
|----------|-----------|
| Content | hero, banner, multi-media, columns, compound |
| Media | image-only, video-only, audio-only, image-grid, image-compare |
| Interactive | accordion, flip-cards, simple-slider, hero-slider |
| Lists | blurbs, manual-card, collection-list, logos-list, team-grid |
| Specialized | testimonial, pricing-table, stats, steps, timeline, maps, search |

Claude downloads required components and includes them in the final ZIP.

## A4: Claude Builds the Site

Claude creates the complete website:

1. Start with the micro starter from https://github.com/wernerglinka/microStarter
2. Download any additional components needed (Claude handles this)
3. Modify content files based on discovery:
   - `lib/data/site.json` - site title, description, owner
   - `src/index.md` - homepage with user's content
   - `src/*.md` - additional pages
4. Add user's images to `lib/assets/images/`
5. Package everything as a ZIP for download

Provide the ZIP to the user.

## A5: Upload to GitHub

Guide user through web-based upload:

1. Go to github.com and sign in
2. Click "+" icon (top right) → "New repository"
3. Name it (e.g., "my-website")
4. Keep it Public
5. Check "Add a README file"
6. Click "Create repository"
7. Click "Add file" → "Upload files"
8. Drag the contents of the unzipped folder into the upload area
9. Click "Commit changes"

## A6: Deploy on Netlify

Guide user through Netlify connection:

1. Go to netlify.com and sign in
2. Click "Add new site" → "Import an existing project"
3. Click "Deploy with GitHub"
4. Select the repository
5. Verify build settings:
   - Build command: `npm run build`
   - Publish directory: `build`
6. Click "Deploy site"
7. Wait 1-2 minutes, then click the URL to see the live site

## A7: Making Changes

When user wants to edit:

**Option 1: Return to Claude**
- Describe changes needed
- Claude provides updated files
- User uploads to GitHub (replacing old files)
- Netlify auto-rebuilds

**Option 2: Edit on GitHub directly** (for simple text changes)
- Navigate to file in GitHub
- Click pencil icon to edit
- Make changes to the YAML/markdown
- Click "Commit changes"
- Netlify auto-rebuilds

---

# Path B Workflow: Claude Desktop with MCP

For users with Claude Desktop and MCP servers configured.

## B1: Verify MCP Setup

Check available MCP servers:

**Required:**
- Filesystem MCP - to read/write local files

**Recommended:**
- Git MCP - for version control
- Google Drive MCP - to pull content from Docs

If filesystem MCP isn't available, fall back to Path A.

## B2: Environment Check

Determine what's available:
- Does user have Node.js 18+? (`node --version`)
- Does user have git? (`git --version`)

If yes, can run local dev server. If no, will deploy to see results.

## B3: Project Setup

Ask: "Where would you like your website project folder?"

**If user has git and Node.js:**
```bash
git clone https://github.com/wernerglinka/microStarter.git my-website
cd my-website
npm install
npm start
```

**If not**, Claude creates the project structure directly via filesystem MCP.

## B4: Discovery Dialog (DO NOT SKIP)

Same as Path A - understand what the user needs:
- Website purpose and audience
- Homepage requirements
- Additional pages
- Content sources
- Technical needs

## B5: Content Gathering

If Google Drive MCP is available:
- Ask what documents contain their content
- Read directly from Google Docs
- Extract text for pages

If not:
- Ask user to paste content
- Or provide file paths to local documents

## B6: Component Selection & Download

Based on discovery, determine needed components.

Download additional components:
```bash
# From project root
curl -L https://metalsmith-components.com/downloads/sections/hero.zip -o hero.zip
unzip hero.zip
cd hero
./install.sh
cd ..
```

## B7: Build Pages

Using filesystem MCP, create/modify files:

1. Update `lib/data/site.json` with site metadata
2. Create page files in `src/` with user's content
3. Organize images in `lib/assets/images/`

## B8: Preview & Iterate

If dev server is running:
- View at http://localhost:3000
- Gather feedback
- Modify files directly
- Changes appear immediately

If no dev server, proceed to deployment to see results.

## B9: Deploy

Initialize git and push:
```bash
git init
git add .
git commit -m "Initial site"
```

Create GitHub repo (user does via web), then:
```bash
git remote add origin https://github.com/USERNAME/REPO.git
git push -u origin main
```

Connect Netlify same as Path A.

---

# Path C Workflow: Local Development

For users comfortable with command line.

## C1: Environment Check

Verify prerequisites:
```bash
node --version    # Requires 18+
npm --version
git --version
```

If missing, guide installation:
- **Node.js**: Download from nodejs.org or use nvm
- **Git**: Download from git-scm.com

## C2: Account Setup

Verify or create:
- GitHub account (github.com)
- Netlify account (netlify.com) - recommend "Sign up with GitHub"

## C3: Project Setup

```bash
# Clone the micro starter
git clone https://github.com/wernerglinka/microStarter.git my-website
cd my-website

# Install dependencies
npm install

# Start development server
npm start
```

Confirm running at `http://localhost:3000` before proceeding.

## C4: Discovery Dialog (DO NOT SKIP)

With dev server running, discuss requirements:
- Website purpose and audience
- Homepage requirements
- Additional pages needed
- Content sources
- Technical needs (forms, blog, search)

## C5: Component Selection & Download

Based on discovery, download needed components:

```bash
# Example: download hero section
curl -L https://metalsmith-components.com/downloads/sections/hero.zip -o hero.zip
unzip hero.zip
cd hero
./install.sh
cd ..
rm -rf hero hero.zip
```

The install script:
- Copies files to correct locations
- Checks for dependencies
- Offers to clean up when done

Restart dev server after adding components.

### Available Components

| Category | Components |
|----------|-----------|
| Content | hero, banner, multi-media, columns, compound |
| Media | image-only, video-only, audio-only, image-grid, image-compare |
| Interactive | accordion, flip-cards, simple-slider, hero-slider |
| Lists | blurbs, manual-card, collection-list, logos-list, team-grid |
| Specialized | testimonial, pricing-table, stats, steps, timeline, maps, search |

## C6: Page Building

Create pages in `src/` with YAML frontmatter:

```yaml
---
layout: pages/sections.njk
bodyClasses: page-name

navigation:
  navLabel: Page Name
  navIndex: 1

seo:
  title: Page Title
  description: Page description

sections:
  - sectionType: hero
    # section configuration...
  - sectionType: text-only
    # section configuration...
---
```

See [Page Building Reference](#page-building-reference) for section configuration.

## C7: Preview & Iterate

With live reload running:
1. Edit markdown files in `src/`
2. Preview changes instantly at localhost:3000
3. Gather feedback
4. Refine sections and content
5. Commit progress regularly

```bash
git add .
git commit -m "Add homepage hero and about section"
```

## C8: Create Repository & Deploy

```bash
# Remove link to starter
git remote remove origin

# Create new repo on GitHub (via web), then:
git remote add origin https://github.com/USERNAME/REPO.git
git branch -M main
git push -u origin main
```

Connect Netlify:
1. Log in to netlify.com
2. "Add new site" → "Import an existing project"
3. Select the GitHub repository
4. Build command: `npm run build`
5. Publish directory: `build`
6. Deploy

## C9: Ongoing Development

```bash
npm start          # Dev server with live reload
npm run build      # Production build
npm run serve      # Preview production build
npm run fix        # Format and lint code
```

Commit and push; Netlify auto-deploys.

---

# Page Building Reference

## Page Structure

Every page is a markdown file with YAML frontmatter:

```yaml
---
layout: pages/sections.njk
bodyClasses: page-name

navigation:
  navLabel: Page Name    # Menu label
  navIndex: 1            # Menu order

seo:
  title: Page Title
  description: Page description for search engines
  socialImage: /assets/images/social.jpg

sections:
  - sectionType: component-name
    # section configuration
---
```

## Section Configuration Pattern

All sections follow this pattern:

```yaml
- sectionType: component-name
  containerTag: section          # HTML element: section, article, aside, div
  id: optional-id
  classes: optional-classes
  isDisabled: false              # Set true to hide without removing
  containerFields:
    inContainer: true            # Wrap in .container
    isAnimated: true             # Enable scroll animations
    background:
      color: '#hex'
      image: /path/to/image.jpg
      imageScreen: none          # light, dark, none
    noMargin:
      top: false
      bottom: false
    noPadding:
      top: false
      bottom: false
  text:
    leadIn: Eyebrow text
    title: Main Title
    titleTag: h2                 # h1-h6
    subTitle: Subtitle
    prose: |-
      Markdown content here.
      Multiple paragraphs supported.
  ctas:
    - url: /path
      label: Button Text
      isButton: true
      buttonStyle: primary       # primary, secondary, tertiary, inverted
```

## Common Section Examples

### Hero Section
```yaml
- sectionType: hero
  containerFields:
    background:
      image: /assets/images/hero-bg.jpg
      imageScreen: dark
  text:
    title: Welcome to Our Site
    prose: Your compelling introduction here.
  ctas:
    - url: /contact
      label: Get Started
      isButton: true
      buttonStyle: primary
  image:
    src: /assets/images/hero-image.jpg
    alt: Description of image
```

### Multi-Media Section
```yaml
- sectionType: multi-media
  text:
    title: About Us
    prose: Our story and mission.
  media:
    type: image
    src: /assets/images/about.jpg
    alt: About image
  isReverse: true              # Image on left, text on right
```

### Text-Only Section
```yaml
- sectionType: text-only
  text:
    title: Our Services
    prose: |-
      Description of what we offer.
      
      - Service one
      - Service two
      - Service three
```

For complete configuration options, consult reference pages at metalsmith-components.com.

---

# Troubleshooting

**YAML errors**: Check indentation. Use 2 spaces consistently. No tabs.

**Section not rendering**: Verify `sectionType` matches folder name in `lib/layouts/components/sections/`.

**Images not showing**: Paths must start with `/assets/`. Files go in `lib/assets/images/`.

**Styles missing**: Restart dev server after adding new components.

**Git push rejected**: Verify remote URL with `git remote -v`. Ensure repository exists on GitHub.

**Netlify build fails**: Check build log. Verify `npm run build` works locally. Confirm build command and publish directory settings.

---

# Learning Resources

## Metalsmith Components (metalsmith-components.com)

- **Reference pages** - Complete docs for each component
- **Blog posts** - Concepts and patterns explained
- **Installation guide** - Component download and setup

## Metalsmith Redux Series (glinka.co/blog/)

- Templating with Nunjucks
- Building Sectioned Webpages
- The Anatomy of Section Components
- How the Bundled Components Plugin Works

See `references/learning-resources.md` for complete resource list.
