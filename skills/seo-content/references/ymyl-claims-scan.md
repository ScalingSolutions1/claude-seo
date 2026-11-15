# YMYL Claims and Trust-Risk Scan (health, finance, legal, safety)

Run on the extracted text of every in-scope page of a YMYL site. Each hit is a
Trust finding (High or Critical for health and finance). Report page, a short
quote, and the fix.

| Check | Flag when |
|---|---|
| Absolute outcome claims | cure, heal, treat (as a promise), guaranteed, no side effects, 100% safe, risk-free, "clinically proven" without a cited trial |
| Practitioner language from non-practitioners | patient, prescribe, diagnose, or medical / financial / legal titles the author does not hold; applies to Person `jobTitle` in schema too |
| Instruction content | doses (a number plus mg / mcg / IU / ml near a substance), administration routes, schedules, "how to take", on pages not authored and reviewed by a qualified professional, or used as ad destinations |
| Ungraded claims | a claim about effects with no evidence level; label each claim (First-hand: author's own data / Reported: clients or community / Studied: cited research / Speculative), and label anecdote as anecdote |
| Sourcing | YMYL claims without primary sources (peer-reviewed research, guideline bodies, regulators), or no visible "Updated" date |
| Commercial links | links to a seller that are not plain citations, without `rel="sponsored"` and a visible disclosure; undisclosed discount codes; wording implying an affiliation that does not exist |
| Testimonials | not named or consented; no "individual result, not a promise" framing; incentivised testimonials not labelled |
| Fake pressure | countdown timers, "last chance", scarcity numbers that differ between pages |
| Scope disclaimer | no site-wide scope line (for example "Education, not medical advice") in the footer and on articles |
| Entity naming | legal-entity name used outside legal pages, checkout and invoices; brand name spelled inconsistently |

Rules:
- Every fix the audit proposes must pass this scan itself.
- Niche regulation (pharmacy, supplements, financial promotions, gambling) varies
  by market: name the market, and recommend legal review rather than asserting
  what the law requires.
