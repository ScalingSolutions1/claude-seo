# Broken Link Audit and Fix Workflow

## Three classes, in order of value

1. **Backlinked 404s:** your URLs that external sites link to but that now 404.
   Lost equity: fix first with a 301 to the closest relevant live page. Source
   the list from Search Console (Pages: Not found, plus Links), Bing Webmaster
   Tools, or the backlink tools in `seo-backlinks`.
2. **Internal broken links:** renamed or moved pages without redirects, deleted
   content, typos, case mismatches, missing `#id` targets.
3. **External broken links:** outbound links that died (site gone, page
   removed, URL changed).

AI-assistant referrals to URLs that never existed are a fourth source of 404s:
see `seo-geo/references/ai-answer-visibility.md` (AI-invented URL recovery).

## Status interpretation

| Result | Meaning | Action |
|---|---|---|
| 200 | OK | none |
| 301 / 308 | Permanent redirect | Update the link to the final URL |
| 302 / 307 | Temporary | Confirm it is intended; if permanent, make it 301 |
| 404 | Not found | Redirect, fix or remove |
| 410 | Gone on purpose | Correct for deliberately removed content; remove internal links to it |
| 200 on an error page | Soft 404 | Return a real 404 / 410 or restore the content |
| 5xx / timeout | Server problem | Retry later before calling it broken |

Flag redirect chains (2+ hops) and loops.

## Fix strategies

- Moved or renamed: 301 to the new URL.
- Deleted: 301 to the closest relevant page (never blanket to home), or remove the link.
- Dead external: replace with an equivalent source, or unlink.
- Chain: point the link straight at the final URL.
- Typo: correct the href.

## Prevention

- Add a redirect whenever a URL changes or is deleted.
- Run a link checker in CI for code-based sites (`seo-audit/references/codebase-audit.md`).
- Re-check external links on a schedule; they decay.

## Report

Pages scanned, links checked, broken count, chains. Tables:
- Internal: Source | Broken URL | Status | Fix
- External: Source | Broken URL | Status | Fix
- Chains: Start | Hops | Final

Then a "Quick fixes" list: redirect rules to add, href changes, links to remove.
