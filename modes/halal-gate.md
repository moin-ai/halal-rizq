# Mode: halal-gate — Islamic Permissibility Gate (MANDATORY pre-stage)

Runs BEFORE blocks A–F of every evaluation (oferta, auto-pipeline, batch, pipeline). A role gated ❌ HARAM gets no A–F evaluation, no PDF, no outreach — it is registered and closed.

Full protocol lives in the skill: `skill/halal-career/SKILL.md` + `skill/halal-career/references/`. This file is the mode-level wiring.

## Pipeline

1. **Madhab** — `config/profile.yml → fiqh.madhab`. If `prompt_user`, ask once (Hanafi/Shafi'i/Maliki/Hanbali/all), save. Present the user's madhab position first in all rulings, then other schools.
2. **Company research** — `skill/halal-career/references/company-research.md` (tiered: identity/ownership → revenue from filings → halal screeners → gov/defense contracts → ethics databases → ground truth). Cache dossier at `knowledge/companies/{slug}.md`; reuse if fresh (<6 months).
3. **Oppression watchlists** — `knowledge/oppression-watch/_index.md` (auto-updated every 2 days) + fresh WebSearch (`{company} Israel military | Uyghur | Myanmar`). Check the parent company too.
4. **Rulings** — match industry to `skill/halal-career/references/rulings.md` (riba, insurance, defense, alcohol/tobacco, gambling, indirect-tech). Citations ONLY from `skill/halal-career/references/citations.md` (verified ledger) or live-verified per `verification.md`. Dual numbering for Sahih Muslim. Named graders always.
5. **Personal red lines** — `config/profile.yml → fiqh.personal_red_lines`. Any hit → HARAM.
6. **Verdict** — ✅ HALAL | 🟡 MASHBOOH | 🟠 MUKHTALAF | ❌ HARAM (synthesis table in `rulings.md`). For 🟡/🟠: present who permits vs. prohibits + Istikharah reminder (Bukhari 1166).

## Report integration

- Report header gains: `**Halal:** {✅|🟡|🟠|❌} ({one-line reason})` — placed directly under **Score:**.
- Stage 1 findings go in a `## Halal Gate` section at the TOP of the report, before Block A.
- ❌ HARAM → report contains Halal Gate section only; Score field reads `N/A — haram`; tracker status `SKIP`; notes prefixed `HARAM:`. STOP — no blocks A–F, no PDF.
- Every report ends with one contextual dua from `skill/halal-career/references/duas.md` (Arabic + transliteration + translation + verified source), followed by the Mandatory Disclaimer block from `skill/halal-career/SKILL.md` § Mandatory Disclaimer — dua first, disclaimer last, never omitted.

## Tracker integration (no schema change — scripts keep working)

The 9-column TSV format is untouched. The halal verdict travels in:
- `notes` column: prefix `✅ HALAL |`, `🟡 MASHBOOH |`, `🟠 MUKHTALAF |`, or `HARAM:`
- report header (source of truth)

## Sourcing rule (global, from the skill)

No unsourced claims anywhere — scripture from the verified ledger, company facts with links + confidence (H/M/L), salary data with links + retrieval date, else labeled `[analysis — no source]` or omitted.
