# Pre-Publish Gate (single article or page)

Run in order before a page goes live. Block publishing on any fail.

1. **Meta:** title and meta description set and within limits; slug final.
2. **Index status (updates only):** for an existing URL, the coverage state is
   known (`seo-google/references/indexing-remediation.md`); fix indexing first.
3. **Byline:** a named author is assigned and links to an author page; dates shown.
4. **Structure:** one H1, no skipped heading levels (`page_checks.py` (via `"${CLAUDE_PLUGIN_ROOT}/scripts/claude-seo" run`)).
5. **Answer-first:** the main question is answered in a self-contained 40-60
   word passage near the top; each question H2 opens with its own answer.
6. **Markup parity:** JSON-LD matches the visible text (see `seo-schema`,
   markup-content parity).
7. **Claims:** `content_verify.py` (via `"${CLAUDE_PLUGIN_ROOT}/scripts/claude-seo" run`); every number has a source; no
   invented studies, figures, credentials or customer evidence. YMYL pages also
   pass `ymyl-claims-scan.md`.
8. **Writing:** each section leads with the concrete thing (finding, number,
   example) and explains after it; proof instead of adjectives ("powerful",
   "cutting-edge", "premium"); remove filler openers, "game-changer" phrases,
   "here's why this matters" bridges and engagement-bait closing questions
   (`content_humanize.py` (via `"${CLAUDE_PLUGIN_ROOT}/scripts/claude-seo" run`)); no section repeats another.
9. **Links:** related-reading block present; matching links added FROM the
   related product, category and hub pages in the same release (otherwise the
   new page starts as a near-orphan).
10. **Brand and compliance review**, if the site has one.

## Post-publish

- Submit the URL via IndexNow (`seo-bing`); confirm it is in the sitemap;
  request indexing in Search Console for key pages.
- Add matching prompts to the AI-visibility panel
  (`seo-geo/references/ai-answer-visibility.md`).
- Note the Search Console query and page to measure, with a baseline and a
  review date 4-8 weeks out.
