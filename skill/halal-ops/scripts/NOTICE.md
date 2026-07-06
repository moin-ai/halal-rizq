# Vendored Tooling — Attribution

The `.mjs` scripts in this folder and the CV templates/fonts in `../assets/` are from **career-ops** by Santiago Fernández de Valderrama (https://github.com/santifer/career-ops), MIT License — see `LICENSE` in this folder. Vendored unmodified into the halal-ops skill as optional zero-token accelerators.

| Script | Purpose |
|--------|---------|
| scan.mjs | Zero-token portal scanner (Greenhouse/Ashby/Lever APIs) — needs `portals.yml` |
| generate-pdf.mjs | HTML → ATS-normalized PDF (Playwright) |
| generate-latex.mjs | LaTeX CV validator + compiler |
| check-liveness.mjs / liveness-core.mjs | Posting liveness checker |
| followup-cadence.mjs | Follow-up due-date calculator (JSON) |
| analyze-patterns.mjs | Outcome pattern analysis (JSON) |
| merge-tracker.mjs / dedup-tracker.mjs / normalize-statuses.mjs / verify-pipeline.mjs | Tracker hygiene |
| cv-sync-check.mjs / doctor.mjs | Setup + consistency checks |
| update-system.mjs / test-all.mjs / gemini-eval.mjs | System maintenance (repo-oriented) |

**Requirements:** Node.js ≥18; run `npm install` against the vendored `package.json` from the user's project root. Scripts expect the project layout the skill's onboarding creates (`config/profile.yml`, `data/`, `reports/`, `portals.yml`, `templates/`). Everything in this skill also works without Node — the instruction-driven flows in `../references/` cover the same capabilities.
