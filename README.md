# Plumber Website Template

Production-ready marketing website template for plumbing businesses. Built with Astro + Tailwind.

Single-page site with hero, services, about, reviews, contact form, and map. Mobile-responsive, SEO-optimized, 100 PageSpeed by default.

## Per-client customization

Everything visible on the site is driven by one file:

```
src/config/site.ts
```

To spin up a new client site:

1. Click **Use this template** on GitHub → create `client-[name]` repo
2. Edit `src/config/site.ts` with the client's info (name, phone, services, reviews, etc.)
3. Connect the new repo to Vercel → deploys automatically in ~30s
4. Point the client's custom domain at the Vercel project

Typical end-to-end setup time: **5–10 minutes per client**.

## Local development

```bash
npm install
npm run dev
# open http://localhost:4321
```

## Deploying

### Vercel (recommended)

1. Push this repo to GitHub
2. Go to [vercel.com/new](https://vercel.com/new)
3. Import the repo → Vercel auto-detects Astro
4. Click **Deploy**
5. Live in ~45 seconds at `[project-name].vercel.app`

### Custom domain

In the Vercel project: Settings → Domains → Add → type the domain → paste the 2 DNS records at the domain registrar. SSL is automatic.

## Contact form

The contact form in `src/components/Contact.astro` currently points at a placeholder Formspree URL. For each client:

1. Create a free form at [formspree.io](https://formspree.io)
2. Replace `YOUR_FORMSPREE_ID` in `Contact.astro` with the new form ID
3. Submissions will email to the address attached to the Formspree form

Alternatives: Resend, Web3Forms, Netlify Forms, or a custom Vercel/Cloudflare function.

## Tech stack

- [Astro 5](https://astro.build) — static site generator, zero JS by default
- [Tailwind CSS 4](https://tailwindcss.com) — utility-first styling
- TypeScript — strict mode
- Deployed on Vercel or Cloudflare Pages (both free for this use case)

## Structure

```
src/
├── config/site.ts          ← edit this per-client
├── layouts/Layout.astro    ← HTML head, meta tags, schema.org
├── components/
│   ├── Header.astro
│   ├── Hero.astro
│   ├── Services.astro
│   ├── About.astro
│   ├── Reviews.astro
│   ├── Contact.astro
│   └── Footer.astro
├── pages/index.astro       ← composes all components
└── styles/global.css       ← Tailwind entrypoint
```
