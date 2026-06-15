# HalalOps

> **Evaluate job opportunities through an Islamic lens — before you evaluate them through a career lens.**

A personal career evaluation system for Muslim professionals. Every job is screened for Islamic permissibility first. If it passes, a full career fit analysis (CV match, level strategy, compensation, interview prep) follows automatically.

---

## Why This Exists

Most career tools help you find the best job. This one helps you find the best *halal* job.

Before asking "does this role match my skills?", a Muslim professional must ask:
- Is this company's business permissible?
- Would my work contribute to something haram?
- Is this company complicit in the oppression of Muslims anywhere in the world?

HalalOps answers those questions first — with scholarly citations, hadith references, and rulings prioritised by your madhab — then proceeds to the career evaluation only if the role passes.

---

## How It Works

```
You paste a job description
        ↓
┌─────────────────────────────┐
│     STAGE 1 — HALAL GATE   │
│  Company business ruling    │
│  Your specific role         │
│  Oppression watchlist check │
│  Personal red lines         │
│  Scholarly opinions         │
└────────────┬────────────────┘
             │
      ❌ HARAM? → Report saved. Stop.
             │
      ✅ / 🟡 / 🟠 → Continue
             ↓
┌─────────────────────────────┐
│   STAGE 2 — CAREER FIT     │
│  A) Role Summary            │
│  B) CV Match                │
│  C) Level & Strategy        │
│  D) Comp & Demand           │
│  E) Personalization Plan    │
│  F) Interview Prep (STAR+R) │
│  G) Posting Legitimacy      │
└────────────┬────────────────┘
             ↓
   Halal Verdict + Career Score
   Saved to evaluations/ + tracker
```

---

## Quick Start

### 1. Open HalalOps in Claude Code

```bash
# In Claude Code, open this folder
cd F:\HalalOps
```

### 2. Set your madhab (first time only)

On your first evaluation, the system will ask which madhab you follow:

```
Which madhab do you follow?
1. Hanafi
2. Shafi'i
3. Maliki
4. Hanbali
5. Present all opinions equally

Your answer is saved to config/profile.yml and never asked again.
```

Your madhab's ruling is always presented first and in full. Other schools are shown as supporting or dissenting opinions.

### 3. Evaluate a job

Paste any job description into Claude Code and say:

```
evaluate this
```

or

```
is this halal?
```

The system will research the company, check all watchlists, apply Islamic rulings, and produce a full report.

### 4. Pull watchlist updates (every 2 days)

A scheduled cloud agent updates the oppression watchlists automatically every 2 days. To get the latest:

```bash
git pull
```

---

## Verdict System

| Verdict | Meaning | What to do |
|---------|---------|------------|
| ✅ **HALAL** | Clear permissibility — no significant Islamic concerns | Proceed with career evaluation |
| 🟡 **MASHBOOH** | Doubtful — scholar disagreement or unclear evidence | Read all opinions; perform Istikharah |
| 🟠 **MUKHTALAF** | Major scholarly dispute — no clean ruling | All opinions presented; you decide with Allah's guidance |
| ❌ **HARAM** | Clear prohibition | Do not apply — reason and citations provided |

### Career Score (Stage 2 only)

| Score | Recommendation |
|-------|----------------|
| 4.5 – 5.0 | Strong Apply |
| 3.5 – 4.4 | Apply |
| 2.5 – 3.4 | Borderline |
| Below 2.5 | Skip |
| N/A | Haram — not evaluated |

---

## What Gets Checked

### Islamic Ruling Categories

| Category | File | Key Evidence |
|----------|------|-------------|
| Riba / Banking | `knowledge/rulings/riba-banking.md` | Quran 2:275-279; Sahih Muslim 1598 |
| Conventional Insurance | `knowledge/rulings/insurance.md` | OIC Fiqh Academy Resolution 9/2 (1985) |
| Defense / Weapons | `knowledge/rulings/defense-weapons.md` | Quran 5:2; contextual analysis |
| Alcohol / Tobacco | `knowledge/rulings/alcohol-tobacco.md` | Quran 5:90; Ibn Majah 3381 |
| Gambling / Speculation | `knowledge/rulings/gambling.md` | Quran 5:90; definition of maysir |
| Tech at haram company | `knowledge/rulings/tech-indirect.md` | Quran 5:2; scholarly dispute on indirect facilitation |

### Oppression Watchlists

| Watchlist | Covers | Sources |
|-----------|--------|---------|
| 🇵🇸 Palestine | Gaza genocide; IDF weapons suppliers; tech contracts | BDS, Amnesty, Who Profits, The Intercept |
| 🕌 Uyghurs | Xinjiang forced labor; surveillance infrastructure | ASPI tracker, BIS Entity List, HRW |
| 🏔️ Kashmir | Indian military occupation; surveillance tools | Amnesty, Citizen Lab |
| 🛶 Rohingya | Myanmar military corporate links | UN Fact-Finding Mission, Justice for Myanmar |

Watchlists update automatically every 2 days via a scheduled cloud agent. Each company entry includes confidence level (High / Medium / Low) and evidence source.

---

## Trusted Scholars Referenced

| Scholar | Madhab | Known For |
|---------|--------|-----------|
| Sheikh Ibn Uthaymeen (رحمه الله) | Hanbali | Strict, evidence-based contemporary rulings |
| Sheikh Ibn Baz (رحمه الله) | Hanbali | Comprehensive fatwas on economic issues |
| Mufti Taqi Usmani | Hanafi | Leading Islamic finance authority |
| Dr. Yusuf Al-Qaradawi (رحمه الله) | Comparative | Contemporary fiqh; necessity-based rulings |
| Sheikh Muhammad Al-Munajjid | Hanbali-leaning | IslamQA — large fatwa database |
| Darul Uloom Deoband | Hanafi | South/Southeast Asian Hanafi authority |

Primary fatwa sources: [islamqa.info](https://islamqa.info/en) · [islamqa.org](https://islamqa.org/)

---

## File Structure

```
HalalOps/
│
├── config/
│   ├── profile.yml          ← Your madhab, red lines, Islamic preferences
│   └── scholars.md          ← Trusted scholars reference
│
├── knowledge/
│   ├── rulings/             ← Islamic ruling library (one file per category)
│   │   ├── riba-banking.md
│   │   ├── insurance.md
│   │   ├── defense-weapons.md
│   │   ├── alcohol-tobacco.md
│   │   ├── gambling.md
│   │   └── tech-indirect.md
│   │
│   ├── companies/           ← Per-company research (auto-saved, reused)
│   │   └── {company}.md
│   │
│   └── oppression-watch/    ← Living watchlists (auto-updated every 2 days)
│       ├── _index.md        ← Master list + update log
│       ├── palestine.md
│       ├── uyghurs.md
│       ├── kashmir.md
│       └── rohingya.md
│
├── evaluations/             ← One report per job evaluated
│   └── {company}-{role}-{date}.md
│
├── modes/
│   └── evaluate.md          ← The evaluation pipeline (instructions for Claude)
│
└── tracker.md               ← All jobs: verdict, score, status
```

---

## Learning System

HalalOps gets better the more you use it:

| What improves | How |
|---------------|-----|
| **Company knowledge** | After researching a company once, the dossier is saved to `knowledge/companies/`. Future evaluations for the same company start from existing research. |
| **Your annotations** | Each evaluation report has an `## Annotations` section at the bottom. Update it after you accept or decline a job — future evaluations of the same company read these notes. |
| **Watchlists** | Automatically updated every 2 days by a scheduled cloud agent. Run `git pull` to get the latest. |
| **Rulings** | If a new fatwa is issued on a topic, update the relevant file in `knowledge/rulings/`. All future evaluations benefit immediately. |

---

## Personalisation

Edit `config/profile.yml` to change:

```yaml
fiqh:
  madhab: "hanafi"            # Your madhab — set once after first prompt
  mashbooh_tolerance: "strict" # strict = treat doubtful as haram
  personal_red_lines:
    - "Any work contributing to weapons against civilians"
    - "Any riba product role"
    # Add your own absolute prohibitions here
```

---

## Istikharah

When the verdict is 🟡 MASHBOOH or 🟠 MUKHTALAF, the evaluation will always remind you:

> *"When in doubt, perform Salat al-Istikharah — the prayer of seeking guidance from Allah ﷻ. The Prophet ﷺ used to teach us Istikharah in all matters as he used to teach us a surah from the Quran."*
> — Sahih Bukhari 1166

No tool can replace tawakkul. HalalOps provides information and scholarly guidance — the final decision, and reliance, is with Allah ﷻ alone.

---

## Disclaimer

This system presents scholarly opinions and fatwa sources as reference material. It is not itself a fatwa. When in doubt about a specific situation, consult a qualified scholar directly.

---

*Built for a Muslim professional who wants his rizq to be halal — in this dunya and the next.*

> **"O you who believe! Eat of the good things which We have provided for you and be grateful to Allah."** — Quran 2:172
