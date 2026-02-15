# seongjinpark.com

Academic homepage for Seongjin Park — phonetics, speech technology, pronunciation assessment.

Built with [Quarto](https://quarto.org/).

## Prerequisites

- [Quarto CLI](https://quarto.org/docs/get-started/) (v1.3+)

## Local Development

```bash
quarto preview
```

This starts a local server with live reload.

## Build

```bash
quarto render
```

Output is written to `docs/`.

## Deploy

This site is deployed via GitHub Pages from the `docs/` directory.

To publish:

```bash
quarto publish gh-pages
```

Or push to the `main` branch — GitHub Pages serves from `docs/` on main.

## Project Structure

```
├── _quarto.yml          # Site configuration
├── index.qmd            # Home page
├── cv.qmd               # CV with PDF download
├── publications.qmd     # Publications (rendered from publications.yml)
├── publications.yml     # Structured publication data
├── software.qmd         # Software catalog
├── contact.qmd          # Contact information
├── notes/               # Research notes (blog-style)
│   ├── index.qmd        # Auto-listing page
│   └── YYYY-MM-DD-*/    # Individual posts
├── cv/                  # CV assets
│   └── CV.pdf           # Your CV (add manually)
├── styles.css           # Light theme
├── styles-dark.css      # Dark theme
└── docs/                # Built site output
```

## Adding Content

### New Publication

Edit `publications.qmd` and add an entry following the existing HTML structure. Also update `publications.yml` for the structured data record.

### New Note

Create a new directory under `notes/`:

```bash
mkdir notes/YYYY-MM-DD-title
```

Create `notes/YYYY-MM-DD-title/index.qmd` with frontmatter:

```yaml
---
title: "Your Title"
date: "YYYY-MM-DD"
description: "Brief description"
categories: [category]
---
```

### Update CV

Replace `cv/CV.pdf` with your current CV.

## License

Content copyright Seongjin Park. Site source available for reference.
