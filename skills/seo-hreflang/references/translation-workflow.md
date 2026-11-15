# Translate, Localize and Link Across Languages

`seo-hreflang` audits translations. This reference covers producing them and
wiring them together.

## 1. Per-market keyword research (never translate the keyword list)

- Research each market natively: autocomplete with that market's `hl` and `gl`,
  a live SERP with that market's location, and volume data for that country.
- Volumes and phrasing differ sharply: the English head term can be small in a
  market where the local "{product} + buy verb" phrase dominates.
- Learn each language's transactional word order. German and Dutch put the verb
  after the noun ("{product} kaufen", "{product} kopen"); Spanish puts it before
  ("comprar {product}"). Lead the buyer page's title and H1 with that phrase.
- Each market has its own trust, payment and location modifiers (local payment
  brands, local words for "reviews" or "legit", the country name). Cover them in
  that locale's copy and FAQ.
- Output: | Source keyword | Target keyword | Local volume | Notes |

## 2. Element inventory

Body, headings, CTAs, title, meta description, URL slug, image alt text, JSON-LD
text values, navigation labels, UI strings (buttons, forms, errors).

## 3. Translation rules

- Translate meaning, not words; adapt examples, idioms and cultural references.
- Localize numbers, dates, currency and units (`locale-formats.md`).
- Keep the heading structure; put the local keyword in title, H1 and opening.
- Keep brand names and established technical terms where locals use them.
- One language per page; translate alt text and schema strings; support RTL.
- Each locale page needs unique text written for that market. A thin
  translation of a thin page tends to end up "Crawled, currently not indexed".
- Machine output gets human review before important pages ship
  (`machine-translation-qa.md`).
- Write the source-language page first, then localize; track source and
  translation pairs so updates propagate (`content-parity.md`).

## 4. URL structure choice

| Option | Example | Pros | Cons |
|---|---|---|---|
| Subdirectory | /fr/ | Easiest; shares domain signals | One host location |
| Subdomain | fr.site.com | Separate hosting possible | Signals more separated |
| ccTLD | site.fr | Strongest local signal | Costly; each builds authority separately |

Default to subdirectories unless there is a legal, brand or market reason not
to. Localize slugs consistently per language.

## 5. Cross-language linking

- The language switcher uses crawlable `<a href>` links to the EQUIVALENT page
  in the other language, not that language's homepage; present on mobile too.
- Internal links on a language version point to same-language targets (flag
  cross-language internal links outside the switcher).
- Each article visibly links its other-language versions, alongside hreflang.
- hreflang set includes self and x-default; `<html lang>` set; self-canonical
  per language (never canonical to the source language).

## 6. Market localisation of trust and conversion elements

Payment methods buyers in that market expect (for example local bank-transfer
schemes vs cards), currency, shipping times and costs, returns terms, legal
notices. Confirm against what the business actually offers; never list
unsupported methods.

Check every locale's index status separately; sitemaps and AI-visibility
prompts are maintained per language.
