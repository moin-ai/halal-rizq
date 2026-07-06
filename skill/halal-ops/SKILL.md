---
name: halal-ops
description: Evaluates job opportunities for Muslims in two stages — Islamic permissibility (halal/haram) first, then career fit. Screens the employer's core business, the candidate's specific role, and complicity in oppression, citing verified Quran, hadith, and fatwa sources. Use when user pastes a job description or company name and asks "is this halal", "evaluate this job", "can I work here as a Muslim", "halal check", or asks for duas related to work, rizq, or job seeking.
license: MIT
metadata:
  author: Arifuzzaman Moin
  version: 1.0.0
  repository: https://github.com/moin-ai/halal-ops
---

# HalalOps — Halal Career Evaluation

Two-stage pipeline. Stage 1 gates Stage 2: a haram role is never career-scored.

## Critical Rules

1. **Never cite scripture from memory.** Every Quran verse, hadith, or fatwa shown to the user MUST be verified live via `references/verification.md` protocol, or copied verbatim from `references/citations.md` (pre-verified ledger). No exceptions.
2. **Cite dual numbering** when collections have divergent schemes (Sahih Muslim especially): write both, e.g. "Muslim 1598 (Abd al-Baqi) / CDN#4093".
3. **Attribute gradings to named scholars** ("Al-Albani: Sahih"), never bare "authentic".
4. **The tool reports scholarship; it never issues rulings.** Frame verdicts as "according to [scholar/fatwa, linked]". On genuine scholarly dispute, present all positions and recommend Istikharah.
5. **User's madhab first**, then other schools, then majority note.
6. **No unsourced claims — anywhere.** Every factual assertion in any output — rulings, company facts, watchlist flags, market/salary figures, scholar attributions, statistics — carries a verifiable reference: a URL, an API-verified citation from the ledger, or a named document with date. A claim that cannot be sourced is either omitted or explicitly labeled `[analysis — no source]`. Applies equally to Stage 1 and Stage 2. The user must be able to check everything themselves.

## Data Locations

- **User data** (profile, evaluations, tracker): `F:/HalalOps/` if it exists, else create `./halal-ops/` in the working directory with `config/profile.yml`, `evaluations/`, `tracker.md`.
- **Skill knowledge** (read-only): this folder's `references/`.
- Richer data (full rulings, live watchlists, company dossiers) lives in the user's HalalOps repo when present — prefer it over bundled snapshots.

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

Follow `references/career-fit.md`: A) Role summary, B) CV match table, C) Level strategy, D) Comp & demand, E) Personalization plan, F) STAR+R interview prep, G) Posting legitimacy → Score /5 with stated deductions.

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
