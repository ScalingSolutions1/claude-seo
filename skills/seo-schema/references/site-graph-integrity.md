# Site-Wide Entity Graph Integrity, Markup Parity, and Delivery

Per-block validation checks syntax and required properties. These checks look
across pages and against what users can see.

## Entity graph (parse every JSON-LD block from the initial HTML of each page)

- **Organization:** exactly one per page; name = the public brand name (not the
  legal entity); `url`, `logo`, `sameAs` to every owned profile; `founder` or
  `employee` pointing at the Person by `@id`.
- **Person (author):** defined once (about or author page) and referenced by
  `@id` from every Article. `sameAs` lists every active profile. `jobTitle` is
  true and earned; on YMYL sites, no professional titles the person does not hold.
- **Article / BlogPosting:** exactly one block per post. Flag duplicates (often a
  CMS block plus a plugin block). `author` is a Person, never an Organization.
  Includes `publisher` (the Organization), `datePublished`, `dateModified`, `image`.
- **WebSite:** homepage only.
- **Name variants:** any brand-name spelling in markup that differs from the
  canonical form.
- **Leftovers:** Product, Offer or AggregateRating on pages that no longer sell
  anything (retired products, sites that changed model). **High.**

## Markup-content parity

Google's structured-data guidelines require markup to describe content visible
to users on that page.
- Q&A text in markup matches the visible questions and answers word for word.
- Product `price`, `priceCurrency`, `availability` match the visible buy box
  (check after JS render and per variant).
- `aggregateRating` / `review` counts match what the page shows.
- Article `headline`, `author`, `datePublished` / `dateModified` match the
  visible byline and dates.
- BreadcrumbList matches the visible breadcrumb trail.

Severity: **High** when a mismatch could mislead (price, rating, availability);
**Medium** otherwise. Hidden-only markup risks a manual action.

## Delivery (tell the user where the output goes)

Wrap output in `<script type="application/ld+json">`, rendered server-side in
the initial HTML.
- Plain HTML or CMS: inside `<head>` (or end of `<body>`).
- Next.js App Router: render the script tag in a Server Component (page or
  layout) with `JSON.stringify(data)`; not only inside client components.
- Other SSR frameworks: the head API (`<svelte:head>`, `useHead`, Astro
  layout), server-rendered.

## Eligibility line

For each emitted type, state the Google rich result it can qualify for, or
"none (semantic / entity value only)", using the current deprecation status in
`deprecated-types-2024-2026.md`.
