# Stage 2 — Career Fit Framework

Runs only when Stage 1 verdict ≠ HARAM. Candidate data: `config/profile.yml` → `cv_path`/`cv_data` (or ask for CV if absent). Never invent experience, metrics, or skills — every match claim cites the CV line it comes from.

## A) Role Summary
Table: Archetype (vs. candidate's primary/secondary) · Domain · Seniority · Location/model · one-line TL;DR of what the role actually buys.

## B) CV Match & Strategy
Table per key JD requirement: | JD Requirement | CV Evidence (cite the CV line) | ✅ Strong / ⚠️ Partial / ❌ Gap |.
After the table: hard blockers vs. bridgeable gaps (and the bridge), the seniority gate and how to clear it, and the one narrative anchor for this application.

## D) Comp & Demand
Market range vs. candidate target vs. likely offer — then **recommend a specific ask**, not just a range (anchor in the upper half the candidate can defend; note the walk-away floor).
**Sourcing required:** salary figures from WebSearch of salary sites for that market (Glassdoor, Payscale, levels.fyi, JobStreet for SEA, StepStone for DE) — cite link + retrieval date. No data → label `[estimate — no market data found]`.

## E) Personalization Plan
Numbered table: Section → Change → Why (mirror JD vocabulary; reorder bullets; surface matching skills). This plan feeds `apply-kit.md` when the user asks for documents.

## F) Interview Prep — STAR+R
Top 4–5 JD requirements → | Requirement | Story | Result (quantified) | Reflection |. Then anticipated hard questions with honest model answers — address gaps directly, never fabricate. Append new stories to the story bank (`{data}/interview/story-bank.md`) so they accumulate across applications. Full interview intel: `interview-prep.md`.

## G) Posting Legitimacy
| Signal | Finding | Weight |: posting age (<30d good, >60d concerning), apply flow active, JD specificity, requirements realism, recent layoff news, reposting pattern, salary transparency. Assessment: High / Caution / Suspicious.
Frame as prioritization signals, never accusations — note innocent explanations for concerning signals.

## Score (/5)
Primary: CV match strength. Deductions (state each): −0.5 unconfirmed visa sponsorship · −0.3 significant domain gap · −0.5 seniority mismatch · −0.3 comp below candidate floor.
4.5–5 Strong Apply · 3.5–4.4 Apply · 2.5–3.4 Borderline · <2.5 Skip — recommend against applying below 3.5 unless the user has a stated reason; their time and the recruiter's attention both matter.

## Tracker

Canonical statuses only: `Evaluated → Applied → Responded → Interview → Offer` | `Rejected` | `Discarded` | `SKIP`. One row per company+role — update the existing row on status change, never duplicate.

**Pattern learning:** once ≥10 rows have decided outcomes (beyond Evaluated), offer analysis on request: conversion by archetype, score-vs-outcome (empirical score floor), recurring blockers (visa, domain, seniority), halal-verdict distribution. Recommend targeting changes from the data; update `profile.yml` if the user agrees.

## Report Template

```markdown
# Evaluation: {Company} — {Role}
**Date:** {date} · **Halal Verdict:** {✅|🟡|🟠|❌} · **Career Score:** {X.X/5 | N/A}

## STAGE 1 — HALAL GATE
### 1. Company Overview
### 2. Core Business Ruling
### 3. Your Specific Role
### 4. Oppression Watchlist
### 5. Personal Red Lines
### 6. Halal Verdict
### References

## STAGE 2 — CAREER FIT  (or "Not evaluated — role is haram.")
### A) Role Summary · B) CV Match & Strategy · D) Comp & Demand · E) Personalization Plan · F) Interview Prep · G) Posting Legitimacy

## Final Verdict
Halal: {verdict} · Score: {X.X}/5 · Recommendation: {Strong Apply|Apply|Borderline|Skip|Do Not Apply}

## Dua
{one contextual dua from duas.md}

## Annotations
(update after outcome)
```

Tracker row: `| N | date | company | role | verdict | score | status | [eval](path) | note |`
