# Discovery, Pipeline & Batch

## Scan — find new openings
Config lives in user data as `portals.yml` (create on first use): `tracked_companies` (name, careers_url, ats provider), `search_queries`, `title_filter` (positive/negative keywords).

**Halal default sources:** `assets/templates/halal-portals.yml` ships pre-populated with Muslim job boards (UmmahJobs, MuslimJobs, WorkHalal, Barakah Jobs, HijraJob, Muslim Professionals), Islamic-economy employers (IsDB, IFSB, fully-Islamic banks, takaful), Muslim tech (LaunchGood, Tarteel, Zoya, Musaffa, Wahed, Yaqeen, Quran Foundation), Islamic relief orgs, and Islamic-finance queries on mainstream boards (Bayt, JobStreet, NaukriGulf). On onboarding — or whenever the user says "find me halal jobs" — offer to merge it into their `portals.yml`, substituting their role keywords into the `{role keywords}` placeholders. Be honest with the user: a listing on a Muslim board is NOT automatically halal — every result still passes the gate (and Islamic windows of conventional banks are mashbooh per some scholars; the gate presents the split).

**Halal pre-filter (always step 0):** drop any company on the watchlist Highest-Confidence tier before it enters the pipeline (log `HARAM-prefiltered`); Medium-tier companies pass through flagged `⚠ watchlist` for the gate to investigate fully.

Three additive levels, dedup across all:
1. **ATS APIs** (fast, structured — try first when provider known):
   - Greenhouse: `https://boards-api.greenhouse.io/v1/boards/{company}/jobs` → `jobs[].title/.absolute_url`
   - Lever: `https://api.lever.co/v0/postings/{company}?mode=json` → `[].text/.hostedUrl`
   - Ashby: `https://jobs.ashbyhq.com/api/non-user-graphql?op=ApiJobBoardWithTeams` (POST, `organizationHostedJobsPageName`) → `jobBoard.jobPostings[]`
   - Teamtailor: `https://{company}.teamtailor.com/jobs.rss` · BambooHR: `https://{company}.bamboohr.com/careers/list` · Workday: `https://{company}.{shard}.myworkdayjobs.com/wday/cxs/{company}/{site}/jobs`
2. **Browser** (SPAs without APIs): navigate careers_url, snapshot, extract title+URL per listing.
3. **WebSearch** (`site:` queries) for discovering companies not yet tracked — results may be stale, verify before pipeline entry.

Filter titles against `title_filter`, dedup against scan history + tracker + pipeline, then append survivors to the pipeline inbox. Record every URL seen (even rejected) in `{data}/scan-history.tsv` with date + disposition.

## Pipeline — the URL inbox
`{data}/pipeline.md`: one line per pending offer (`- {url} — {title} — {company} — added {date}`). "Process the pipeline" → evaluate each entry oldest-first through the full flow (halal gate → A–G), remove processed lines, tracker rows added. Cap per run (default 5) to keep quality; tell the user what remains.

## Batch — many offers at once
For N>5 offers: spawn parallel evaluation agents (background), each running the full gate+evaluation for one offer and writing its own report + a single tracker-addition line to `{data}/tracker-additions/`. After ALL return: merge additions into the tracker (dedup on company+role — update existing rows, never duplicate), then present a ranked digest. Never run browser automation in more than one agent at a time.

## Liveness check (before any application effort)
Postings die silently. Before generating documents or answers, verify the posting is live: browser-navigate and confirm title + description + apply control are present (footer-only page = dead). No browser available → WebFetch and mark the report `Verification: unconfirmed`. An expired signal ("no longer accepting applications") beats a generic Apply button.

## Onboarding (first run)
Before any evaluation, silently check user data exists: CV (`cv_data` path or `cv.md`), `profile.yml` (identity, target roles, comp targets, fiqh.madhab), tracker file. Anything missing → guided setup: (1) CV — paste it / LinkedIn URL / describe experience, convert to clean markdown; (2) profile — name, location, target roles, salary range, madhab; (3) create empty tracker. Then invite deeper context (superpowers, deal-breakers, best achievement, red lines) — store in profile.yml. After every evaluation, learn: user corrections ("score too high", "I know X") update the profile, never the skill.
