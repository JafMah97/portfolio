# Jafar Mahmoud · Portfolio

My personal portfolio, in Arabic and English.

**Live:** [jafarmahmoud.sy](https://jafarmahmoud.sy)

---

## Features

- **Bilingual (Arabic / English)** with full right-to-left layout for Arabic, using CSS logical properties
- **Light and dark themes** that follow the system, with the visitor's choice remembered
- **Statically generated** pages for both languages
- **SEO:** per-page metadata, Open Graph images, `hreflang`, sitemap, robots and JSON-LD structured data
- **Accessible:** semantic HTML, skip link, keyboard-friendly navigation
- **Content in one place:** projects, experience and skills live in typed files under `content/`, so updating the site means editing data, not components

## Tech stack

| | |
| :--- | :--- |
| Framework | Next.js (App Router) |
| UI | React |
| Language | TypeScript |
| Styling | Tailwind CSS |
| Fonts | IBM Plex Sans, IBM Plex Sans Arabic, IBM Plex Mono (self-hosted) |
| Hosting | Vercel |

No UI or i18n libraries: localization, theming and SEO are built with plain Next.js APIs.

## Project structure

```text
app/
  [locale]/            pages for /en and /ar
    page.tsx           home: intro, work, experience, skills, contact
    work/[slug]/       case study page for each project
    opengraph-image    generated social preview image
  sitemap.ts, robots.ts, manifest.ts
components/            header, footer, section
content/               all site text and data (typed)
  site.ts              profile, links
  projects.ts          case studies
  experience.ts        jobs and skills
  ui.ts                interface labels in both languages
lib/
  i18n.ts              locales, direction, date formatting
  seo.tsx              metadata and JSON-LD helpers
proxy.ts               redirects / to the visitor's language
```

## Run locally

```bash
npm install
npm run dev
```

Then open http://localhost:3000.

| Command | What it does |
| :--- | :--- |
| `npm run dev` | Start the development server |
| `npm run build` | Build for production |
| `npm run start` | Run the production build |
| `npm run typecheck` | Check TypeScript types |

## Editing content

All text is in `content/`. Every string has both languages:

```ts
role: { en: "Frontend Developer", ar: "مطوّر واجهات أمامية" }
```

To add a project, add an entry to `content/projects.ts`. Its case study page at `/work/<slug>` is generated automatically.
