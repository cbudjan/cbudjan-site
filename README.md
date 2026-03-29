# cbudjan.com — Static Site Migration Guide

A complete guide for migrating from Squarespace to a self-hosted static site
on GitHub Pages, using either Hugo or Jekyll with the custom `cbudjan` theme.

---

## Directory structures

### Hugo
```
my-site/
├── .github/workflows/deploy.yml   # Auto-deploy to GitHub Pages
├── hugo.toml                      # Site config (title, nav, social links)
├── content/
│   ├── _index.md                  # Home page (hero text + interests)
│   ├── current-research/
│   │   ├── _index.md              # Section intro text
│   │   ├── hem-gst.md             # Project: Hemogenic Gastruloids
│   │   ├── dev-robustness.md      # Project: Developmental Robustness
│   │   └── in-silico-gst.md      # Project: In Silico Modeling
│   ├── past-research/
│   │   ├── _index.md
│   │   └── somitoids.md           # Past project example
│   └── contact.md
└── themes/cbudjan/
    ├── layouts/
    │   ├── _default/baseof.html   # Base HTML wrapper
    │   ├── index.html             # Home page template
    │   ├── research/
    │   │   ├── list.html          # Research listing grid
    │   │   └── single.html        # Individual project page
    │   └── partials/
    │       ├── nav.html
    │       └── footer.html
    └── assets/css/main.css        # All styles

```

### Jekyll
```
my-site/
├── .github/workflows/deploy.yml   # Auto-deploy to GitHub Pages
├── _config.yml                    # Site config
├── Gemfile                        # Ruby dependencies
├── _layouts/
│   ├── default.html               # Base HTML wrapper
│   ├── home.html                  # Home page
│   ├── research-list.html         # Research listing grid
│   └── project.html               # Individual project page
├── _includes/
│   ├── nav.html
│   └── footer.html
├── _research/                     # Jekyll collection
│   ├── hem-gst.md
│   ├── dev-robustness.md
│   └── in-silico-gst.md
├── assets/
│   ├── css/main.css               # All styles (copy from hugo theme)
│   └── img/
│       ├── logo.png               # Your saddle-node logo
│       └── projects/              # Project banner + gallery images
├── index.md                       # Home page
├── current-research.md            # Research listing page
├── past-research.md
└── contact.md
```

---

## Quick start

### Hugo

```bash
# 1. Install Hugo (macOS)
brew install hugo

# 2. Create new site
hugo new site my-site
cd my-site

# 3. Copy theme files into themes/cbudjan/
mkdir -p themes/cbudjan
cp -r /path/to/theme/* themes/cbudjan/

# 4. Copy hugo.toml to site root, edit with your details

# 5. Add your content
cp content/_index.md my-site/content/
# ... add project .md files

# 6. Add your images to static/img/

# 7. Preview locally
hugo server -D
# → open http://localhost:1313

# 8. Push to GitHub, Actions will auto-deploy
```

### Jekyll

```bash
# 1. Install Ruby (macOS — via rbenv recommended)
brew install rbenv ruby-build
rbenv install 3.2.0 && rbenv global 3.2.0

# 2. Install Bundler
gem install bundler

# 3. Install dependencies
cd my-site
bundle install

# 4. Preview locally
bundle exec jekyll serve --livereload
# → open http://localhost:4000

# 5. Push to GitHub, Actions will auto-deploy
```

---

## Content migration from Squarespace

### Step 1 — Export raw content
Go to **Settings → Advanced → Import/Export → Export XML**.
This gives you an XML file with all page content. The formatting is messy
but body text is intact. For a small site like yours (~6 pages + 3 projects)
it's faster to copy-paste directly from the live site into Markdown files.

### Step 2 — Front matter per content type

**Home page (`_index.md` / `index.md`)**
```yaml
---
greeting: "Hello."
hero_images:
  - /img/gst-d3-tbxt-594.jpg
  - /img/glr-hem-kdr647-5d.jpg
  - /img/gst-hem-kdr647-d9.jpg
interests:
  - title: "Principles of cell fate decision making"
    body: |
      Your paragraph text here...
      > Blockquote text here...
---
```

**Research project**
```yaml
---
title: "Derivation of Human HSPCs from Hemogenic Gastruloids"
tag: "HemGST project"        # shown as small label on card + detail page
image: /img/projects/hem-gst-banner.jpg   # banner + card thumbnail
gallery:
  - /img/projects/hem-gst-01.jpg
  - /img/projects/hem-gst-02.jpg
weight: 2                    # controls order in the grid
---
Your project body text in Markdown...
```

### Step 3 — Images
Copy all your microscopy images and data figures into:
- Hugo: `static/img/` → served at `/img/filename.jpg`
- Jekyll: `assets/img/` → served at `/assets/img/filename.jpg`

Your saddle-node logo goes in:
- Hugo: `themes/cbudjan/assets/img/logo.png`
- Jekyll: `assets/img/logo.png`

Recommended: export your Squarespace images at max resolution and use
Hugo's built-in image processing or a script to generate optimized WebP
versions for web delivery.

---

## Custom domain (cbudjan.com)

1. In your GitHub repo: **Settings → Pages → Custom domain** → enter `cbudjan.com`
2. GitHub will create a `CNAME` file in your repo automatically.
3. At your DNS registrar (wherever you bought the domain), update records:

```
A     @    185.199.108.153
A     @    185.199.109.153
A     @    185.199.110.153
A     @    185.199.111.153
CNAME www  yourgithubusername.github.io.
```

4. Enable **Enforce HTTPS** in GitHub Pages settings (available once DNS propagates, ~10 min–2 hours).
5. Cancel Squarespace subscription — domain lives at your registrar, not Squarespace.

---

## Icon sets used

- **Font Awesome 6 Free** (CDN) — ORCID, GitHub, Google Scholar, X/Twitter
  - CDN: `https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css`
  - License: Font Awesome Free License (free for any use, including commercial)
  - Icons used: `fa-orcid`, `fa-github`, `fa-x-twitter`, `fa-graduation-cap`

No other icon dependencies. Social links are purely Font Awesome classes —
no SVG management required.

---

## Design tokens (easy customization)

All visual parameters are CSS custom properties at the top of `main.css`:

```css
:root {
  --bg:           #f8f7f4;   /* warm off-white page background */
  --nav-bg:       #141414;   /* near-black nav/footer */
  --accent-warm:  #8b4513;   /* blockquote left border (saddle brown) */
  --rule:         #d8d5cf;   /* horizontal rules, card borders */
  --max-w:        920px;     /* content column width */
  --font-serif:   'DM Serif Display', Georgia, serif;
  --font-sans:    'IBM Plex Sans', system-ui, sans-serif;
}
```

To change the accent color, blockquote style, or max content width,
edit only these variables — nothing else needs to change.

---

## Extending the site

**Add a Publications page:**
Create `content/publications.md` (Hugo) or `publications.md` (Jekyll).
Use a BibTeX → Markdown converter (e.g. `academic-cli`, `bib2md`) to
auto-generate entries from your Paperpile `.bib` export.

**Add a CV/Resume:**
Link your CV PDF directly: put `cv.pdf` in `static/` (Hugo) or `assets/` (Jekyll)
and link to `/cv.pdf` from the nav or contact page.

**Add a News/Updates section:**
Both Jekyll and Hugo have native blog/post support. Create `_posts/` (Jekyll)
or `content/news/` (Hugo) and add the News link to the nav in `_config.yml`
or `hugo.toml`.
