# Store Template Checklists (non-product page types)

Score every element **PRESENT / PARTIAL / MISSING**. Audit one representative
URL per template, then sample others to confirm the template behaves the same.

## Homepage
- H1 states brand plus primary category or offer (entity clarity).
- Answer-first hero: 40-60 words answering "What is [brand] and what does it sell?"
- Cards linking to every top-level category.
- Trust row near the top (proof of quality, delivery promise, returns, ratings).
- Differentiators with specifics, not adjectives.
- Links to every major hub (guides, trust / proof page, tools).
- Organization (name, url, logo, sameAs) plus WebSite JSON-LD.
- Self-canonical; hreflang if multilingual; OG title, description, image.

## Category / collection page
- H1 = the category's primary keyword; title and meta lead with it
  (transactional phrasing where the SERP is transactional).
- Unique title and meta per category (flag shared or templated metas).
- Short answer-first intro (1-2 sentences, up to ~100 words) above the grid,
  so products stay above the fold.
- Roughly 300-600 words of unique copy below the grid: what the category
  includes, how to choose (criteria, sizes, formats), quality and
  certifications, delivery and returns for this category. Boilerplate repeated
  across categories does not count.
- 4-6 category-specific questions answered on the page in plain HTML.
- Crawlable `<a href>` links to subcategories and every product (not JS-only
  load-more); descriptive anchors.
- Never link to filter, sort or parameter URLs; faceted URLs canonicalised or
  noindexed.
- Links to the buying guides that help choose within the category.
- Key categories linked from the main navigation and strong pages.
- BreadcrumbList; CollectionPage or ItemList where useful. Shipping
  (`hasShippingService`) and returns (`hasMerchantReturnPolicy` with
  `returnPolicyCountry`) defined once at Organization level.
- Same copy and schema on mobile; copy not hidden behind "read more" on load.

## Header navigation
- Logo links home; all categories reachable via crawlable links (mega menus too).
- Site search present; language / market switcher (see `seo-hreflang`).
- Trust / proof page and Guides hub in the main nav.
- Mobile menu exposes the same links as desktop (mobile-first parity).

## Footer
- Company (about, contact), Resources (guides, tools, FAQ, trust page), Policy
  (privacy, terms, shipping, returns) columns.
- Accepted payment methods for the market; social profiles matching
  `Organization.sameAs`; newsletter signup.
- Current copyright year (a stale year signals neglect).

## Trust / proof page (test results, certificates, warranties, standards)
- Clear H1; per-product evidence (documents or embedded results).
- Methodology in plain language.
- Linked from every product page; unique meta description.

## Tool / calculator page
- H1 names the tool; clear input and output; usage instructions and short FAQ.
- Linked from relevant product pages and guides; WebApplication schema optional.

## Supporting pages (About, Contact, Shipping, Returns, How to order, Legal)
- Unique title, meta and a purpose-matching H1 on each.
- Organization on About; a contact method on Contact.
- Shipping table by region, method, speed and cost.
- Returns policy stated plainly and mirrored in MerchantReturnPolicy markup.

## Catalog consistency
Score every product with the same product checklist. Name the deepest product
page as the benchmark and report "N of M products at benchmark depth", listing
the thin ones. Uneven depth is a site-wide thin-content risk.

## Report shape
Summary (pages audited; gaps by Critical / Important / Nice-to-have), then per
template PRESENT / PARTIAL / MISSING, site-wide technical gaps, content to
create (pages, comparisons, unanswered questions), and an action order sorted
by impact, then effort.
