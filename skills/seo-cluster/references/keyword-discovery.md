# Keyword Discovery Workflow

Run these sources in order. Record each source and its date in a "Data
sources" block in the output.

1. **Your own Search Console queries first.** Queries the page or site already
   gets impressions for are proven demand that Google already associates with you.
2. **Volume baseline** from a keyword tool (DataForSEO, Ahrefs, Semrush, Keyword
   Planner). Without a tool, label demand High / Medium / Low and say it is an estimate.
3. **Autocomplete alphabet sweep**, per language and market: the seed, then the
   seed plus each letter a-z (optionally 0-9), with the market's language and
   country set. Any endpoint used for this is unofficial and may rate-limit;
   cache results. Autocomplete gives the phrasing for H2s, FAQs and titles.
4. **Bucket suggestions into buyer-concern modifier families** (each often
   deserves its own section or page):
   - Trust: "legit", "reviews", "reddit", "scam", "is it safe", "experiences"
     (plus local-language versions).
   - Legal and regulatory: "legal", "prescription", "allowed in {country}".
   - Payment: "paypal", "klarna", "pay later", "crypto".
   - Location and shipping: "{country}", "near me", "fast delivery".
   - Price: "price", "cheap", "cost", "discount code".
   - Comparison: "vs", "alternative", "best".
5. **Live SERP per market** (location set). For the top 3, record page type
   (category, product, guide, forum, video) and site size or authority.
   Beatable-SERP rule: if a small or low-authority site ranks top 3 with a page
   type, that type is viable; build it with more depth and more internal links.
   With a backlink tool, list keywords where low-authority competitors rank top 3.
6. **YouTube and community questions:** video search suggestions, titles,
   comments, Reddit threads. YouTube demand alone does not prove Google
   demand: cross-check against steps 1-5 before building a web page.
7. **Competitor gap and link intersect** (with a tool): keywords competitors
   rank for and you don't; domains linking to 2+ competitors but not you.

Classify each keyword: intent (informational / commercial / transactional /
navigational), funnel stage (awareness / consideration / decision), type
(primary / secondary / long-tail / question).

## One primary keyword per URL

Map each primary keyword to exactly one URL in a keyword-to-URL map. Never
target one primary keyword with two pages.

## Output: Keyword Opportunity Table (15-25 rows, sorted by opportunity)

| Keyword | Demand (volume or H/M/L) | Difficulty (easy / moderate / hard) | Current rank | Intent | Funnel stage | Opportunity (H/M/L) | Target URL (existing or new) | Content type |

Opportunity combines demand, difficulty and business relevance: a winnable
transactional keyword with moderate demand beats a high-volume informational
keyword you cannot win.

Multilingual: run the whole workflow natively per market
(`seo-hreflang/references/translation-workflow.md`).
