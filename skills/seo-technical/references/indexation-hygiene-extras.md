# Indexation Hygiene and Exposure Checks (extras)

Additional checks for the Indexability and Security categories.

## Utility and placeholder pages

- Utility pages are `noindex`: form thank-you or confirmation pages,
  quiz or calculator result pages, per-user and session pages, internal search
  results. Money and content pages stay indexable.
- Placeholder or "coming soon" pages for features not yet launched are not
  indexable: noindex them, or remove them until launch.
- A blog mirrored under two paths (for example a subdomain and `/blog`) needs
  one canonical home.

## Parameters in canonicals and links

- Canonicals and internal links carry no CMS-appended or tracking parameters
  (language toggles such as `?hsLang=`, `utm_*`, session IDs, sort or filter
  parameters).
- A parameter inside a canonical URL is **High**.

## Age, region and consent gates

A gate that redirects to a separate page, or renders content only after a
click, can leave Googlebot and AI crawlers with an empty page.
- Keep the full content in the initial HTML and show the gate as an overlay or
  cookie-based dialog on top of it.
- Do not serve different content by user-agent (cloaking risk).
- Verify with URL Inspection (rendered HTML) and a raw-HTML fetch, which is
  what non-JS AI crawlers see.

## Exposed sensitive files

On sites the user owns or is authorised to audit, check whether these return
200 with real content:
- `/.env`, `/.git/HEAD`, `/.git/config`
- backup or dump files (`*.sql`, `*.zip`, `*.bak`, `*.tar.gz`)
- open directory listings

Any hit is **Critical**: a security issue first, and a risk of indexed leaks.
Fix by blocking at the server or CDN, never with robots.txt (which only
advertises the paths). Report the URL and status only; never paste file
contents into the report.
