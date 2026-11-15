# Codebase Audit Mode (no live URL, or pre-deploy)

Use when the user has a local project and no live URL, or wants issues caught
before deploy. Every finding cites `file:line` and the exact code change. Use
the same severity bands as the live audit.

## 1. Discover the stack and routes

| Stack | Routes | Metadata lives in | Sitemap / robots |
|---|---|---|---|
| Next.js App Router | `app/**/page.tsx` | `export const metadata` / `generateMetadata()` | `app/sitemap.ts`, `app/robots.ts` |
| Next.js Pages Router | `pages/**` | `next/head` | `public/` or next-sitemap config |
| Nuxt | `pages/**` | `useHead` / `useSeoMeta` | module config |
| SvelteKit | `src/routes/**/+page.svelte` | `<svelte:head>` | route endpoints |
| Astro | `src/pages/**` | layout `<head>` | `@astrojs/sitemap` |
| Remix / React Router v7 | `app/routes/**` | `meta` export | resource routes |
| Static / SSG (Hugo, Jekyll, 11ty, plain HTML) | content dirs / `*.html` | front matter / templates | generator config |

Also read redirect sources: `next.config.*` redirects, `middleware.*`,
`_redirects`, `vercel.json`, `netlify.toml`, server config.

## 2. Per-route checks

- Title and description defined per route, not inherited site-wide; unique
  across routes. Flag a metadata default that is identical on every page.
- Canonical defined and absolute; `robots` noindex only where intended.
- Exactly one H1 per rendered route (check layout and page together).
- `<img>` without `alt`, without width/height, or bypassing the framework's
  image component.
- Primary content rendered client-only (`"use client"` on content components,
  data fetched in `useEffect`): it will not be in the raw HTML that non-JS
  crawlers and many AI crawlers see.
- JSON-LD injected only client-side (Helmet or head managers inside client
  components): same risk.
- Open Graph and Twitter tags present.

## 3. Link integrity from source

- Collect every internal href: `<a href>`, framework `<Link href/to>`, Markdown
  `[x](url)`, CSS `url()`, redirect targets, sitemap entries.
- Resolve each against the route table, including dynamic segments. Flag
  targets with no matching route.
- Flag `#fragment` links whose target `id` does not exist on the destination.
- Flag case mismatches (`/About` vs `/about`), inconsistent trailing slashes, and
  hardcoded absolute URLs to your own domain (staging or old domains break).
- Flag redirect rules that chain (A to B, B to C) or point to missing routes.

## 4. After deploy

Re-run the live checks on the deployed URLs with
`"${CLAUDE_PLUGIN_ROOT}/scripts/claude-seo" run page_checks.py` and
`render_page.py`: source analysis cannot see CDN, server or CMS behaviour.
