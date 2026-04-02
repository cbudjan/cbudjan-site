# cbudjan.com

Personal academic website for Christoph Budjan, built with [Hugo](https://gohugo.io/) and deployed via GitHub Pages at [cbudjan.com](https://cbudjan.com).

## Stack

- **Static site generator:** Hugo with a custom theme (`themes/cbudjan`)
- **Hosting:** GitHub Pages with a custom domain (`cbudjan.com`)
- **Deployment:** GitHub Actions — pushes to `main` automatically build and deploy the site
- **Icons:** Font Awesome 6 Free (CDN) for social/academic icons (ORCID, GitHub, Google Scholar, X/Twitter)
- **Fonts:** IBM Plex Sans (body) and DM Serif Display (headings) via Google Fonts

## Structure

```
├── .github/workflows/deploy.yml   # Auto-deploy to GitHub Pages on push to main
├── hugo.toml                      # Site config (title, baseURL, nav, social links)
├── content/
│   ├── _index.md                  # Home page (hero text + research interests)
│   ├── current-research/          # Current research projects
│   ├── past-research/             # Past research projects
│   └── contact.md                 # Contact page
├── static/
│   ├── CNAME                      # Custom domain for GitHub Pages
│   └── img/                       # Images (project banners, microscopy)
└── themes/cbudjan/
    ├── layouts/                   # HTML templates
    └── assets/css/main.css        # All styles (CSS custom properties for easy theming)
```

## Local development

```bash
# Install Hugo (macOS)
brew install hugo

# Preview locally with live reload
hugo server -D
# → open http://localhost:1313
```

Pushing to `main` triggers the GitHub Actions workflow, which builds the site and deploys it to GitHub Pages.
