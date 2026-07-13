# Halal-Rizq — Full Evaluation Mode

## Purpose

Complete two-stage evaluation of a job opportunity:

**Stage 1 — Halal Gate** (always runs first)
Islamic permissibility check: company business, your specific role, oppression complicity, scholarly rulings.
→ If ❌ HARAM: stop. No career evaluation needed. Save report.
→ If ✅ / 🟡 / 🟠: continue to Stage 2.

**Stage 2 — Career Fit** (only if halal gate passes)
Skills match, level strategy, compensation analysis, interview prep — same rigour as a full career evaluation.

**Final output:** Halal Verdict + Career Score (X.X/5) in one unified report.

---

## How to Use

Paste a job description and say: **"evaluate this"** or **"is this halal?"**

---

## STAGE 1 — HALAL GATE

### Step 0 — Madhab Check (ALWAYS first)

Read `config/profile.yml → fiqh.madhab`.

**If madhab is `"prompt_user"` or `"include_all"`:**
Ask the user before doing anything else:

> "Which madhab do you follow?
> 1. Hanafi
> 2. Shafi'i
> 3. Maliki
> 4. Hanbali
> 5. I follow all / present all opinions
>
> Your choice will be saved for future evaluations and used to prioritise rulings."

Save their answer to `config/profile.yml → fiqh.madhab` before proceeding.

**If madhab is already set (hanafi / shafi / maliki / hanbali):**
Proceed directly — no prompt needed.

**How madhab affects rulings:**
Present the user's madhab's position FIRST and in full. Then present other madhabs' positions as "Other scholarly opinions". When the user's madhab and the majority agree, note that. When they differ, flag it clearly so the user can make an informed decision.

---

### Step 1 — Parse the JD

Extract:
- Company name + any parent company
- Role title
- Core responsibilities (what you would actually build/do day to day)
- Company description (what they do, how they make money)
- Location and work model
- Any red flags visible in the JD itself (financial products, defense clients, etc.)

---

### Step 2 — Research the Company

1. Check `knowledge/companies/{company-slug}.md` — if a dossier exists, load it and skip re-research
2. If no dossier: use WebSearch to research:
   - Primary business model and revenue sources
   - Key clients and industries served
   - Any known haram elements (riba products, alcohol, gambling, weapons, surveillance)
   - Size, ownership, recent news
3. Save research as `knowledge/companies/{company-slug}.md` for future use

---

### Step 3 — Oppression Watchlist Check

1. Load `knowledge/oppression-watch/_index.md` quick-reference table
2. Check company name AND any parent/subsidiary companies against the table
3. If flagged: load the relevant watchlist file for full evidence and confidence level
4. Run targeted WebSearch: `"{company} Israel military contract"` / `"{company} Uyghur forced labor"` / `"{company} Myanmar military"` to catch anything newer than last watchlist update
5. Record: Flagged / Clear + Confidence (High / Medium / Low) + Source

---

### Step 4 — Apply Islamic Rulings

Load the relevant ruling file(s) from `knowledge/rulings/`:

| If the company does this... | Load this file |
|-----------------------------|----------------|
| Interest/lending/banking | `riba-banking.md` |
| Conventional insurance | `insurance.md` |
| Defense/weapons manufacturing | `defense-weapons.md` |
| Alcohol/tobacco | `alcohol-tobacco.md` |
| Gambling/betting/speculative platforms | `gambling.md` |
| Tech/IT role at a haram-industry company | `tech-indirect.md` |

**How to present rulings (madhab-aware):**

```
### [User's Madhab] Position — [RULING]
{Full ruling, reasoning, hadith/Quran reference}
Scholar(s): {names}
Reference: {islamqa.info link or fatwa source}

### Other Scholarly Positions
**[Madhab 2] — [RULING]:** {brief summary}
**[Madhab 3] — [RULING]:** {brief summary}
**Majority position:** {note if user's madhab is majority or minority on this issue}
```

---

### Step 5 — Personal Red Lines Check

Load `config/profile.yml → fiqh.personal_red_lines`
Check each red line against the JD and company research.
If ANY red line is triggered → verdict is ❌ HARAM, regardless of other factors.

---

### Step 6 — Halal Verdict

Apply `mashbooh_tolerance` from `config/profile.yml`:

| Condition | Verdict |
|-----------|---------|
| Personal red line triggered | ❌ HARAM |
| Core business clearly haram (majority + user's madhab agree) | ❌ HARAM |
| Core business haram per user's madhab, but minority permits | ❌ HARAM (note minority opinion) |
| Oppression watchlist: High confidence flag | ❌ HARAM |
| Oppression watchlist: Medium confidence flag | 🟡 MASHBOOH |
| Scholar disagreement with no clear majority | 🟠 MUKHTALAF |
| Doubtful but no clear prohibition | 🟡 MASHBOOH |
| No concerns across all dimensions | ✅ HALAL |

**If ❌ HARAM:** Write the report (Stage 1 sections only), save, update tracker, STOP.
**If ✅ / 🟡 / 🟠:** Note verdict, continue to Stage 2.

---

## STAGE 2 — CAREER FIT (only if halal gate passes)

Read candidate profile from `config/profile.yml → cv_path` and `cv_data`.

---

### A) Role Summary

| Field | Detail |
|-------|--------|
| Archetype | {Primary archetype match: DA / BA / DE / Power Platform / etc.} |
| Domain | {Industry domain} |
| Seniority | {Entry / Mid / Senior} |
| Location | {City, country, remote/hybrid/onsite} |
| TL;DR | {One sentence: what this role actually is and what it buys} |

---

### B) CV Match

For each key JD requirement, map to CV evidence:

| JD Requirement | CV Evidence | Strength |
|----------------|-------------|----------|
| {requirement} | {proof point from CV} | ✅ Strong / ⚠️ Partial / ❌ Gap |

**Gap mitigation:** For each ❌ Gap, explain whether it is a hard blocker or bridgeable.

---

### C) Level & Strategy

- Is the candidate at the right seniority level?
- How to frame experience to clear the hardest gate (years, domain, specific skill)?
- What is the narrative anchor for this application?

---

### D) Comp & Demand

| Scenario | Estimate |
|----------|----------|
| Market range for this role/location | {range} |
| Candidate's target | {from profile.yml} |
| Likely offer | {estimate} |
| Gap / alignment | {note} |

---

### E) Personalization Plan

Specific changes to make to CV/cover letter for this role:

| # | Section | Change | Why |
|---|---------|--------|-----|
| 1 | Summary | {change} | {reason} |
| 2 | {role} bullets | {change} | {reason} |
...

---

### F) Interview Prep — STAR+R

For the top 4-5 JD requirements, map to a STAR+R story from the candidate's experience:

| # | JD Requirement | Story | Result | Reflection |
|---|----------------|-------|--------|------------|
| 1 | {requirement} | {situation/task/action} | {quantified result} | {what you learned} |
...

**Anticipated hard questions + model answers:**
- {Likely objection} → {How to respond}

---

### G) Posting Legitimacy

| Signal | Finding | Weight |
|--------|---------|--------|
| JD quality | {specific/vague/template} | {Positive/Neutral/Negative} |
| Company verifiable | {yes/no} | {Positive/Neutral/Negative} |
| Salary disclosed | {yes/no} | {Positive/Neutral} |
| Visa/sponsorship | {mentioned/not mentioned} | {note} |
| Recent posting | {date if known} | {Positive/Neutral/Negative} |

**Assessment:** {High / Medium / Low} confidence — {1 sentence}

---

### Career Score

Score out of 5.0 based on:
- CV match strength (primary factor)
- Seniority alignment
- Location/visa clarity
- Comp alignment with target
- Posting legitimacy

Deductions: -0.5 for unconfirmed visa sponsorship; -0.3 for significant domain gap; -0.5 for seniority mismatch

**Score: {X.X}/5 — {Apply / Borderline / Skip}**

---

## FULL REPORT TEMPLATE

Save to: `evaluations/{company-slug}-{role-slug}-{YYYY-MM-DD}.md`

```markdown
# Evaluation: {Company} — {Role}

**Date:** {YYYY-MM-DD}
**Halal Verdict:** {✅ HALAL | 🟡 MASHBOOH | 🟠 MUKHTALAF | ❌ HARAM}
**Career Score:** {X.X/5 | N/A — Haram, not evaluated}
**Madhab Applied:** {User's madhab}

---

## STAGE 1 — HALAL GATE

### 1. Company Overview
{Business model, revenue sources, size, key clients}

### 2. Core Business Ruling

**Industry:** {industry}
**Your madhab ({madhab}) position:** {ruling + reasoning + scholar + citation}
**Other scholarly opinions:** {other madhabs briefly}
**Majority position:** {note alignment or divergence with user's madhab}

### 3. Your Specific Role
**What you would do:** {extracted from JD}
**Connection to haram elements:** {Direct / Indirect / None}
**Ruling:** {apply tech-indirect.md logic if relevant, citing user's madhab first}

### 4. Oppression Watchlist

| Watchlist | Status | Confidence | Evidence |
|-----------|--------|------------|----------|
| Palestine | {Flagged/Clear} | {H/M/L} | {source} |
| Uyghurs | {Flagged/Clear} | {H/M/L} | {source} |
| Kashmir | {Flagged/Clear} | {H/M/L} | {source} |
| Rohingya | {Flagged/Clear} | {H/M/L} | {source} |

### 5. Personal Red Lines
{Each red line: triggered ❌ / clear ✅}

### 6. Halal Verdict

**{SYMBOL} {VERDICT}**

{2-3 sentences of reasoning}

{If MASHBOOH/MUKHTALAF: specific scholars who permit vs. prohibit + istikharah reminder}
{If HARAM: which red line or ruling was the primary trigger}

> 🤲 *"When in doubt, perform Salat al-Istikharah. The Prophet ﷺ used to teach us Istikharah in all matters as he used to teach us a surah from the Quran." — Sahih Bukhari 1166*

### References
{All Quran ayaat, hadith, fatwas, and scholar opinions cited — with links where available}

---

## STAGE 2 — CAREER FIT
{Include only if halal verdict is ✅ / 🟡 / 🟠. Otherwise write: "Not evaluated — role is haram."}

### A) Role Summary
{table}

### B) CV Match
{table}

### C) Level & Strategy
{paragraph}

### D) Comp & Demand
{table}

### E) Personalization Plan
{table}

### F) Interview Prep
{STAR+R table + hard questions}

### G) Posting Legitimacy
{table + assessment}

---

## Final Verdict

**Halal: {SYMBOL} {VERDICT}**
**Career Score: {X.X}/5**
**Recommendation:** {Strong Apply / Apply / Borderline / Skip / Haram — Do Not Apply}

---

## Annotations
{Leave blank — update after you take/decline the job}
```

---

## Tracker Update

After every evaluation, add one row to `tracker.md`:

| # | Date | Company | Role | Halal | Score | Applied | Report | Notes |
|---|------|---------|------|-------|-------|---------|--------|-------|
| N | YYYY-MM-DD | Company | Role | ✅/🟡/🟠/❌ | X.X/5 or N/A | ❌ | [link] | one-line summary |

---

## Learning System

1. **Company dossiers** (`knowledge/companies/`) persist — re-used on every future evaluation of the same company
2. **Annotations** section updated after you take/decline — read by future evaluations of the same company
3. **Watchlist updates** run automatically every 2 days via scheduled cloud agent
4. **Madhab saved** to `config/profile.yml` after first prompt — never asked again unless you change it
5. **Rulings files** updated manually when new fatwas issued — all future evaluations benefit automatically
