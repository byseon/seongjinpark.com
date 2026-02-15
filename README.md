# seongjinpark.com

Academic homepage for **Seongjin Park** — researcher in phonetics, speech technology, pronunciation assessment, ASR, and educational NLP.

- Live site: <https://seongjinpark.com>
- Repository: <https://github.com/byseon/seongjinpark.com>
- Google Scholar: <https://scholar.google.com/citations?user=-Bc2U_oAAAAJ&hl=en>

Built with [Quarto](https://quarto.org/) and deployed via GitHub Pages.

---

## Prerequisites

You need **one** tool installed:

- [Quarto CLI](https://quarto.org/docs/get-started/) v1.3 or later

Verify with:

```bash
quarto --version
```

**Install options:**

| Platform | Command |
|----------|---------|
| macOS (Homebrew) | `brew install --cask quarto` |
| macOS (manual) | Download `.pkg` from [quarto.org/docs/get-started](https://quarto.org/docs/get-started/) |
| Linux | `wget` the `.deb` or `.tar.gz` from the same page |
| Windows | Download the `.msi` installer |

No other dependencies are required. No Node.js, no Python, no Ruby.

---

## Quick Start

```bash
# Clone the repo
git clone https://github.com/byseon/seongjinpark.com.git
cd seongjinpark.com

# Preview locally (live reload on file save)
quarto preview

# Build the site (output goes to docs/)
quarto render
```

The preview server runs at `http://localhost:XXXX` (port shown in terminal). Every saved change auto-refreshes.

---

## Project Structure

```
seongjinpark.com/
├── _quarto.yml              # Site-wide configuration (nav, theme, metadata)
├── index.qmd                # Home page (bio, keywords, links)
├── cv.qmd                   # CV page (PDF download link)
├── publications.qmd         # Publications page (HTML using pub-* CSS classes)
├── publications.yml         # Publications as structured YAML data
├── software.qmd             # Software catalog (card grid)
├── contact.qmd              # Contact info (email, Scholar, GitHub)
├── notes/                   # Research notes (blog-style)
│   ├── index.qmd            # Auto-generated listing page
│   └── YYYY-MM-DD-title/    # Each note is a folder with:
│       └── index.qmd        #   - frontmatter (title, date, description, categories)
│                             #   - markdown content
├── cv/                      # CV assets
│   └── CV.pdf               # Your actual CV PDF (add manually)
├── styles.css               # Light theme (SCSS layer format for Quarto)
├── styles-dark.css           # Dark theme overrides
├── publication_latest.rdf   # Zotero RDF export (source data for publications)
├── .gitignore               # Excludes .quarto/, .env, .omc/, etc.
├── CLAUDE.md                # Project conventions for AI assistants
├── PROJECT.md               # Original project specification
├── docs/                    # Built site output (served by GitHub Pages)
│   ├── index.html           # Generated HTML pages
│   ├── search.json          # Full-text search index
│   └── sitemap.xml          # Sitemap for search engines
└── docs/plans/              # Design documents and implementation plans
```

### Key files explained

| File | What it does | When to edit |
|------|-------------|--------------|
| `_quarto.yml` | Controls navigation, theme, fonts, metadata | Changing nav items, site title, or adding new top-level pages |
| `styles.css` | All CSS variables, card grids, publication styling | Changing colors, spacing, or layout |
| `publications.qmd` | Renders publications using HTML with CSS classes | Adding/removing/editing publications |
| `publications.yml` | Structured data for each publication | Keeping a machine-readable record (future automation) |
| `software.qmd` | Card grid of software projects | Adding/removing software projects |

---

## How to Maintain This Site

### Add a New Publication

1. Open `publications.qmd`
2. Find the correct year section (or create a new `<div class="pub-year">YEAR</div>` block)
3. Add a new entry following this exact HTML template:

```html
<div class="pub-entry">
<span class="pub-title">Title of the Paper.</span>
<span class="pub-authors">Author A, <strong>Seongjin Park</strong>, Author B</span><br>
<span class="pub-venue"><em>Journal or Conference Name</em> Volume(Issue), Pages</span>
<span class="pub-links"><a href="URL">PDF</a> <a href="URL">Code</a> <a href="URL">DOI</a></span>
</div>
```

4. Also add a corresponding entry in `publications.yml`:

```yaml
- title: "Title of the Paper"
  authors: "Author A, **Seongjin Park**, Author B"
  venue: "Journal or Conference Name"
  year: 2025
  type: journal    # journal, conference, workshop, or thesis
  pages: "1-10"
  links:
    pdf: "https://..."
    code: "https://..."
    doi: "https://doi.org/..."
```

5. Rebuild: `quarto render`

**Rules:**
- Bold your name with `<strong>Seongjin Park</strong>` in the HTML
- Italicize the venue with `<em>...</em>`
- Group publications by year, reverse chronological (newest first)
- The `pub-links` span is optional (omit if no links available)

### Add a New Note / Blog Post

1. Create a folder:

```bash
mkdir -p notes/2025-03-15-your-title
```

2. Create `notes/2025-03-15-your-title/index.qmd`:

```yaml
---
title: "Your Post Title"
date: "2025-03-15"
description: "One-sentence summary of the post."
categories: [research, paper-summary, tools]  # pick relevant ones
---

Your markdown content here. You can use:

- **Bold**, *italic*, `code`
- [Links](https://example.com)
- Images: ![alt text](image.png)
- Code blocks with syntax highlighting
- Math with LaTeX: $E = mc^2$
```

3. The listing page (`notes/index.qmd`) auto-detects new posts. No manual indexing needed.

4. Rebuild: `quarto render`

### Add a New Software Project

1. Open `software.qmd`
2. Add a card inside the `<div class="software-grid">` block:

```html
<div class="software-card">
<h3>repo-name</h3>
<p>One or two sentence description of what this tool does and its research context.</p>
<p class="text-secondary">Python</p>
<div class="card-links"><a href="https://github.com/byseon/repo-name">GitHub</a></div>
</div>
```

3. Rebuild: `quarto render`

### Update Your CV

Replace the file at `cv/CV.pdf` with your updated PDF. No other changes needed.

### Change Colors or Fonts

All design tokens are CSS variables in `styles.css`:

```css
:root {
  --color-primary: #1e3a5f;         /* Navy accent */
  --color-link: #2d5986;            /* Steel blue links */
  --color-link-hover: #1e3a5f;      /* Link hover */
  --color-body-text: #2c3e50;       /* Body text */
  --color-secondary-text: #546e7a;  /* Muted text */
  --color-bg: #ffffff;              /* Background */
  --color-code-bg: #f5f7fa;         /* Code block background */
  --color-border: #e8eaed;          /* Borders */
  --content-max-width: 900px;       /* Content width */
}
```

Dark mode overrides are in `styles-dark.css` with the same variable names.

Fonts are set in `_quarto.yml`:

```yaml
mainfont: "IBM Plex Sans"
monofont: "JetBrains Mono"
fontsize: "17px"
```

### Add a New Top-Level Page

1. Create `newpage.qmd` in the project root
2. Add it to the navbar in `_quarto.yml`:

```yaml
navbar:
  left:
    - href: newpage.qmd
      text: "New Page"
```

3. Rebuild: `quarto render`

---

## Deployment

### GitHub Pages (current setup)

The site is served from the `docs/` directory on the `main` branch.

**To deploy:**

```bash
# Build the site
quarto render

# Commit the built output
git add docs/
git commit -m "build: update site"
git push
```

GitHub Pages picks up changes automatically.

**Alternative** (uses a separate `gh-pages` branch — keeps `docs/` out of `main`):

```bash
quarto publish gh-pages
```

### GitHub Pages setup (one-time)

In the repository settings on GitHub:
1. Go to **Settings > Pages**
2. Set **Source** to "Deploy from a branch"
3. Set **Branch** to `main` and folder to `/docs`
4. Optionally set custom domain to `seongjinpark.com`

---

## CSS Classes Reference

These classes are defined in `styles.css` and used in `.qmd` files:

| Class | Used in | Purpose |
|-------|---------|---------|
| `.pub-year` | publications.qmd | Year heading with bottom border |
| `.pub-entry` | publications.qmd | Single publication wrapper (hover highlight) |
| `.pub-title` | publications.qmd | Publication title (bold) |
| `.pub-authors` | publications.qmd | Author list |
| `.pub-venue` | publications.qmd | Journal/conference name (italic) |
| `.pub-links` | publications.qmd | Inline PDF/Code/DOI links |
| `.software-grid` | software.qmd | 3-column responsive card grid |
| `.software-card` | software.qmd | Individual project card (hover lift) |
| `.card-links` | software.qmd | Links inside software cards |
| `.keyword-tag` | index.qmd | Inline research keyword badge |
| `.btn-row` | index.qmd | Flexbox button row |
| `.text-secondary` | various | Muted/secondary text color |

---

## Quarto-Specific Notes

### SCSS Layer Boundaries

The `styles.css` and `styles-dark.css` files contain special comments:

```css
/*-- scss:defaults --*/
/*-- scss:rules --*/
```

These are **required** by Quarto's theme system. Do not remove them. All custom CSS goes after the `/*-- scss:rules --*/` line.

### Theme Configuration

The site uses Quarto's dual-theme system:

```yaml
theme:
  light: [cosmo, styles.css]    # cosmo base + light overrides
  dark: [cosmo, styles-dark.css] # cosmo base + dark overrides
```

The `cosmo` theme is a Bootstrap 5 theme. Custom CSS overrides Bootstrap defaults.

### Render Exclusions

`_quarto.yml` excludes non-page files from rendering:

```yaml
render:
  - "*.qmd"
  - "notes/"
  - "!PROJECT.md"
  - "!CLAUDE.md"
  - "!README.md"
```

If you add new `.md` files that should NOT become site pages, add them here with `!` prefix.

---

## Troubleshooting

| Problem | Solution |
|---------|----------|
| `quarto render` fails with SCSS error | Check that `styles.css` has `/*-- scss:defaults --*/` and `/*-- scss:rules --*/` comments |
| New note doesn't appear in listing | Verify folder name is `notes/YYYY-MM-DD-title/index.qmd` with correct frontmatter |
| Page appears in nav but shows 404 | Check `_quarto.yml` navbar `href` matches the `.qmd` filename |
| Fonts look wrong | Clear browser cache; verify Google Fonts import in `styles.css` |
| Dark mode not working | Ensure `styles-dark.css` has SCSS layer boundaries |
| `docs/` not updating | Run `quarto render` before committing |

---

## Future Enhancements

- **Zotero auto-import**: Script to convert `.bib` export to `publications.yml` and regenerate `publications.qmd`
- **Auto-build CV**: Generate CV from structured YAML data
- **GitHub release sync**: Auto-update Software page when new releases are published
- **Citation export**: Add BibTeX/RIS download buttons per publication
- **Obsidian integration**: Link research knowledge graph to published notes
- **Self-hosted fonts**: Replace Google Fonts with local `.woff2` files for privacy and speed

---

## License

Content copyright Seongjin Park. Site source available for reference.
