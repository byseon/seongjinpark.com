# CLAUDE.md — Project Conventions

## Project

Academic homepage for Seongjin Park. Static site built with Quarto.

- Domain: https://seongjinpark.com
- Repo: https://github.com/byseon/seongjinpark.com

## Tech Stack

- Quarto (static site generator)
- HTML/CSS (cosmo theme + custom styles)
- GitHub Pages (deployment)

## Commands

- `quarto preview` — local dev server with live reload
- `quarto render` — build site to docs/
- `quarto publish gh-pages` — deploy to GitHub Pages

## File Conventions

- Pages are `.qmd` files (Quarto Markdown)
- Publications data in `publications.yml` (YAML structure)
- Publications page (`publications.qmd`) uses HTML with CSS classes from styles.css
- Notes are in `notes/YYYY-MM-DD-title/index.qmd` format
- CSS classes: .software-grid, .software-card, .pub-year, .pub-entry, .pub-title, .pub-authors, .pub-venue, .pub-links, .keyword-tag, .btn-row
- Internal links use .html extensions (Quarto renders .qmd → .html)

## Style Guidelines

- Minimal, clean, academic design
- No stock photos or decorative clutter
- Navy accent (#1e3a5f), steel blue links (#2d5986)
- IBM Plex Sans body font, JetBrains Mono for code
- Light and dark mode supported

## Important Rules

- Do NOT invent CV content — the CV page is a placeholder with PDF download
- Do NOT add external JavaScript or CMS dependencies
- Do NOT add database dependencies
- Keep the site static and self-contained
- Obfuscate email addresses (use [at] notation, no mailto: links)
- Publications use the pub-* CSS classes for consistent styling
- Software cards use the software-* CSS classes

## Color Palette

| Element | Light | Dark |
|---------|-------|------|
| Primary | #1e3a5f | #1e3a5f |
| Links | #2d5986 | #539bf5 |
| Body text | #2c3e50 | #e6edf3 |
| Background | #ffffff | #0d1117 |
| Borders | #e8eaed | #30363d |
