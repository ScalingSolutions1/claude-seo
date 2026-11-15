# Video SEO Playbook: Text Twins and YouTube Demand

## Text twin (one per meaningful video)

Every substantial video gets its own indexable page on your domain: a watch
page, or an article built around the video.
- The video is the main content, embedded near the top.
- A cleaned full transcript, or an edited article version, in the HTML (not
  behind a click or tab).
- Timestamped chapters linking to moments in the video.
- An answer-first summary of 40-60 words.
- VideoObject markup: `name`, `description`, `thumbnailUrl`, `uploadDate`,
  `duration`, `contentUrl` or `embedUrl`, `transcript`, `creator`. Add `Clip`
  items for chapters, or `SeekToAction` so Google can generate key moments.
- A video sitemap entry or VideoObject on the page; one canonical watch page
  per video.

Why: search and AI engines read text. A text twin makes the video's facts
indexable and citable, and connects the YouTube entity to your site.

## On YouTube itself

- Title front-loads the searched phrase; chapters in the description; accurate
  captions uploaded; a link to the text twin in the first description lines.
- Keep entity facts (brand name, descriptor, links) identical to the site
  (`seo-geo/references/offsite-entity-building.md`).

## Demand research

- YouTube search suggestions and the question wording in titles and comments
  supply H2s and FAQs (`youtube_search.py` (via `"${CLAUDE_PLUGIN_ROOT}/scripts/claude-seo" run`)).
- Prefer topics with high demand and low competition.
- YouTube demand does not prove web demand: validate against Search Console,
  keyword volume and the live SERP before building a web page. A video carousel
  in the Google SERP signals that a video-led page can rank.
