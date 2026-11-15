# Entity Consistency and Off-Site Citation Building

AI engines cite brands they can resolve and corroborate. This reference covers
the on-site entity card, the off-site footprint, and honest placement in the
sources engines already cite.

## 1. Entity fact sheet (do this first)

Write one canonical sheet:
- Brand name in exactly one spelling.
- One fixed one-line descriptor: "X is a {category} that {does Y} for {audience}".
- Founder or author name and role.
- Hard facts: founding year, markets served, delivery times, payment methods,
  pricing model, key people.

Use those exact facts on the homepage, about page, Organization and Person
schema (`sameAs` to every owned profile), and every profile, directory and
listing. Contradictory facts across sources lower an engine's confidence.

Audit: list every variant found (spelling, descriptor, job title, founding year)
with the URL where it appears. Each variant is a finding.

## 2. Owned profiles

- Every owned channel bio (social, video, podcast, marketplace, directory) names
  the brand exactly and links to the site.
- **Text twins:** every substantial video or podcast episode has an indexable
  text version on the site (summary, key claims, transcript), linked from the
  video or episode description. See `seo-google/references/video-seo.md`.
- AI engines cite YouTube, LinkedIn and X directly; keep entity facts identical there.

## 3. Mention inventory

- List existing third-party mentions: podcasts, guest articles, industry
  communities, disclosed forum answers by the founder, reviews, directories.
- Compare against the "cited instead" sources from the AI-answer panel
  (`ai-answer-visibility.md`). The gap between the two lists is the outreach list.

## 4. Get into the sources engines already cite

- Target the comparison lists, review databases, niche directories and
  testing or verification sites that engines cite for your topic.
- Get listed on their merits. Any paid or affiliate placement is disclosed and
  carries `rel="sponsored"`. Paid followed links violate Google's link-spam
  policy; a "best X" listicle you host on someone else's domain falls under site
  reputation abuse.

## 5. Community participation (Reddit, forums, Q&A)

- One named, real, disclosed account per brand or person. Answer questions;
  don't post promotions.
- Disclose affiliation in every relevant answer and label affiliate links.
- Never: sock puppets, incentivised mentions, mention farming, fake reviews,
  paid links, parasite listicles. Inauthentic mention-chasing is unhelpful and
  risks spam policies.

## 6. Entity identifier block (topic entities)

When a page is about a specific substance, material, component, standard,
species or model, add a small visible table of its canonical identifiers from
authoritative registries (chemical registry numbers, standard or spec numbers,
scientific names, model numbers, Wikidata QID) with links. Mirror them in
markup (`identifier`, `sameAs`, `additionalProperty`, `about` / `mentions`
pointing at the entity).

Use the same identifiers on every page about that entity (product, guide,
comparison) so they all resolve to one entity. Only list identifiers verified
at the registry.

## Report

| Item | Status | Evidence (URL) | Fix |
Sections: entity variants found, profile bio gaps, missing text twins, mention
inventory vs cited-instead gap, outreach targets (with disclosure note).
