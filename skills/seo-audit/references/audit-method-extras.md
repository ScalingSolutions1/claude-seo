# Audit Method Extras: History, Inventory, Scoring, Honesty, Report Shape

Additions to the full-site audit process. Steps are numbered to slot into the
`seo-audit` Process.

## Step 0: Load history

- Read the newest previous audit for this domain (for example the
  `{domain}-audit/` folder) and any decisions log or site plan the user provides.
- Do not re-report items marked fixed or deliberately decided. If a "fixed" item
  has regressed, report it as a **regression**.
- When the user's site plan and this skill disagree on structure, the plan wins.
  Say so in the report.

## Step 3b: Inventory reconciliation

Merge four lists: CMS export (pages, landing pages, posts, redirects), crawl or
map, sitemap(s), and the intended site plan if one exists. Output one table:

| URL | Status | In sitemap | Indexable | Page type | Cluster | Primary question | In plan |

Flag:
- In plan but not live; live but not in plan (stale, legacy, placeholder pages).
- Orphans; any 3xx/4xx.
- Two indexable URLs sharing one primary question (cannibalisation: merge, or
  split by intent). One URL answers one primary question.

## Per-page-type requirement rubric

For each page type, list its must-have elements (H1 claim, one primary CTA,
required internal links, byline, dates, sources, schema type). Score each
element **PRESENT / PARTIAL / MISSING** with evidence. E-commerce templates:
`seo-ecommerce/references/store-template-checklists.md`.

## Priority scoring

Score = Impact (1-5) x Confidence (1-3) / Effort (1-5). Sort by score within
each band:
- **Critical / P1:** not indexable or not rendering, broken redirects, wrong or
  missing Organization/Person entity, YMYL claim-scan hits.
- **High / P2:** money and lead-capture pages: titles, answer-first blocks,
  internal links.
- **Medium / P3:** blog and cluster gaps, AEO content to create.
- **Low / P4:** nice to have.

## Data honesty

- Every number carries its source and date. Never invent a volume, ranking or
  AI citation.
- A check whose tool or data is missing is marked `UNKNOWN (reason)`, never
  skipped silently.
- Raw-HTML checks (title, H1, canonical, JSON-LD) run on raw HTML only, never on
  a markdown or text scrape.

## Report additions

- `## Verdict in five lines` before any detail, including an overall verdict:
  **Strong foundation**, **Needs work**, or **Critical issues**; the site's single
  biggest strength (protect it in any change); the top 3 priorities in plain language.
- `## Data pass`: | Source | Used? | Key numbers (dated) | Notes |
- Findings table: | # | Band | Page/template | Finding | Evidence | Fix |
  Where the fix is made (CMS page / template / module / redirect / off-site) |
  Effort | Dependencies |
- Effort tiers: quick win (< 2 h), moderate (half a day), substantial (days).
- Split actions into **Quick wins (this week)** and **Strategic investments
  (this quarter)**.
- `## Fix list (ranked, top 15)`
- `## Not available this run` (each `UNKNOWN` with its reason)

## Lighter audit modes

When the user asks for less than a full audit:
- Keyword research: `seo-cluster/references/keyword-discovery.md`.
- Content gap: competitor topic coverage, content older than 12 months, thin
  pages, missing content types, funnel-stage gaps
  (`seo-plan/references/content-prioritization.md`).
- Technical only: `seo-technical`.
- Competitor comparison: `seo-plan/references/competitor-benchmark.md`.
- Local codebase, no live URL: `codebase-audit.md`.

## Follow-up offers

After the report, offer to: draft briefs for the top opportunities, rewrite
titles and metas for key pages, build a content calendar from the gaps, go
deeper into one section, or rerun against another competitor.

## Hard lines

- Read-only: never submit forms, start quizzes or checkers, or file applications
  on the live site to test SEO. Change nothing in a CMS without explicit approval
  for that specific change.
- The audit describes fixes and hands copy work to the writer; it does not
  rewrite page copy.
- Never paste API tokens or keys into a report.
