# TechOptiCore LLC — Website

Business website for TechOptiCore LLC. Built with Astro and Tailwind CSS.

**Stack:** Astro v6 · Tailwind CSS v4 · Static output · GoDaddy hosting

---

## Pages

| Page | Route | Description |
|---|---|---|
| Home | `/` | Hero, services overview, stats, CTA |
| Services | `/services` | Full service listings with pricing ranges |
| About | `/about` | Bryan's bio, credentials, industries served |
| Contact | `/contact` | Formspree contact form |

---

## Local Development

**Requirements:** Node.js v22+ ([nodejs.org](https://nodejs.org))

```sh
# Install dependencies (first time only)
npm install

# Start local dev server
npm run dev
```

Dev server runs at `http://localhost:4321` (or next available port).

---

## Deploying to GoDaddy

### Step 1 — Build the Site

Run the build command from the project folder:

```sh
npm run build
```

This generates a `dist/` folder containing all compiled HTML, CSS, and assets. That folder is your website.

### Step 2 — Back Up Your Current Site (Recommended)

Before uploading, save a copy of what's currently live:

1. Log in to [godaddy.com](https://godaddy.com) → **My Products**
2. Under your hosting plan, click **Manage** → **cPanel** → **File Manager**
3. Open the **public_html** folder
4. Select all files → **Compress** → download the zip as a backup

### Step 3 — Upload the New Site

1. In GoDaddy File Manager, open **public_html**
2. Select and delete all existing files and folders (including any `.htaccess` file)
3. On your computer, open the `dist/` folder, select everything inside it, and compress it into a zip file
4. In File Manager, click **Upload** and upload the zip
5. Once uploaded, select the zip → **Extract** → confirm the path is `/public_html/`
6. Delete the zip file after extraction

After extraction, `public_html` should contain:

```
public_html/
├── index.html
├── about/
├── services/
├── contact/
├── _astro/
├── favicon.ico
├── favicon.svg
├── logo.png
└── bryan-dutson.png
```

### Step 4 — Verify

Visit your domain and confirm:

- [ ] Homepage loads correctly
- [ ] Navigation links work (Services, About, Contact)
- [ ] Profile photo appears on the About page
- [ ] "Schedule a Free Consultation" buttons open Calendly in a new tab
- [ ] Contact form on the Contact page submits correctly
- [ ] Site looks correct on mobile

### Troubleshooting

**Site still shows the old design**
Force a hard refresh: `Ctrl + Shift + R` (Windows) or `Cmd + Shift + R` (Mac). If still showing old site, clear your browser cache.

**404 errors on pages**
The files may have extracted into a subfolder inside `public_html` (e.g., `public_html/dist/index.html`). Check for a `dist/` folder inside `public_html` — if present, move its contents up one level, then delete the empty `dist/` folder.

**Images not loading**
Confirm `bryan-dutson.png` and `logo.png` are in the root of `public_html`, not inside a subfolder.

**Blank page or missing styles**
The `_astro/` folder must be present alongside `index.html`. If missing, re-upload it from `dist/_astro/`.

---

## Pushing Updates

When you make changes to the site:

1. Edit the relevant `.astro` file in `src/pages/` or `src/components/`
2. Run `npm run build` to regenerate `dist/`
3. Upload the new `dist/` contents to `public_html`, overwriting the old files

---

## Project Structure

```
TechOptiCore/
├── public/               # Static assets (images, favicon)
├── src/
│   ├── components/       # Nav.astro, Footer.astro
│   ├── layouts/          # Layout.astro (shared page wrapper)
│   ├── pages/            # One .astro file per page
│   └── styles/           # global.css
├── astro.config.mjs
├── package.json
└── README.md
```

---

## Commands Reference

| Command | Action |
|---|---|
| `npm install` | Install dependencies |
| `npm run dev` | Start local dev server |
| `npm run build` | Build to `dist/` for production |
| `npm run preview` | Preview the production build locally |

---

*Built by [Clearmark Digital](https://clearmarkdigital.com) · March 2026*
