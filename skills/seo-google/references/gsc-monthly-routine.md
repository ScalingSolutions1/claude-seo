# Monthly Search Console Opportunity Routine

28-day window, `query` + `page` dimensions (`gsc_query.py` (via `"${CLAUDE_PLUGIN_ROOT}/scripts/claude-seo" run`)).

1. **Split branded and non-branded.** Exclude branded queries with a regex of
   the brand name, misspellings and product names. Report both totals;
   non-branded is the SEO growth metric.
2. **Striking distance:**
   - Positions 4-10 with high impressions: title and CTR work, small on-page
     improvements.
   - Positions 11-20: page-2 pages that need depth, internal links or links to
     reach page 1.
3. **Decliners:** compare the last 28 days with the previous 28 days, and with
   the same period last year for seasonal sites. Flag pages with a clicks drop
   of 20% or more, or a position loss of 3 or more. Check the Google update
   ledger first (`seo_updates.py` (via `"${CLAUDE_PLUGIN_ROOT}/scripts/claude-seo" run`)), then refresh the page or check for
   a lost SERP feature.
4. **Live cannibalisation:** flag any non-branded query where 2+ URLs from the
   site get impressions and their positions alternate, or both sit below 10.
   Fix: pick one URL, merge and 301 the others or re-target them, and point
   internal anchors at the winner.
5. **Top 5 actions by revenue impact.** Money pages (product, category, service,
   pricing) and link acquisition for them come before informational content.
   Show expected impact and effort per action.

Record each run with its date so the next month compares like with like.
