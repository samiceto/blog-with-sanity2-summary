# RUNO — Blog with Next.js & Sanity

A modern, responsive blog built with [Next.js 14](https://nextjs.org) (App Router), [Sanity CMS](https://www.sanity.io) and [Tailwind CSS](https://tailwindcss.com).

## Features

- 📰 Featured-post hero carousel and responsive article grid
- ✍️ Content managed in Sanity Studio, embedded at `/studio`
- 🔄 Incremental Static Regeneration (content updates within 60s)
- 🖼️ Optimized images via `next/image` + Sanity image pipeline
- 💬 Client-side comments with validation (persisted in localStorage)
- 🔍 SEO: per-page metadata, Open Graph tags, custom 404 page
- 📱 Fully responsive with a mobile slide-out menu

## Getting Started

1. **Install dependencies**

   ```bash
   npm install
   ```

2. **Configure environment variables**

   Copy `.env.example` to `.env.local` and fill in your Sanity project values
   (from [sanity.io/manage](https://www.sanity.io/manage)):

   ```bash
   cp .env.example .env.local
   ```

3. **Run the dev server**

   ```bash
   npm run dev
   ```

   Open [http://localhost:3000](http://localhost:3000) for the site and
   [http://localhost:3000/studio](http://localhost:3000/studio) for the CMS.

## Project Structure

```
src/
├── app/
│   ├── page.tsx              # Home (hero carousel + article grid)
│   ├── [blog]/page.tsx       # Article detail page
│   ├── articles/             # All articles
│   ├── about/                # About page
│   ├── contact/              # Contact page
│   ├── studio/               # Embedded Sanity Studio
│   └── Components/           # Navbar, HeroCarousel, PostGrid, Comments, Footer
├── components/ui/            # shadcn/ui primitives
├── lib/                      # Utilities (cn, formatDate)
└── sanity/                   # Schemas, client, queries
```

## Deploying to Vercel

1. Push the repo to GitHub and import it in [Vercel](https://vercel.com/new).
2. Add the environment variables from `.env.example` in the Vercel project settings
   (set `NEXT_PUBLIC_SITE_URL` to your production URL).
3. In [sanity.io/manage](https://www.sanity.io/manage) → API → CORS origins, add your
   Vercel domain so the embedded Studio can connect.
4. Deploy.
