# AI Engine Playbook: AEO / GEO per Engine

The SKILL.md crawler table says which bot governs which capability. This
playbook turns that into actions per engine. Label every claim: **Doc** =
documented by the vendor; **Obs** = third-party observation (quote with source
and date, or leave out).

## Terms

- **AEO** (answer-engine optimization): being the answer a search engine or
  assistant gives.
- **GEO** (generative-engine optimization): being mentioned and cited inside
  generated answers.
- Google's position (Doc): optimizing for generative AI search is still SEO
  (`google-ai-optimization-guide.md`). The levers are the same everywhere: be
  indexable by the engine's own citation crawler, own the clearest citable
  passage, and be corroborated by the sources that engine trusts.

## Universal checklist (all engines)

- Answer and JSON-LD in the server HTML (many AI crawlers do not run JavaScript).
- A self-contained answer near the top; question-led H2s that open with their
  answer; "X is ..." definitions; comparison tables; named, dated sources.
- One entity fact sheet everywhere (`offsite-entity-building.md`).
- Original data or first-hand experience; commodity pages are rarely cited.
- Measure per engine and per market (`ai-answer-visibility.md`). Obs: only ~11%
  of domains are cited by both ChatGPT and AI Overviews for the same query.

## Per engine

### Google AI Overviews
- Citation crawler: `Googlebot` (not `Google-Extended`).
- Doc: grounded in Search ranking and quality systems, with query fan-out.
  Eligibility needs indexing, snippet eligibility, and the Search Console
  "Search generative AI" control set to include.
- Obs: citations mostly come from pages already in the top 10.
- Do: classic SEO first (index, rank), then make the best passage citable.
  `nosnippet`, `data-nosnippet` and `max-snippet` limit what can be quoted.

### Google AI Mode
- Citation crawler: `Googlebot`.
- Obs (Ahrefs): broader pool (~9 domains per answer); reaches the same
  conclusion as AI Overviews ~86% of the time but cites the same URLs only
  ~14% of the time.
- Do: score it separately from AI Overviews. Entity authority, freshness of
  facts and citable passages on pages ranking below position 5 matter more.
  Doc: Preferred Sources is a per-user choice, not a ranking signal; "Highly
  cited" badges reward original reporting.

### Gemini app
- Doc: grounded in Google Search. `Google-Extended` controls Gemini training and
  grounding use only; blocking it does not remove a site from Google Search or
  AI Overviews.
- Do: as AI Mode.

### ChatGPT (search)
- Citation crawler: `OAI-SearchBot`. `GPTBot` is training only;
  `ChatGPT-User` is a user-triggered fetch ("may not apply" to robots.txt, Doc).
- Obs (Profound, 2025-06-05): Wikipedia and Reddit dominate the top cited sources.
- Do: allow `OAI-SearchBot`; strong, consistent entity presence (Wikipedia /
  Wikidata only where the brand genuinely qualifies); disclosed community
  answers; comparison and "best X for Y" pages with explicit data. Track
  referrals (ChatGPT adds `utm_source=chatgpt.com` to many outbound links).

### Perplexity
- Citation crawler: `PerplexityBot` (Doc: not used for foundation-model
  training). `Perplexity-User` is user-triggered and generally ignores robots.txt.
- Obs (Profound, 2025-06-05): Reddit is the largest single cited source.
- Do: allow `PerplexityBot`; genuine, disclosed participation in the forums it
  cites; specific, dated, sourced pages. Perplexity shows citations, so record
  which URL wins and why.

### Microsoft Copilot (Bing)
- Citation crawler: `Bingbot`; Doc: grounded in the Bing index.
- Do: verify the site in Bing Webmaster Tools, submit sitemaps, use IndexNow
  on publish and update (`seo-bing`). Bing indexing gaps are Copilot gaps.

### Claude (web search)
- Citation crawler: `Claude-SearchBot`. `ClaudeBot` is training only;
  `Claude-User` is user-triggered and honors robots.txt (Doc).
- Do: allow `Claude-SearchBot`; same passage and entity work as above.

### Apple (Siri, Spotlight, Safari)
- Crawler: `Applebot`. `Applebot-Extended` is an Apple Intelligence training
  opt-out only (Doc).
- Do: allow `Applebot`; blocking `Applebot-Extended` does not hide the site.

### Other assistants (Meta AI, Grok, DeepSeek and others)
- Mechanisms are not reliably documented. Do not claim one. Include them in the
  prompt panel and measure; the universal checklist still applies.

## Controls recap

| Goal | Control |
|---|---|
| Stay citable in AI search | Allow `Googlebot`, `Bingbot`, `OAI-SearchBot`, `Claude-SearchBot`, `PerplexityBot`, `Applebot`; keep "Search generative AI" on include |
| Opt out of model training | `GPTBot`, `ClaudeBot`, `Google-Extended`, `Applebot-Extended`, `CCBot` (licensing choice; no effect on search citations) |
| Limit quoting in Google AI features | `nosnippet`, `data-nosnippet`, `max-snippet` |
| Block user-triggered fetchers | Server-side controls (robots.txt may be ignored) |
| `llms.txt` | Optional; not a citation lever for any major engine (`llmstxt-evidence.md`) |

## Agents

Assistants increasingly act (book, buy, fill forms). Real buttons and links, a
clean accessibility tree and stable layout make the site usable by agents:
audit with `seo-agentic`.

## Reporting per engine

| Engine | Citation crawler allowed? | Mentioned (rate) | Owned citations | Cited instead | AI referral sessions (dated) | Top action |

Never merge engines into one score without also showing the per-engine rows.
