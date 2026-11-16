# Abrendra Singh – Portfolio

A static, framework-free portfolio for a Solution Architect specialising in Enterprise AI, Microsoft Copilot Studio, Azure AI Foundry and Power Platform. Built with HTML5, CSS3 and vanilla JavaScript. No Node.js, npm or build step.

## Repository structure

```
Portfolio/
├── index.html                      # entry point (must stay lowercase, at repo root)
├── css/style.css
├── js/script.js
├── assets/
│   ├── images/profile-placeholder.svg
│   ├── icons/favicon.svg
│   └── documents/Abrendra-Singh-Resume.pdf
├── README.md
├── .nojekyll
└── .github/workflows/static.yml    # GitHub Pages deployment
```

## Test locally

Open `index.html` directly in a browser, or serve the folder:

```bash
python3 -m http.server 8000   # then visit http://localhost:8000/
```

All asset paths are relative (`./css/style.css`, `./assets/...`), so it works from a file, a local server, or under `/Portfolio/`.

## Deploy to GitHub Pages

1. Create a repository named **Portfolio**.
2. Upload the *contents* of this folder to the repository root (so `index.html` is at the top level, not inside a sub-folder).
3. In the repository go to **Settings → Pages → Build and deployment → Source** and choose **GitHub Actions**.
4. Push to `main` (or run **Actions → Deploy static site to GitHub Pages → Run workflow**).
5. After it succeeds, the site is live at `https://USERNAME.github.io/Portfolio/`.

The workflow uploads the repository root (`path: "."`), so `index.html` sits at the top level of the Pages artifact.

## Customise

| Task | Where |
|------|-------|
| Replace profile photo | Save a square image (about 800×800) as `assets/images/profile.jpg`, then in `index.html` change the hero `<img src>` to `./assets/images/profile.jpg` and update the `alt` text. |
| Update resume | Replace `assets/documents/Abrendra-Singh-Resume.pdf` (keep the same filename), or change the `href` of the Download Resume button. |
| LinkedIn / GitHub / Microsoft Learn URLs | Search `index.html` for `YOUR-LINKEDIN-HANDLE`, `YOUR-GITHUB-USERNAME` and `YOUR-LEARN-PROFILE` (each appears in the hero and/or contact section) and replace them. Also change the visible link text in the contact section. |
| Email | Edit the `mailto:` link in the Contact section. |
| Certifications | Copy or edit an `<li>` in the `#credentials` section. |
| Colours | Edit CSS variables at the top of `css/style.css`. |
| Social preview | Add `og:url` and an absolute `og:image` URL in the `<head>` after you know your Pages URL. |

## Troubleshooting

### GitHub Pages 404
1. Confirm `index.html` exists at the **repository root**.
2. Confirm the filename is exactly lowercase `index.html` (not `Index.html`, `index.HTML` or `home.html`).
3. Confirm the workflow uploads the repository root (`path: "."` in `static.yml`).
4. Confirm `index.html` is at the top level of the uploaded artifact (check the workflow's *upload-pages-artifact* step).
5. Confirm the **deploy** job succeeded in the Actions tab, and that Settings → Pages source is set to **GitHub Actions**.

### CSS / images not loading
Verify paths are relative (`./css/style.css`, `./assets/...`) rather than root-relative (`/css/...`, `/assets/...`). Root-relative paths break under `/Portfolio/`. Also check filename capitalisation: GitHub Pages is case-sensitive.

### Resume button returns 404
Ensure the file is at `assets/documents/Abrendra-Singh-Resume.pdf`.
