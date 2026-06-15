# HalalOps — Evaluation Mode

## Purpose

Evaluate a job opportunity from an Islamic perspective. Produces a structured report covering:
- Company's core business halal/haram status
- Your specific role's permissibility
- Oppression/complicity check across all active watchlists
- Full scholarly opinions with citations
- A clear verdict with reasoning

---

## How to Use

Paste a job description and say: **"evaluate this"** or **"is this halal?"**

You can also provide just a company name for a company-only check.

---

## Evaluation Pipeline

### Step 1 — Parse the JD

Extract:
- Company name
- Role title
- Core responsibilities (what you would actually build/do)
- Company description (what they do, revenue model)
- Location
- Any red flags visible in the JD itself

### Step 2 — Research the Company

1. Check `knowledge/companies/{company-slug}.md` — if a dossier exists, load it (do not re-research from scratch)
2. If no dossier: use WebSearch to research:
   - Primary business model and revenue sources
   - Key clients and industries served
   - Any known haram elements (interest products, alcohol, gambling, weapons)
   - Wikipedia, Crunchbase, company website, LinkedIn
3. Save the research as a new company dossier: `knowledge/companies/{company-slug}.md`

### Step 3 — Oppression Watchlist Check

1. Load `knowledge/oppression-watch/_index.md`
2. Check the quick-reference table against the company name and any parent companies
3. If flagged: load the relevant watchlist file for full detail and confidence level
4. Also perform a targeted WebSearch: "{company name} Israel military" / "{company name} Uyghur" / "{company name} genocide" to catch anything newer than the last watchlist update
5. Record confidence level: High / Medium / Low

### Step 4 — Apply Islamic Rulings

Load the relevant ruling files from `knowledge/rulings/`:
- Does the company's core business involve riba? → `riba-banking.md`
- Insurance? → `insurance.md`
- Defense/weapons? → `defense-weapons.md`
- Alcohol/tobacco? → `alcohol-tobacco.md`
- Gambling? → `gambling.md`
- Your role is in tech for a haram company? → `tech-indirect.md`

For each applicable ruling:
- State the majority scholarly position
- State the cautious position
- State any dissenting/lenient positions (with scholar names)
- Cite specific fatwas where available (islamqa.info links preferred)

### Step 5 — Personal Red Lines Check

Load `config/profile.yml → personal_red_lines`
Check each red line against the role:
- If ANY red line is triggered: verdict is ❌ HARAM regardless of other factors

### Step 6 — Synthesize Verdict

Apply `mashbooh_tolerance: strict` from profile.yml:
- If any element is haram: ❌ HARAM
- If all clear but scholar disagreement exists: 🟠 MUKHTALAF (present all opinions)
- If genuinely doubtful: 🟡 MASHBOOH
- If no concerns: ✅ HALAL

### Step 7 — Write Report

Save to: `evaluations/{company-slug}-{role-slug}-{YYYY-MM-DD}.md`

### Step 8 — Update Tracker

Add one row to `tracker.md`

---

## Report Template

```markdown
# Halal Evaluation: {Company} — {Role}

**Date:** {YYYY-MM-DD}
**Verdict:** {✅ HALAL | 🟡 MASHBOOH | 🟠 MUKHTALAF | ❌ HARAM}
**Confidence:** {High | Medium | Low}

---

## 1. Company Overview

{What the company does, primary revenue model, key clients, size}

## 2. Core Business Ruling

**Industry:** {e.g., Conventional banking / SaaS / Defense / Halal food}
**Ruling:** {Halal / Haram / Mashbooh}

### Scholarly Positions
{Present majority, cautious, and dissenting positions with scholar names and citations}

## 3. Your Specific Role

**What you would build/do:** {Extracted from JD}
**Connection to haram elements:** {Direct / Indirect / None}
**Ruling on your role:** {Apply tech-indirect.md if relevant}

## 4. Oppression Watchlist Check

| Watchlist | Status | Confidence | Evidence |
|-----------|--------|------------|----------|
| Palestine | {Flagged/Clear} | {H/M/L} | {Source} |
| Uyghurs | {Flagged/Clear} | {H/M/L} | {Source} |
| Kashmir | {Flagged/Clear} | {H/M/L} | {Source} |
| Rohingya | {Flagged/Clear} | {H/M/L} | {Source} |

## 5. Personal Red Lines

{List each red line and whether it is triggered}

## 6. Final Verdict

**Verdict: {SYMBOL} {VERDICT}**

**Reasoning:** {2-3 sentences explaining the verdict}

**If MASHBOOH or MUKHTALAF:** {Specific advice — which scholars permit, which prohibit, recommendation for istikharah}

**If HARAM:** {Primary prohibition and which red line or ruling was triggered}

---

## References

{List all fatwas, scholar opinions, hadith cited}

---

## Annotations

{Leave blank — update after you take or decline the job with what you learned}
```

---

## Learning System

The system improves with every evaluation:

1. **Company dossiers** (`knowledge/companies/`) persist — each new job at the same company starts from existing research
2. **Annotations** in evaluation files are read by future evaluations of the same company
3. **Watchlist updates** happen automatically every 2 days via scheduled cloud agent
4. **Rulings files** can be updated when new fatwas are issued — future evaluations automatically benefit

---

## Istikharah Reminder

When the verdict is 🟡 MASHBOOH or 🟠 MUKHTALAF, the system will always remind:

> "When in doubt, perform Salat al-Istikharah (the prayer of seeking guidance from Allah). Ask Allah ﷻ to guide you toward what is good for your deen and dunya, and away from what is harmful. The Prophet ﷺ used to teach us Istikharah in all matters as he used to teach us a surah from the Quran." — Sahih Bukhari 1166
