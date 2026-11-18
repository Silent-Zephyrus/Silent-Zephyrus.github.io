# Joe Feredel Cabar - Portfolio

A static portfolio (HTML, CSS, JavaScript). No backend, no build step, no dependencies. Works on GitHub Pages as-is.

```
/
├── index.html
├── resume.pdf          <- placeholder, replace with your resume
├── favicon.svg
├── README.md
└── assets/
    ├── css/style.css   <- colors and fonts are CSS variables at the top
    ├── js/script.js
    └── images/         <- put project screenshots here
```

## Run locally

Double-click `index.html`, or from the folder run `python -m http.server 8000` and open http://localhost:8000.

## 1. Replace your details

Open `index.html` and search for these placeholders:

| Search for | Replace with |
|---|---|
| `YOUR_EMAIL@example.com` (2 places) | your email |
| `YOUR_GITHUB_USERNAME` | your GitHub username |
| `YOUR_LINKEDIN_USERNAME` | your LinkedIn username |
| `[Month Year – Present]`, `[Month Year – Month Year]`, `[Organization Name]` | your real dates and employer |
| `[Issuing Organization]`, `[Year]` | your NC II certificate details |

For a phone number, uncomment the `Phone` line in the Contact section. Project features are examples; edit them to match what each system actually does. All four projects carry a "Private / Internal Project" badge; delete that line for any project that is public.

## 2. Add your resume

Save your PDF as `resume.pdf` in the root folder (next to `index.html`), replacing the placeholder. Both Download buttons use that filename.

## 3. Add project screenshots

Only use screenshots with no private data (names, IDs, credentials, internal URLs). Put images in `assets/images/`, then in `index.html` replace the `<div class="shot">...</div>` of a project with:

```html
<img class="shot" src="assets/images/ticketing.jpg" alt="IT Ticketing System dashboard" loading="lazy" width="800" height="450">
```

To show GitHub or Live Demo buttons, paste the snippets from the comment at the top of the Projects section into that project's empty `project-links` div.

## Deploy on GitHub Pages

1. Sign in at github.com and click **New repository**.
2. Name it `YOUR-GITHUB-USERNAME.github.io` (for example `joe-cabar.github.io` if that is your username). Set it to **Public**, then click **Create repository**.
3. Upload the files: click **uploading an existing file**, drag in everything from this folder (keep the `assets` folder structure), and click **Commit changes**. Or use Git:
   ```
   git init
   git add .
   git commit -m "Initial portfolio"
   git branch -M main
   git remote add origin https://github.com/YOUR-GITHUB-USERNAME/YOUR-GITHUB-USERNAME.github.io.git
   git push -u origin main
   ```
4. Go to **Settings → Pages**.
5. Under **Build and deployment**, set **Source** to **Deploy from a branch**.
6. Set **Branch** to `main` and the folder to `/ (root)`, then click **Save**.
7. Wait 1-2 minutes, then open `https://YOUR-GITHUB-USERNAME.github.io/`. The URL also appears at the top of the Pages settings.

If the repository is not named `USERNAME.github.io`, the site lives at `https://USERNAME.github.io/REPO-NAME/`. All paths in this project are relative, so it still works.

## Connect a custom domain (later)

You need to buy a domain first (for example `joecabar.com`) from a registrar such as Namecheap, Cloudflare, or Porkbun.

1. In **Settings → Pages → Custom domain**, enter your domain and click **Save**. GitHub creates a `CNAME` file in the repo.
2. At your registrar's DNS settings, add:
   - Apex domain (`joecabar.com`): four `A` records pointing to `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - `www` subdomain: a `CNAME` record pointing to `YOUR-GITHUB-USERNAME.github.io`
3. Wait for DNS to update (minutes to a few hours), then tick **Enforce HTTPS** in Pages settings.

If you use Cloudflare DNS, set the records to "DNS only" until GitHub finishes issuing the HTTPS certificate. Check GitHub's current docs for these IP addresses if anything fails: docs.github.com/pages.

## Update the portfolio later

Edit files on GitHub (pencil icon) or on your computer, then commit and push. The site redeploys automatically within a minute or two. Hard-refresh (Ctrl+Shift+R) if you don't see changes.

## Never publish

Passwords, database credentials, API keys, `.env` files, or screenshots showing confidential data.
