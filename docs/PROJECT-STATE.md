# Halal-Career — Project State (session handoff, 2026-07-08)

Read this before major work. CLAUDE.md has the operating rules; this file has history, decisions, and todos.

## What exists

- **Architecture:** full career-ops (MIT, santifer — attribution stays) + halal layer on top. Renamed HalalOps→Halal-Career 2026-07-06. Repo: github.com/moin-ai/halal-career (private) · local F:\Halal-Career · skill installed at `C:\Users\arifu\.claude\skills\halal-career\` (SYNC after skill edits: `cp -r skill/halal-career/. <installed>`).
- **Gate wiring:** modes/halal-gate.md runs before A–G in oferta (Paso -1), auto-pipeline (0.5), batch-prompt (1.5); _shared.md ALWAYS rule -1; scan.md step 0 = watchlist pre-filter. HARAM → report + SKIP + stop.
- **Skill:** SKILL.md + 13 references (citations ledger, rulings, duas, verification, company-research, career-fit, apply-kit, outreach-followup, interview-prep, discovery-pipeline, compare-grow, exit-mode, watchlist-snapshot) + 17 vendored career-ops scripts + templates/fonts. 100% career-ops feature parity, all original text.
- **Citations:** ledger has 20 Quran verses + 17 hadith, all live-verified. APIs: api.quran.com (translation ID 20=Saheeh Intl; 131 doesn't exist; 44 language IDs in verification.md) · fawazahmed0 CDN (Muslim: match on `arabicnumber`, NOT `hadithnumber`!) · hadeethenc.com (70 langs) · hadithapi.com (key in .env). BLOCKED: sunnah.com (403), dorar.net — link-only. Ibn Majah 4250 has split grading (Albani: Da'if) — cite with both or skip.
- **Watchlists:** Palestine/Uyghurs/Kashmir/Rohingya; cloud routine `halal-career-watchlist-update` (trig_017orVjKXTbtjKa8KaEnady1), every 2d 02:00 UTC. ⚠ It silently auto-disabled once (repo access) for ~3 weeks; re-enabled 2026-07-06.
- **Company research:** 6-tier. Verified working: Wikipedia REST, GLEIF (fulltext filter), SEC EDGAR (needs User-Agent; XBRL companyfacts), AFSC Investigate (fetchable profiles). Via site: search only: Who Profits, Violation Tracker, ASPI. OpenSanctions needs free key. USAspending API finicky → website route.
- **Employer index:** knowledge/employer-index.md — 37 entries, self-growing (gate checks first, updates after; 12-month staleness).
- **Halal job sources:** assets/templates/halal-portals.yml (Muslim boards + Islamic-economy employers) + merged into Moin's portals.yml (52 queries, 38 companies, YAML-validated).
- **Evaluations:** 053 AI HIVE ✅3.0 borderline · 054 GDEX ✅(SC Shariah-listed) 3.6 apply, CV+cover generated in output/GDEX/ · 055 Allianz ❌HARAM (+posting dead). Tracker rows 80–82.
- **skill-forge:** permanent skill (user scope) encoding Anthropic's skill guide — use for any skill build.
- **Business Gate (2026-07-08, v1.1.0):** `references/business-gate.md` — validates business ideas the user OWNS: batched fiqh intake (qabd, riba, gharar/maysir, ghish, partners) → per-component rulings → verdict incl. new 🔧 CONDITIONAL (list restructures). rulings.md gained § Business Ownership & Trade (dropshipping/wakalah/salam, funding, revenue decomposition, mystery-box maysir). Ledger +4 verified 2026-07-08: Quran 2:188, Tirmidhi 1232, Bukhari 2079, Tirmidhi 1315. Fiqh source probe: aaoifi/iifa-aifi/sc.com.my/muftiwp/askimam/seekersguidance/amanahadvisors/themwl = 200 fetchable; daruliftaa.com (522) + darulifta-deoband.com (403) = LINK-ONLY (table in citations.md).
- **Mandatory Disclaimer (all reports, both pipelines):** exact block in SKILL.md § Mandatory Disclaimer (not-a-fatwa, AI-can-err, seek scholar, no liability, Quran 16:116) — dua first, disclaimer last, never omitted. Wired in modes/halal-gate.md too.
- **Global slash commands** (user scope `C:\Users\arifu\.claude\commands\` + repo copy `.claude/commands/`): /halalcheck (router), /halalbiz (business gate), /halaljob (job gate), /halaldua. Registered and working.
- **Multilingual READMEs (2026-07-08):** 22-language selector in README.md; all non-English files are honest stubs w/ native pitch + contribute instructions; career-ops-era es/cn/ja/ko/pt-BR/ru/zh-TW translations replaced (P3 item done); Uyghur flag ☪️ not 🇨🇳.

## Template design (settled — do not relitigate)

Single column · name centered ALL-CAPS 29px + keyword role-line under it · **DM Sans only** (hierarchy by weight/size; Space Grotesk retired) · **one accent color** via `:root{--accent}` — default navy #1F4E79, brand-match per employer only if darkened contrast-safe (GDEX: #A6151D; never raw brand colors; never mimic fonts) · body 13px≈10pt, line-height ~1.4 · **margins 0.65in from generate-pdf.mjs ONLY — HTML body has NO padding** (double-margin bug: script 0.6 + body 0.6 = fixed) · Month-Year dates · policy lives in apply-kit.md §Brand Accent. CV target 2 pages.

## Key decisions & why (don't re-argue)

1. Career-ops kept + attributed: MIT makes it legal; erasing attribution = MORE legal risk + against adab (user accepted).
2. No unsourced claims anywhere; scripture only from ledger or live verification; tool reports scholarship, never issues fatwas; mashbooh_tolerance strict; madhab = hanafi, present_all_madhabs true (asked once, saved).
3. Tracker TSV 9-col schema unchanged — halal verdict travels in Notes prefix (`✅ HALAL |` / `HARAM:`) + report `**Halal:**` header, so merge-tracker.mjs etc. keep working.
4. Branch protection impossible on free private repo → deferred to public release (rulesets free once public).
5. PDF needs Playwright (installed); fallback = browser print-to-PDF. Not a blocker.
6. Muslim job boards ≠ automatically halal — everything still passes the gate; Islamic windows of conventional banks = mashbooh (gate presents split).

## TODO (priority order)

**P0 — use it:**
- [ ] Submit GDEX application (ask EP sponsorship FIRST; docs ready in output/GDEX/); then follow-up +7d
- [ ] Live-test `node scan.mjs` with halal portals (never run end-to-end)
- [ ] Dry-run Exit Mode + onboarding as fresh user (both untested)

**P1 — reliability:**
- [ ] Watchlist heartbeat: routine prompt appends last-run date to _index.md; gate warns if >7d stale (routine died silently once)
- [ ] Disk hygiene: 3 stray career-ops copies (F:\CareerOps, f:\Claude\career-ops, f:\Claude\career-ops-main.zip) — archive/delete to prevent wrong-tree edits

**P2 — growth:**
- [ ] Employer index → top-100 (batches of ~10: Petronas, Grab, Shopee, AirAsia, TM, Maxis, GLCs, FAANG, Big4)
- [ ] Scholar review package (rulings + ledger + exit-mode purification section **+ NEW muamalat/business-gate section**) — REQUIRED before public release; candidates: local JAKIM-affiliated mufti, Amanah Advisors (Mufti Faraz Adam — extra fitting now, his papers are the business gate's Tier-3 source)
- [ ] Dry-run the Business Gate end-to-end on a real idea (untested; try a dropshipping example — exercises intake, CONDITIONAL verdict, and restructure list)

**P3 — later:**
- [ ] Green List (deen-friendly employers — populates from post-interview annotations)
- [ ] Purification calculator (only after scholar sign-off)
- [ ] Public release: make repo public → enable ruleset, our own multilingual READMEs, CONTRIBUTING w/ evidence template; career-ops translated READMEs still describe career-ops (replace or delete)
- [ ] Verdict API/MCP for Muslim job boards · Calibri template variant · LaTeX template not restyled to new design

## Roadmap vision (agreed direction)
Exit Mode ✅ built → Employer Index public asset → scholar review → open-source release (waqf model if monetized) → browser extension / API. Positioning: "Zoya for your career" — first halal employer screener.
