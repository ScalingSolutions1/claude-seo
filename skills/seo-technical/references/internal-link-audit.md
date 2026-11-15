# Internal Link Graph Audit

Site-wide audit of the internal link graph for existing sites. (`seo-cluster`
plans links for new clusters; this audits what is live.)

## Build the graph

- Page inventory from crawl, sitemap or routes, with type (home / hub /
  product / blog / landing) and topic per page.
- Per page: outlinks, inlinks and anchor text. Count body and main-nav links
  separately from footer and sidebar boilerplate.

## Issues

| Issue | Detection | Fix |
|---|---|---|
| Orphan | 0 internal inlinks (often only in the sitemap) | Contextual links from 2+ topically related, indexed pages |
| Dead end | 0 internal outlinks in the body | Related-content links, breadcrumbs, next-step CTA |
| Over-linked | > 100 links on one page | Cut low-value links; keep priority targets |
| Buried | Important page 4+ clicks from home | Link from hubs, main nav or homepage |
| Weak anchor | "click here", "read more", "learn more", bare URLs | Descriptive anchor naming the target topic |
| One-way in cluster | A links B, B never links A within one topic | Add the reciprocal contextual link where natural |
| Thin cluster linking | Cluster page links to < 2 siblings | Each cluster page links 2+ siblings and its hub |
| Parameter links | Internal hrefs carry filter, sort, session or tracking parameters | Link the clean canonical URL |
| JS-only links | Navigation via `onclick` or buttons without `<a href>` | Plain crawlable `<a href>` links |

## Priority rules

- Home links to category / hub pages (highest priority).
- Hub links to every page in its topic; every spoke links back to its hub.
- Blog posts link to related posts and the relevant product or service page
  (e-commerce: `seo-ecommerce/references/product-depth-and-linking.md`).
- Footer and sidebar link only to evergreen, important pages.
- Multilingual sites: internal links stay inside one language, except the
  language switcher.

## Report

- Pages analysed, total internal links, average per page.
- Orphans (with a suggested source page), dead ends (with suggested targets),
  weak anchors (current to suggested).
- A "From | To | Anchor" table of link additions.
- An ASCII hub-to-spoke map per topic.

Broken links: see `broken-links.md`.
