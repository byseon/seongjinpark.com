You are a research website bootstrap agent.

Your task is to generate a COMPLETE, READY-TO-DEPLOY academic website
for a researcher.

OWNER
-----
Name: Seongjin Park
Primary GitHub: https://github.com/byseon
Homepage repo: https://github.com/byseon/seongjinpark.com
Google Scholar: https://scholar.google.com/citations?user=-Bc2U_oAAAAJ&hl=en

DOMAIN
------
https://seongjinpark.com

PURPOSE
-------
This is an academic homepage.

Primary emphasis:
- CV
- Publications
- Software
Secondary:
- research notes
- paper summaries

Tone:
professional, minimal, reproducible, PI-level.

We prefer clarity over design complexity.

TECHNICAL REQUIREMENTS
----------------------
Use Quarto.

The output must be a full repository structure that can be pushed
directly to GitHub and deployed via GitHub Pages or Cloudflare Pages.

No external CMS.
No databases.

CONTENT REQUIREMENTS
--------------------

### Home
Short bio.
Research keywords:
phonetics, speech technology, pronunciation assessment,
ASR, educational NLP.

Link to:
CV, publications, software, Google Scholar, GitHub.

### CV
Create a placeholder page.

Add:
"Download CV (PDF)"

The PDF will later live at:

/cv/CV.pdf

Do NOT invent CV content.

### Publications
Create a structured page.

Use the Google Scholar link to design placeholders.

If scraping is not possible, create representative mock entries like:

- title
- authors
- venue
- year
- links (pdf / code / doi if available)

Make it easy to replace later.

### Software
Create a catalog-style page.

Each entry should include:
- name
- one-line description
- GitHub link

Use realistic future repo names such as:
praat-phonetics-toolkit
pronunciation-eval-pipeline
l2-acoustic-analysis

Take a look at old legacy github repo: https://github.com/seongjinpark-88 and clone/fork the repository you think is relevant/useful to add to the initial webpage.

### Notes
Prepare a blog/news style list.
Add 2–3 example placeholder posts:
- research update
- paper summary
- tool release

### Contact
Academic email placeholder.
Links to Scholar and GitHub.

DESIGN RULES
------------
Minimal.
Clean.
Academic.
No stock photos.
No decorative clutter.

Discuss with frontend engineer to pick best color theme, UI design, font, etc.

NAVIGATION
----------
Home / CV / Publications / Software / Notes / Contact

REPOSITORY OUTPUT
-----------------
Generate:

_quarto.yml
index.qmd
cv.qmd
publications.qmd
software.qmd
notes/
contact.qmd
styles.css (optional minimal tweaks)

Also include:

README.md explaining how to:
- run locally
- build
- deploy

AUTOMATION IDEAS
----------------
At the end, propose optional future improvements:

- auto import from scholar
- auto build CV
- release sync from GitHub
- citation export

STYLE OF YOUR ANSWER
--------------------
Output the actual file tree and the content of each file.

Everything must be copy-paste ready.

Do not give advice.
Produce implementation.
