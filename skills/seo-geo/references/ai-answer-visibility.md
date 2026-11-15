# AI-Answer Visibility: Measuring Presence, Not Just Readiness

The GEO readiness score predicts whether a page *can* be cited. This reference
measures whether the brand *is* mentioned or cited in AI answers today, and who
is cited instead. Use it when the user asks "are we in ChatGPT / AI Overviews /
Perplexity", during a full GEO audit, or before planning GEO content.

## 1. Build the prompt panel

- 20-50 prompts real buyers ask, mostly **unbranded**. Keep 10-25 for a quick check.
- Source wording from Search Console queries, autocomplete, People Also Ask,
  community threads (Reddit, forums), first-party questions (see
  `seo-content-brief/references/question-bank.md`), and any AI-visibility tool's
  tracked prompts.
- Cover the grid below and flag empty cells before trusting any trend:

| Axis | Cells to cover |
|---|---|
| Funnel phase | Awareness ("what is X"), Consideration ("best X for Y"), Evaluation ("X vs Y", "alternatives to [competitor]", "how to tell a reliable X"), Decision ("is [brand] legit", "[brand] review", "where to buy X in [country]") |
| Prompt type | Category best-of, head-to-head, alternatives, brand review, problem-led ("how do I ..."), recommendation ("recommend a X for [audience]"), regulation per market |
| Market / language | One sub-set per target market, written natively in that language (not translated English), tagged with its language code |
| Topic | Every product/service category and every editorial pillar |

Common failure: every prompt sits in one phase (usually Consideration) and one
language, so the panel cannot see awareness or brand demand.

Keep the panel stable between runs. Add new prompts as a separate cohort so
trends stay comparable.

## 2. Collect answers (preference order)

1. A first-party or paid AI-visibility tool (tracked prompts, citations,
   competitors), filtered to this brand. If brands share one account and the
   tool cannot separate them, filter by prompt text and say so.
2. DataForSEO AI-optimization endpoints (`seo-dataforseo`) or another citation tracker.
3. Manual checks per engine (ChatGPT search, Perplexity, Gemini / AI Mode,
   Copilot, Claude), **per market with that market's location set**. Never run
   every market from one location.

Answers vary between runs. Run each prompt at least 3 times, report the mention
rate as a percentage, and record date, engine, model and logged-out state.
Without a tool this is a **sample, not a measurement**. Label it that way.

## 3. Record (never infer)

| Prompt | Engine | Market | Mentioned (Y/N, rate %) | Position in list | Our URL cited | Description accurate? | Sentiment (+/0/-) | Cited instead (domains/URLs) | Date |

A prompt that was not tested is listed as `UNKNOWN (reason)`, never skipped or guessed.

## 4. KPIs (baseline, then monthly)

| KPI | Definition |
|---|---|
| Unbranded mention rate | Unbranded prompts whose answer names the brand / all unbranded prompts |
| Owned citation share | Citations to your domains / all citations across the panel |
| Share of voice | Your mentions / (your mentions + named competitors' mentions) |
| Cited third-party sources | Outside domains (lists, forums, video, reference sites) the engines cite for your topics: your off-site targets |

## 5. Brand-in-answer rubric (0-10 each; overall = mean x 10)

| Dimension | What 10 looks like |
|---|---|
| Presence | Mentioned in most panel prompts |
| Position | Named first or second when lists are given |
| Accuracy | Features, pricing and positioning described correctly |
| Sentiment | Positive or neutral; no unaddressed negatives |
| Completeness | Key differentiators and use cases mentioned |
| Consistency | Same story across engines and runs |

## 6. Read the results and map fixes

- **"Cited instead"** is the GEO competitor list. Look for pages that win
  repeatedly and the source *types* that win (forums, video, reference sites).
- **Mentioned but not linked:** an entity-strength signal, not a citation win.
- **Our URL cited for the wrong question:** an intent or cannibalisation finding.

| Failed dimension | Fix |
|---|---|
| Presence / Position | Comparison and "alternatives to [competitor]" pages; honest inclusion in third-party roundups and reviews; disclosed participation where buyers ask (see `offsite-entity-building.md`) |
| Accuracy / Completeness | One entity fact sheet used everywhere (site, Organization/Product schema with `sameAs`, profiles, directories); factual docs and comparison tables with explicit data |
| Sentiment | Find the cited source of the negative claim and answer it publicly with evidence; act early, narratives reverse slowly |
| Lost prompt | A page that answers it directly: heading mirrors the prompt, first sentence gives the answer |

Prioritise topics where owned mentions = 0 and competitors are cited. Expect
change over weeks or months; re-run the same panel on a fixed cadence (monthly
or quarterly) and compare like with like. Treat vendor "recommendations" as
hypotheses and validate them against Search Console and
`google-ai-optimization-guide.md`.

When a page ships, add matching prompts in every relevant language and phase so
its effect is measured. Markets that send traffic but have no prompts are blind
spots; review the panel quarterly.

## 7. AI-invented URL recovery (monthly)

AI assistants sometimes link URLs on your domain that never existed; the visit
lands on a 404 and the referral is lost.

1. Pull 404 hits whose referrer is an AI assistant (chatgpt.com, perplexity.ai,
   copilot.microsoft.com, gemini.google.com, claude.ai) from server logs or
   analytics (GA4's AI-assistant traffic, where available).
2. For each invented path with a clear intent, add a **single-hop 301** to the
   closest live page on that intent. Never send them to the homepage by default.
3. Recurring invented slugs reveal content engines expect you to have: treat
   them as content-gap candidates.

Report: | Invented URL | AI referrer | Hits | Proposed 301 target |

## Output section

Add to the GEO report: "AI-answer presence (measured, dated)" with the panel
table, KPIs, rubric score, top "cited instead" domains, and the fix list.
Never invent a citation, ranking or volume.
