# Company Research Protocol

Goal: know what the company ACTUALLY does — revenue truth, real owners, real clients — not its marketing copy. Endpoints marked ✅ verified working 2026-06-16. Every dossier claim gets: source + date + confidence (H/M/L).

## Tier 0 — Cache
`knowledge/companies/{slug}.md` exists → load it; only refresh sections older than 6 months or when the role demands (e.g. defense flag).

## Parallel research (>3 companies, agent-capable environments)
Researching many companies inline buries the session in fetched pages and degrades late-batch quality. When more than 3 companies need research (employer-index growth, scan pre-research, multi-client checks): spawn one researcher subagent per company (background, all in one message). Each agent gets this file's protocol + the company name, and returns ONLY the filled dossier template — no verdict. **Verdicts are ruled by the coordinating session** against the ledger and rulings — researchers dig, the gate judges. No agent capability → run the tiers inline, batched by company.

## Tier 1 — Identity & Ownership (always)
Resolve the TRUE entity before anything else. A clean subsidiary of a haram parent fails the gate; parent evaluation is mandatory.

- ✅ **Wikipedia REST**: `https://en.wikipedia.org/api/rest_v1/page/summary/{Title}` — instant identity, industry, ownership pointers.
- ✅ **GLEIF LEI** (no key): `https://api.gleif.org/api/v1/lei-records?filter[fulltext]={name}` — legal entities worldwide; follow `relationship-records` for parent/child (Level 2 data). Exact-name filter often misses — use fulltext.
- **OpenCorporates** via WebSearch `site:opencorporates.com {company}` — registrations, officers.
- Record: legal name, jurisdiction, parent chain to ultimate owner, ticker if listed.

## Tier 2 — Revenue Truth
**Listed companies** (best source — sworn filings):
- ✅ **SEC EDGAR** (free, needs any User-Agent header): company search `https://www.sec.gov/cgi-bin/browse-edgar?action=getcompany&company={name}&type=10-K&output=atom`; structured financials `https://data.sec.gov/api/xbrl/companyfacts/CIK{10-digit}.json`. Read the 10-K/20-F "Business" + segment revenue: what % from what. Interest income line → riba screen input.
- Non-US listings: annual report PDF from investor-relations page (WebFetch).

**Private companies:** company site (WebFetch) + WebSearch `{company} revenue model clients` + `site:crunchbase.com {company}`. Label confidence Medium at best — private financials are claims, not filings.

## Tier 3 — Halal Screeners (listed only)
- WebSearch `{ticker} halal musaffa OR zoya OR islamicly` — screener verdicts (AAOIFI-based) often public per ticker.
- No screener coverage → manual AAOIFI screen from EDGAR XBRL: impermissible revenue <5% of total; interest-bearing debt <30% of market cap; interest-bearing securities <30%. **State honestly**: AAOIFI thresholds govern share ownership; for employment they are an analogy, not a fatwa.

## Tier 4 — Government & Defense Contracts
- **USAspending.gov** — US federal awards incl. DoD, by recipient. API is POST-based and finicky; prefer `https://www.usaspending.gov/search` results via WebSearch `site:usaspending.gov {company}` or WebFetch of the recipient profile URL.
- UK: WebSearch `site:contractsfinder.service.gov.uk {company}`.
- Generic: WebSearch `{company} defense contract military` + `{company} ministry of defence`.

## Tier 5 — Ethics & Oppression Databases (always, alongside watchlists)
- ✅ **AFSC Investigate** (fetchable, structured): `https://investigate.afsc.org/company/{slug}` — Palestine/prisons/borders involvement, contract amounts, divestment record. Try slug = kebab company name; else WebSearch `site:investigate.afsc.org {company}`.
- **UN OHCHR settlement-business list** (official UN, A/HRC/43/71 + updates): WebSearch `OHCHR database settlements {company}` — the single most authoritative Palestine-complicity source.
- **Who Profits**: WebSearch `site:whoprofits.org {company}` (direct URLs 404 — use search).
- **ASPI Uyghur tracker**: WebSearch `site:aspi.org.au uyghur {company}`.
- **Business & Human Rights Resource Centre**: WebFetch `https://www.business-humanrights.org/en/companies/{slug}/` or site-search — tracked allegations + company responses (gives BOTH sides).
- **Violation Tracker** (US misconduct, direct fetch blocked): WebSearch `site:violationtracker.goodjobsfirst.org {company}`.
- **OpenSanctions** (sanctions/PEP screening): needs free non-commercial key (`OPENSANCTIONS_API_KEY` in .env); skip gracefully without.
- **BDS official**: WebSearch `site:bdsmovement.net {company}` — distinguish official targeted-boycott list from grassroots lists.

## Tier 6 — Ground Truth (what would YOU build)
- WebSearch `{company} glassdoor software engineer` — what engineers actually work on.
- LinkedIn company page + the JD itself: team names, product names → map your role to a revenue stream from Tier 2.
- News sweep: WebSearch `{company} controversy lawsuit` (cap at 2 searches).

## Synthesis Rules
1. **Confidence**: High = official filing/UN/court record OR 2+ independent credible sources. Medium = 1 credible source. Low = single activist/uncorroborated claim — report it labeled as such, never as fact.
2. **Disagreement** (e.g. company denies an allegation): present both, cite both, do not adjudicate.
3. **Dead ends are findings**: "no defense contracts found on USAspending (searched {date})" belongs in the dossier.
4. **Effort budget**: Tier 1-2 always; Tier 3 if listed; Tier 4-5 always but ≤6 searches total; Tier 6 if verdict still unclear. Small local business → Tier 1 + 6 may suffice; say so.

## Dossier Template (`knowledge/companies/{slug}.md`)
```markdown
# {Legal Name} ({ticker|private})
**Researched:** {date} · **Stale after:** {+6mo} · **Ultimate parent:** {name}
## Identity  (jurisdiction, structure, ownership — sources)
## Revenue  (segments + %, filing year — source)
## Halal screen  (screener verdict or manual AAOIFI + numbers)
## Contracts  (gov/defense findings incl. clean results)
## Ethics record  (per-database findings, confidence-labeled, incl. company responses)
## Role exposure  (what this JD's team builds → which revenue stream)
## Open questions
```
