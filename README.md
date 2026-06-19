# TechOptiCore LLC — Website

Business website for TechOptiCore LLC. Built with Astro and Tailwind CSS.

**Stack:** Astro v6 · Tailwind CSS v4 · Static output · Cloudflare (auto-deploy from GitHub)

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

## Deploying (Cloudflare + GitHub)

The site is hosted on Cloudflare, connected to the GitHub repo
[`bryandutson-ctrl/TechOptiCore`](https://github.com/bryandutson-ctrl/TechOptiCore).
**Deployment is automatic:** any push to the `main` branch triggers Cloudflare to
run `npm run build` and publish the resulting `dist/` to the edge. There is no
manual upload.

### Pushing Updates

1. Edit the relevant `.astro` file in `src/pages/` or `src/components/`
2. (Optional) Run `npm run build` and `npm run preview` to check locally
3. Commit and push to `main`:
   ```sh
   git add -A
   git commit -m "Describe the change"
   git push origin main
   ```
4. Cloudflare builds and deploys automatically (usually under a minute). Watch the
   build in the Cloudflare dashboard → Workers & Pages → **techopticore**.

### Edge configuration

- **Security headers & caching:** `public/_headers` (served at the edge for every route).
- **HTTPS:** enforced by Cloudflare. Confirm **Always Use HTTPS** is enabled in the
  Cloudflare dashboard (SSL/TLS → Edge Certificates).

### Verify after deploy

Hard-refresh (`Ctrl + Shift + R`) and confirm:

- [ ] Homepage, Services, About, Contact all load
- [ ] Profile photo appears on the About page
- [ ] "Schedule a Free Consultation" buttons open Calendly in a new tab
- [ ] Contact form submits correctly
- [ ] Site looks correct on mobile
- [ ] Security headers present (run the domain through [securityheaders.com](https://securityheaders.com))

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
