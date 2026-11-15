# List Mode: Clustering a User-Supplied Keyword List

Use when the user pastes or uploads a list (often hundreds of keywords) instead
of a single seed.

## Accept
Pasted list, CSV / TXT, or URLs to extract terms from. Optional intent filter.

## Clean
Lowercase, remove exact and near duplicates, fix obvious typos, drop off-topic
terms, merge singular / plural and word-order variants (keep the higher-volume
form as the label).

## Cluster cheaply first, then verify
Group by semantic similarity, intent and modifier pattern. Then run SERP-overlap
checks (`serp-overlap-methodology.md`) only on the primary keyword of each
cluster and on borderline pairs, not on every pair.

## Rules
- One cluster = one URL. Two URLs on one cluster = cannibalisation.
- 3-15 keywords per cluster: fewer, merge into a neighbour; more, split by sub-intent.
- Every cluster has one primary keyword (highest value).
- Branded terms get their own cluster mapped to brand or product pages (keep
  them in list mode).
- "X vs Y" terms get separate comparison clusters.
- Location-modified terms cluster by location.
- Question terms may join an informational cluster with the same answer.
- Anything that fits nowhere goes to an "Orphan keywords" table with the reason.

## Modifier to page type
best / top: listicle · how to: tutorial · X vs Y: comparison · for [audience]:
audience page · tools / software: review or roundup · pricing / buy: product or
landing page.

Funnel tag: what is / why = TOFU; best / vs / review = MOFU; pricing / buy /
[brand] demo = BOFU.

## Map to URLs
Per cluster: "existing page: /url" or "new page needed" with a recommended slug.

## Output
Per cluster: name, intent, funnel stage, content type, URL, and a table of
Keyword | Volume | Difficulty | Role (Primary / Secondary / Supporting). Then the
orphan table and a roadmap: Priority | Cluster | Type | Primary KW | Est. traffic.
