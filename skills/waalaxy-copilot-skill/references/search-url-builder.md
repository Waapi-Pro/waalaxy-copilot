# Search URL builder

Turn a locked target into a LinkedIn search, then import into Waalaxy.

All instructions here are in English (system language). Every string SHOWN to the user — warnings,
action lists, notes — must be rendered in the user's language. The templates below are English
specimens of what to say, not literal output.

---

## Default flow

1. Always generate the standard LinkedIn URL first.
2. If Sales Nav would add meaningful precision for this target, explain it in 2-3 lines (only if true).
3. Ask whether the user has Sales Navigator.
4. Based on the answer: produce the Sales Nav payload, or present the partner.

---

## Step 1 — Standard LinkedIn URL (always)

Base: `https://www.linkedin.com/search/results/people/`

Parameters:
- `keywords` — titles in Boolean: `("Gérant" OR "Directeur Général") NOT stagiaire`
- `geoUrn` — country geo ID, encoded as `%5B%22105015875%22%5D`
- `industry` — V2 numeric code(s), encoded as `%5B%22CODE%22%5D`
- `origin` — always `FACETED_SEARCH`

### Country geoUrn table (Captain Data, country level only)

| Country | geoUrn |
|---|---|
| France | 105015875 |
| Belgium | 100565514 |
| Spain | 105646813 |
| England | 102299470 |
| Germany | 101282230 |
| Italy | 103350119 |
| United States | 103644278 |
| Canada | 101174742 |
| Australia | 101452733 |
| India | 102713980 |
| China | 102890883 |
| Japan | 101355337 |
| Brazil | 106057199 |
| Mexico | 103323778 |
| Netherlands | 102890719 |
| Singapore | 102454443 |
| Switzerland | 106693272 |
| Sweden | 105117694 |
| South Korea | 105149562 |
| Russia | 101728296 |
| United Arab Emirates | 104305776 |

Combine countries: `geoUrn=%5B%22105015875%22%2C%22100565514%22%5D`

Regions (Auvergne-Rhône-Alpes, etc.): IDs are not in a reliable public list. Use the UI fallback.

### Industry codes

Use `references/industry-codes.md` for exact labels and numeric V2 codes (434 industries). Put the
numeric code directly in the `industry` parameter.

Encoding:
- 1 industry: `industry=%5B%22CODE%22%5D`
- Multiple: `industry=%5B%22CODE1%22%2C%22CODE2%22%5D`

Example, Software Development (4) + IT Services and IT Consulting (96): `industry=%5B%224%22%2C%2296%22%5D`

With the industry code in the URL, the user does not need the UI filter for sector.

### Building the URL

1. Titles in `keywords`, Boolean, URL-encoded.
2. Country geoUrn from the table if the target is country-level.
3. Industry numeric code(s) in `industry`.
4. If region is sub-country (not in the geoUrn table): build the partial URL, then show the warning
   and action list for the UI step.

### Output format

Show the URL. If a filter cannot be embedded (sub-country region), show a warning then an action list.

WARNING template (render in user's language):
> ⚠️ This URL is incomplete. Without the steps below you will get off-target results.

ACTION LIST template (render in user's language, fill the exact values):
- Open the URL in LinkedIn
- Click **Locations** → select [exact region]
- Copy the final URL from the address bar
- Import it into Waalaxy via the LinkedIn import

### Example

Target: Founder / CEO, Software Development, 1-10, France. Country + industry both embeddable:

```
https://www.linkedin.com/search/results/people/?keywords=%28%22Founder%22%20OR%20%22CEO%22%20OR%20%22Co-founder%22%29&origin=FACETED_SEARCH&geoUrn=%5B%22105015875%22%5D&industry=%5B%224%22%5D
```

Complete URL, no UI step needed. Import directly into Waalaxy.

---

## Step 2 — Transition to Sales Nav (contextual)

After the standard URL, judge whether Sales Nav adds meaningful precision for THIS target.

Mention Sales Nav only when at least one applies:
- Company size is a key criterion (e.g. BET 1-50, SaaS 51-200)
- Seniority needs precise filtering (e.g. exclude juniors on a decision-maker target)
- The target is broad and would exceed 2,500 results on standard LinkedIn

If relevant, explain in 2-3 lines max the specific extra filters useful for this target. No generic
list. Then ask (render in user's language): "Do you have access to Sales Navigator?"

---

## Step 3 — Based on the answer

### User has Sales Nav → produce the payload

Do not hand-build a Sales Nav URL; the query string is opaque and unstable. Produce a structured
filter payload the user applies in the Sales Nav UI.

Payload generation method (B2B strategist): translate the target into Sales Nav filters. Use only
filters the target justifies. Quality > quantity: a precise 5-7 filter search beats a padded 12-filter one.

CORE filters (always set when the matching ICP field exists):
- `current_title.include` — 4 to 6 real LinkedIn titles
- `current_title.exclude` — 2 to 4 adjacent-but-wrong titles
- `seniority_level` — strict enum: Owner, Partner, CXO, VP, Director, Manager, Senior, Entry, In Training
- `geography` — country or major region Sales Nav recognizes; never city or département
- `industry` — LinkedIn industry labels verbatim
- `company_headcount` — strict bands: Self-employed, 1-10, 11-50, 51-200, 201-500, 501-1000, 1001-5000, 5001-10000, 10001+

EXPLORATORY filters (add only when the target justifies):
- `function` — strict enum: Accounting, Administrative, Arts and Design, Business Development, Community and Social Services, Consulting, Education, Engineering, Entrepreneurship, Finance, Healthcare Services, Human Resources, Information Technology, Legal, Marketing, Media and Communications, Military and Protective Services, Operations, Product Management, Program and Project Management, Purchasing, Quality Assurance, Real Estate, Research, Sales, Support
- `years_in_current_position` — 0-25; when the pain implies tenure
- `company_type` — strict enum: Public Company, Privately Held, Nonprofit, Educational Institution, Partnership, Self-Employed, Self-Owned, Government Agency
- `profile_language` — "French", "English", etc.

Rules:
- Titles are real LinkedIn strings, never job families
- "Head of X" → seniority Director (Sales Nav has no "Head" enum)
- Each exploratory filter must be justifiable by the target
- Exclusions only when the target explicitly justifies cutting them

Output the payload as a checklist, then an action list (both rendered in user's language):

Titles include / Titles exclude / Seniority / Geography / Industry / Company size / Function (if justified) / Years in position (if justified) / Company type (if justified)

ACTION LIST template:
- Open Sales Navigator → People search
- Apply each filter above
- Check result count: aim for 1,000 to 1,500
- Too broad: tighten company size or seniority
- Too narrow: widen titles or add an adjacent industry
- Save the search in Sales Nav (Waalaxy auto-syncs every 12h)
- Import into Waalaxy via the Sales Navigator import

### User does NOT have Sales Nav → present the partner

Present once (render in user's language), then move on:
> Sales Navigator costs ~€100/month direct. Waalaxy has a partnership with SalesNavSplit giving
> access at -60% by sharing a licence. It's the most-used route for Waalaxy customers who want
> Sales Nav without full price.
> 👉 https://salesnavsplit.com/waalaxy-partnership

Do not insist. Offer once, continue.

---

## After delivering the URL or payload

One line: estimated volume and the filter doing the heavy lifting.
One line: reminder of 1,000-1,500 max prospects for an effective Waalaxy campaign.
Update `prospecting-strategy.md` with the search section.
