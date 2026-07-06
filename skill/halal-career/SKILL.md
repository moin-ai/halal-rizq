---
name: halal-career
description: Evaluates job opportunities for Muslims in two stages — Islamic permissibility (halal/haram) first, then career fit. Screens the employer's core business, the candidate's specific role, and complicity in oppression, citing verified Quran, hadith, and fatwa sources. Use when user pastes a job description or company name and asks "is this halal", "evaluate this job", "can I work here as a Muslim", "halal check", or asks for duas related to work, rizq, or job seeking.
license: MIT
metadata:
  author: Arifuzzaman Moin
  version: 1.0.0
  repository: https://github.com/moin-ai/halal-career
---

# Halal-Career — Halal Career Evaluation

Two-stage pipeline. Stage 1 gates Stage 2: a haram role is never career-scored.

## Critical Rules

1. **Never cite scripture from memory.** Every Quran verse, hadith, or fatwa shown to the user MUST be verified live via `references/verification.md` protocol, or copied verbatim from `references/citations.md` (pre-verified ledger). No exceptions.
2. **Cite dual numbering** when collections have divergent schemes (Sahih Muslim especially): write both, e.g. "Muslim 1598 (Abd al-Baqi) / CDN#4093".
3. **Attribute gradings to named scholars** ("Al-Albani: Sahih"), never bare "authentic".
4. **The tool reports scholarship; it never issues rulings.** Frame verdicts as "according to [scholar/fatwa, linked]". On genuine scholarly dispute, present all positions and recommend Istikharah.
5. **User's madhab first**, then other schools, then majority note.
6. **No unsourced claims — anywhere.** Every factual assertion in any output — rulings, company facts, watchlist flags, market/salary figures, scholar attributions, statistics — carries a verifiable reference: a URL, an API-verified citation from the ledger, or a named document with date. A claim that cannot be sourced is either omitted or explicitly labeled `[analysis — no source]`. Applies equally to Stage 1 and Stage 2. The user must be able to check everything themselves.

## Data Locations

- **User data** (profile, evaluations, tracker): `F:/Halal-Career/` if it exists, else create `./halal-career/` in the working directory with `config/profile.yml`, `evaluations/`, `tracker.md`.
- **Skill knowledge** (read-only): this folder's `references/`.
- Richer data (full rulings, live watchlists, company dossiers) lives in the user's Halal-Career repo when present — prefer it over bundled snapshots.

## First Run — Onboarding

Before any evaluation, check user data exists (CV, profile.yml, tracker). Missing → guided setup per `references/discovery-pipeline.md` § Onboarding. Never evaluate against an empty profile.

## Stage 0 — Madhab (once)

Read `config/profile.yml → fiqh.madhab`. If missing or `prompt_user`: ask (Hanafi / Shafi'i / Maliki / Hanbali / present all), save the answer, never ask again.

## Stage 1 — Halal Gate

1. **Parse** JD: company (+parent), role, what the user would actually build/do.
2. **Research company**: follow `references/company-research.md` — tiered protocol (identity/ownership → revenue truth from filings → halal screeners → contracts → ethics databases → ground truth). Cache result as dossier.
3. **Oppression check**: consult `knowledge/oppression-watch/_index.md` (repo) or `references/watchlist-snapshot.md` (bundled fallback). Also WebSearch `"{company} Israel military | Uyghur | Myanmar"` for anything newer. Record confidence H/M/L + source.
4. **Apply rulings**: load matching section of `references/rulings.md` (riba, insurance, defense, alcohol/tobacco, gambling, indirect-tech). Present user's madhab position first with verified citations, then others.
5. **Red lines**: check every entry in `profile.yml → personal_red_lines`. Any trigger → HARAM.
6. **Verdict**:
   - ❌ HARAM — clear prohibition (majority + user's madhab) or red line or High-confidence oppression flag → write report, STOP.
   - 🟠 MUKHTALAF — real scholarly split, no clear majority.
   - 🟡 MASHBOOH — doubtful / Medium-confidence flag.
   - ✅ HALAL — clear on all six checks.
   - For 🟡/🟠: append Istikharah reminder + dua (from `references/duas.md`).

## Stage 2 — Career Fit (only if not HARAM)

Follow `references/career-fit.md`: A) Role summary, B) CV match & strategy, D) Comp & demand (with a recommended ask), E) Personalization plan, F) STAR+R interview prep, G) Posting legitimacy → Score /5 with stated deductions. Recommend against applying below 3.5 unless the user has a reason.

## Stage 3 — Application Lifecycle (on request)

| User wants | Follow |
|------------|--------|
| Find new openings / "scan" / process URL inbox / many offers at once | `references/discovery-pipeline.md` (scan + pipeline + batch + liveness) |
| Tailored CV / cover letter / form & screening answers | `references/apply-kit.md` |
| LinkedIn outreach / follow-ups / "what's due?" | `references/outreach-followup.md` |
| Interview prep (incl. deen accommodations) | `references/interview-prep.md` |
| Compare offers / evaluate a course, cert, or portfolio project / external research prompt | `references/compare-grow.md` |
| Outcome recorded / "what's working?" | tracker update + pattern learning (`career-fit.md` § Tracker) |

Document output: markdown or self-contained HTML by default; user has a template/pipeline (HTML→PDF script, LaTeX/Overleaf, Canva) → use theirs. Verify a posting is live (liveness check) before investing document effort.

Lifecycle ethics: draft everything, submit nothing — the user sends; never record a draft as sent; never invent experience anywhere.

## Script Acceleration (optional — Node ≥18)

This skill bundles zero-token tooling in `scripts/` (vendored from career-ops, MIT — see `scripts/NOTICE.md`) and CV templates/fonts in `assets/`. When Node is available, PREFER scripts over token-driven equivalents:

| Task | Run from user project root |
|------|---------------------------|
| Portal scan | `node scripts/scan.mjs` (after copying `assets/templates/portals.example.yml` → `portals.yml`) |
| CV PDF | `node scripts/generate-pdf.mjs {in.html} {out.pdf} --format=a4` with `assets/templates/cv-template.html` |
| Liveness | `node scripts/check-liveness.mjs {url}` |
| Follow-up due dates | `node scripts/followup-cadence.mjs` → JSON |
| Pattern analysis | `node scripts/analyze-patterns.mjs` → JSON |
| Tracker hygiene | `node scripts/merge-tracker.mjs`, `dedup-tracker.mjs`, `normalize-statuses.mjs` |
| Health check | `node scripts/doctor.mjs` |

First script use: copy `scripts/package.json` to the project root and `npm install`. Scripts expect the layout onboarding creates (`config/profile.yml`, `data/`, `reports/`). No Node → every capability still works instruction-driven; scan results via ATS API fetches, PDFs via user's print-to-PDF, cadence/patterns computed by the model. The halal gate and scan pre-filter apply identically in both paths — scripts discover, the gate still decides.

## Output

Save report to `evaluations/{company}-{role}-{YYYY-MM-DD}.md` using the template in `references/career-fit.md`. Append one row to `tracker.md`. End every report with one contextually relevant dua from `references/duas.md` (verified Arabic + translation + source).

## Duas

When the user asks for work/rizq-related duas — or a report warrants one — use `references/duas.md` only. Never compose or recall duas from memory.

## Language

Respond in the user's language automatically. Prose (analysis, verdicts, career fit) — translate freely. Scripture — NEVER self-translate: fetch the verified translation in the user's language using the per-language sources in `references/verification.md` (§ Languages). Arabic text is always included unchanged. If no verified translation exists in the user's language, give the English verified text plus your translation clearly labeled "unofficial rendering — verified text in English above".

## Troubleshooting

- API unreachable → cite from `references/citations.md` (pre-verified) and mark "ledger citation, live check unavailable".
- Company not identifiable → evaluate what is known; verdict confidence Low; tell the user what to confirm.
- User insists on applying despite HARAM → present the ruling once with sources, respect their agency, do not re-argue.
