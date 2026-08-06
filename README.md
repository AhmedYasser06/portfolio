# Ahmed Yasser — Portfolio

A single static site (no build step, no framework) for AhmedYasser06.github.io.

## Structure

```
ahmed-yasser-portfolio/
├── index.html                        # the whole page
├── assets/
│   ├── css/
│   │   └── style.css                 # all styling (colors, type, layout)
│   ├── js/
│   │   └── main.js                   # scroll-reveal animation
│   └── resume/
│       └── Ahmed_Yasser_Resume.pdf   # linked from the "Resume" buttons
└── README.md
```

Content lives directly in `index.html` — there's no CMS or templating, so editing
text means editing the HTML in place (each section is clearly commented/labeled:
About, Experience, Projects, Skills, Education, Contact).

## Deploy on GitHub Pages (user/organization site)

This is the setup for `AhmedYasser06.github.io`, which GitHub serves at the root
domain automatically.

```bash
# 1. Create a new repo on GitHub named exactly:
#    AhmedYasser06.github.io   (must match your username)

# 2. From inside this folder:
cd ahmed-yasser-portfolio
git init
git add .
git commit -m "Initial portfolio"
git branch -M main
git remote add origin https://github.com/AhmedYasser06/AhmedYasser06.github.io.git
git push -u origin main
```

Then on GitHub: **Settings → Pages → Source → Deploy from a branch → `main` / `root`**.
Your site goes live at `https://AhmedYasser06.github.io` within a minute or two.

## Deploy as a project site instead

If you'd rather keep it at `AhmedYasser06.github.io/portfolio` (e.g. to have your
GitHub profile page be something else), name the repo `portfolio` (or anything)
and enable Pages the same way — GitHub Pages will serve it at
`https://AhmedYasser06.github.io/<repo-name>/`. No file changes needed since all
asset paths in `index.html` are relative.

## Updating content later

- **Text/sections** → edit directly in `index.html`.
- **Colors/fonts/spacing** → edit `assets/css/style.css` (CSS custom properties
  are declared at the top under `:root`).
- **Resume** → replace `assets/resume/Ahmed_Yasser_Resume.pdf` with a new PDF of
  the same filename, or update the two `href="assets/resume/..."` links in
  `index.html` if you rename it.
- **Project links** → each project card's `<a class="proj-link" href="...">`
  currently points to your GitHub profile; swap in individual repo URLs anytime.

After editing, just commit and push — GitHub Pages rebuilds automatically.

## Local preview

No build tools required. Either open `index.html` directly in a browser, or run
a tiny local server (needed if you want `assets/` to load exactly as Pages
would serve it):

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```
