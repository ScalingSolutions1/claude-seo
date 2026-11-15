# Indexing Gate and Remediation by Coverage State

**Gate:** a page Google has not indexed cannot rank or be cited in AI Overviews
or AI Mode. Before optimizing any existing URL, inspect it (URL Inspection API
via `gsc_inspect.py` (via `"${CLAUDE_PLUGIN_ROOT}/scripts/claude-seo" run`); `site:` plus a live fetch only as a rough fallback
without Search Console access). Record the coverage state and date in the brief
or report.

**Site-level ratio:** compare indexed URLs with known URLs (sitemap plus crawl).
If most URLs are not indexed, fix that before page-level optimization.

| Coverage state | Usual meaning | Fix, in order |
|---|---|---|
| Discovered, currently not indexed | Known but not crawled: low perceived value, weak internal links, or crawl budget | 1) Contextual `<a href>` links from strong indexed pages (home, top category, popular posts). 2) A small, focused priority sitemap with accurate lastmod. 3) Make the page substantively unique, not boilerplate or a thin translation. 4) Improve server response time. 5) Request indexing for a few key URLs. |
| Crawled, currently not indexed | Crawled, judged not worth indexing: quality or duplication | Make content unique and substantial; merge near-duplicates; check canonical and hreflang cluster; strengthen internal links; re-request indexing only after a real change |
| Duplicate, Google chose a different canonical | Consolidation | Accept it, or differentiate the content and align canonical, internal links and sitemap |
| Excluded by noindex / blocked by robots.txt | Directive | Confirm it is intended; remove it if not |
| Soft 404 | Thin or empty page | Add real content, or return a real 404 / 410 |

Locale folders (for example `/de/`, `/nl/`) are often not indexed even when the
main locale is. Inspect a sample from every locale separately.
