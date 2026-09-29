# Trio Bean Cafe — GitHub Pages Setup

This website is a static HTML/CSS/JavaScript site. It does not need Node.js, a database, or a backend to run on GitHub Pages.

## 1. Create a GitHub repository

1. Sign in to [GitHub](https://github.com/).
2. Click **New repository**.
3. Name it something like `trio-bean-cafe`.
4. Choose **Public** if you are using GitHub Free.
5. Leave **Add a README file** unchecked if you are uploading this existing folder.
6. Click **Create repository**.

## 2. Upload the code from your computer

Download or copy the complete project folder first. Then open Terminal, PowerShell, or Git Bash inside the project folder and run:

```bash
git init
git branch -M main
git add .
git commit -m "Create Trio Bean Cafe website"
git remote add origin https://github.com/YOUR-USERNAME/trio-bean-cafe.git
git push -u origin main
```

Replace `YOUR-USERNAME` and `trio-bean-cafe` with your actual GitHub username and repository name.

If this folder is already connected to another Git remote, use this instead of `git remote add origin`:

```bash
git remote set-url origin https://github.com/YOUR-USERNAME/trio-bean-cafe.git
git push -u origin main
```

GitHub may open a browser login window. Complete that login; never paste a GitHub password into the terminal.

## 3. Turn on GitHub Pages

1. Open your repository on GitHub.
2. Go to **Settings → Pages**.
3. Under **Build and deployment**, set **Source** to **GitHub Actions**.
4. Save if GitHub asks.
5. Open the **Actions** tab and wait for **Deploy Trio Bean Cafe to GitHub Pages** to finish with a green check.

The included workflow at `.github/workflows/deploy-pages.yml` automatically builds and deploys the site every time you push to `main`.

## 4. Open the live website

For a normal project repository, the address will be:

```text
https://YOUR-USERNAME.github.io/trio-bean-cafe/
```

For a special repository named exactly `YOUR-USERNAME.github.io`, the address will be:

```text
https://YOUR-USERNAME.github.io/
```

The first deployment can take a few minutes.

## 5. Make future updates

After editing the site, run:

```bash
git add .
git commit -m "Update cafe website"
git push
```

GitHub Actions will redeploy the new version automatically.

## Project files that matter

- `index.html` — page content, menu, logo references, and SEO metadata
- `styles.css` — colors, layout, responsive design, and animations
- `script.js` — mobile navigation and scroll reveal behavior
- `assets/` — local logo, favicon, and cafe images
- `.github/workflows/deploy-pages.yml` — automatic GitHub Pages deployment
- `manus-routes.json` — route manifest; keep it at the project root

## If the site looks unstyled or images are missing

- Confirm the repository **Pages Source** is set to **GitHub Actions**, not a branch folder.
- Open the Actions run and inspect the failed step.
- Confirm `styles.css`, `script.js`, and `assets/` were committed:

```bash
git status
git ls-files assets
```

- Hard-refresh the browser with `Ctrl+Shift+R` or `Cmd+Shift+R`.
- Make sure the URL includes the repository name for a project site:
  `https://YOUR-USERNAME.github.io/trio-bean-cafe/`

All image paths in this version are relative/local so they work under a repository subpath on GitHub Pages.
