# HalalOps

> **Evaluate job opportunities through an Islamic lens — before you evaluate them through a career lens.**

A personal career evaluation system for Muslim professionals. Every job is screened for Islamic permissibility first. If it passes, a full career fit analysis (CV match, level strategy, compensation, interview prep) follows automatically.

---

## Why This Exists

Most career tools help you find the best job. This one helps you find the best *halal* job.

The Prophet ﷺ said:
> *"The halal is clear and the haram is clear, and between them are matters that are doubtful (mashbooh). Whoever avoids the doubtful matters has protected his religious commitment and his honour. Whoever falls into doubtful matters will fall into haram."*
> — Sahih Bukhari 52; Sahih Muslim 1599

Before asking "does this role match my skills?", a Muslim professional must ask:
- Is this company's business permissible?
- Would my work contribute to something haram?
- Is this company complicit in the oppression of Muslims anywhere in the world?

HalalOps answers those questions first — with Quranic ayaat, hadith references, and rulings prioritised by your madhab — then proceeds to the career evaluation only if the role passes.

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

### 4. Pull watchlist updates (every 2 days)

A scheduled cloud agent updates the oppression watchlists automatically. To get the latest:

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

#### Riba / Conventional Banking
**File:** `knowledge/rulings/riba-banking.md`

> *"Allah has permitted trade and forbidden riba."*
> — Quran 2:275

> *"O you who believe! Fear Allah and give up what remains of your demand for riba, if you are indeed believers. If you do not, then take notice of war from Allah and His Messenger."*
> — Quran 2:278–279

> *"The Messenger of Allah ﷺ cursed the one who consumes riba, the one who pays it, the one who records it, and the two witnesses to it — and he said: they are all equal."*
> — Sahih Muslim 1598; Sunan Abu Dawud 3333; Jami' at-Tirmidhi 1206; Ibn Majah 2277

**Implication:** Working at a conventional bank is haram under the majority and cautious scholarly positions, as even administrative roles sustain the riba institution and salary derives from haram income.

---

#### Conventional Insurance
**File:** `knowledge/rulings/insurance.md`

> *"O you who believe! Do not consume one another's wealth unjustly, but only through trade by mutual consent."*
> — Quran 4:29

> *"The Messenger of Allah ﷺ forbade transactions determined by throwing stones (gharar), and he forbade gharar transactions."*
> — Sahih Muslim 1513 (prohibition of gharar — excessive uncertainty)

**Resolution:** Islamic Fiqh Academy (OIC) Resolution 9/2 (Second Session, 1985) — conventional insurance is haram due to gharar, maysir, and riba; takaful is the permissible alternative.

---

#### Defense / Weapons Manufacturing
**File:** `knowledge/rulings/defense-weapons.md`

> *"Help one another in righteousness and piety, but do not help one another in sin and aggression (ithm and udwan). Fear Allah; indeed, Allah is severe in penalty."*
> — Quran 5:2

> *"And what is wrong with you that you fight not in the cause of Allah and for the oppressed — men, women, and children — who say, 'Our Lord, take us out of this city of oppressive people and appoint for us from Yourself a protector and appoint for us from Yourself a helper?'"*
> — Quran 4:75

**Implication:** Supplying weapons or enabling technology to forces actively killing civilians or oppressing Muslims is haram. Quran 5:2 is the primary basis — direct or indirect assistance in udwan (transgression/aggression) is prohibited.

---

#### Alcohol / Tobacco
**File:** `knowledge/rulings/alcohol-tobacco.md`

> *"O you who believe! Intoxicants, gambling, sacrificing on stone altars, and divining arrows are but defilement from the work of Satan, so avoid it that you may be successful."*
> — Quran 5:90

> *"The Messenger of Allah ﷺ cursed ten people with regard to khamr: the one who squeezes [the grapes etc.], the one for whom it is squeezed, the one who drinks it, the one who carries it, the one it is carried to, the one who pours it, the one who sells it and consumes its price, the one who buys it and the one it is bought for."*
> — Sunan Ibn Majah 3381; Jami' at-Tirmidhi 1295; Sunan Abu Dawud 3674

**Implication:** The hadith explicitly covers the entire supply chain including those who transport, trade, and profit from it. Working in any capacity for an alcohol company — including building its software — falls under this curse.

---

#### Gambling / Speculative Platforms
**File:** `knowledge/rulings/gambling.md`

> *"O you who believe! Intoxicants and gambling (maysir), stone altars and divining arrows are but defilement from the work of Satan, so avoid it that you may be successful. Satan only wants to cause between you animosity and hatred through intoxicants and gambling and to avert you from the remembrance of Allah and from prayer. So will you not desist?"*
> — Quran 5:90–91

> *"They ask you about wine and gambling. Say: 'In them is great sin and [yet, some] benefit for people. But their sin is greater than their benefit.'"*
> — Quran 2:219

**Implication:** Maysir (gambling) is prohibited in the same ayah as alcohol, with the same severity. Building casino games, betting platforms, or lottery systems is haram — regardless of whether you personally gamble.

---

#### Tech / IT Work for a Haram Company
**File:** `knowledge/rulings/tech-indirect.md`

> *"Help one another in righteousness and piety, but do not help one another in sin and aggression."*
> — Quran 5:2

> *"The Messenger of Allah ﷺ cursed the one who consumes riba, the one who pays it, the one who **records** it, and the two who **witness** it."*
> — Sahih Muslim 1598

**Note:** The hadith on riba explicitly curses the *writer* and *witness* — those with indirect roles. The majority of scholars extend this principle to all who sustain a haram institution, even in unrelated departments. The minority (Al-Qaradawi) permits it under strict conditions of necessity (darurah).

---

### Oppression Watchlists

The Quran commands concern for oppressed Muslims everywhere:

> *"And what is wrong with you that you fight not in the cause of Allah and for the oppressed — men, women, and children."*
> — Quran 4:75

> *"The believers, in their mutual mercy, love, and compassion, are like one body: if one limb suffers, the rest of the body responds with sleeplessness and fever."*
> — Sahih Bukhari 6011; Sahih Muslim 2586

| Watchlist | Covers | Key Sources |
|-----------|--------|-------------|
| 🇵🇸 **Palestine** | Gaza genocide (ICJ provisional measures Jan 2024); IDF weapons suppliers; tech military contracts | BDS Movement, Amnesty International, Who Profits (whoprofits.org), The Intercept |
| 🕌 **Uyghurs** | Xinjiang detention camps (1M+ Muslims); forced labor supply chains; surveillance infrastructure | ASPI Uyghur Forced Labor Tracker, US BIS Entity List, Human Rights Watch |
| 🏔️ **Kashmir** | Indian military occupation; internet shutdowns; surveillance tools used on civilians | Amnesty International, Citizen Lab, OHCHR |
| 🛶 **Rohingya** | Myanmar military genocide (UN Fact-Finding Mission 2018); corporate funding of Tatmadaw | UN Fact-Finding Mission Report A/HRC/39/64, Justice for Myanmar, HRW |

Each company entry includes: confidence level (High / Medium / Low), evidence source, and date added. Watchlists update automatically every 2 days.

---

## Trusted Scholars Referenced

| Scholar | Madhab | Key Works / Positions |
|---------|--------|-----------------------|
| Sheikh Ibn Uthaymeen رحمه الله | Hanbali | *Majmoo' Fataawa* (37 vols.); strict evidence-based rulings on contemporary finance |
| Sheikh Ibn Baz رحمه الله | Hanbali | *Majmoo' Fataawa Ibn Baz* (30 vols.); former Grand Mufti of Saudi Arabia |
| Mufti Taqi Usmani | Hanafi | *An Introduction to Islamic Finance*; *Fiqh al-Buyu'*; AAOIFI Shari'ah Board chairman |
| Dr. Yusuf Al-Qaradawi رحمه الله | Comparative fiqh | *The Lawful and the Prohibited in Islam*; *Fiqh al-Zakat*; contemporary necessity rulings |
| Sheikh Muhammad Al-Munajjid | Hanbali-leaning | IslamQA.info — largest searchable English fatwa database |
| Darul Uloom Deoband | Hanafi | Founded 1867; primary Hanafi authority for South/Southeast Asian Muslims |

**Fatwa bodies consulted:**
- Islamic Fiqh Academy — OIC (*Majma' al-Fiqh al-Islami*)
- AAOIFI (Accounting and Auditing Organization for Islamic Financial Institutions)
- European Council for Fatwa and Research (ECFR)

**Primary online sources:** [islamqa.info/en](https://islamqa.info/en) · [islamqa.org](https://islamqa.org/)

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
| **Company knowledge** | After researching a company once, the dossier is saved to `knowledge/companies/`. Future evaluations start from existing research — never re-researched from scratch. |
| **Your annotations** | Each evaluation report has an `## Annotations` section. Update it after you accept or decline a job — future evaluations of the same company read these notes. |
| **Watchlists** | Auto-updated every 2 days by a scheduled cloud agent. Run `git pull` to sync locally. |
| **Rulings** | If a new fatwa is issued, update the relevant file in `knowledge/rulings/`. All future evaluations benefit immediately. |

---

## Personalisation

Edit `config/profile.yml` to change:

```yaml
fiqh:
  madhab: "hanafi"             # Your madhab — set once after first prompt
  mashbooh_tolerance: "strict" # strict = treat doubtful as haram
  personal_red_lines:
    - "Any work contributing to weapons against civilians"
    - "Any riba product role"
    # Add your own absolute prohibitions here
```

---

## Istikharah

When the verdict is 🟡 MASHBOOH or 🟠 MUKHTALAF, the evaluation will always remind you:

> *"Jabir ibn Abdullah رضي الله عنه said: The Prophet ﷺ used to teach us Istikharah in all matters as he used to teach us a surah from the Quran. He ﷺ would say: 'When one of you is concerned about a matter, let him pray two rak'ahs of non-obligatory prayer, then say: O Allah, I seek Your guidance by Your knowledge, and I seek Your power by Your ability, and I ask of You from Your great bounty...'"*
> — Sahih Bukhari 1166

No tool can replace tawakkul. HalalOps provides information and scholarly guidance. The final decision, and complete reliance, is with Allah ﷻ alone.

---

## On Halal Rizq

The Prophet ﷺ said:
> *"O people! Allah is pure (tayyib) and He only accepts that which is pure (tayyib). Allah commanded the believers with what He commanded the Messengers, saying: 'O Messengers, eat of the good things (tayyibaat) and do righteous deeds.' And He said: 'O you who believe, eat of the good things We have provided for you.'"*
> — Sahih Muslim 1015; referencing Quran 23:51 and Quran 2:172

> *"A man grows dishevelled and dusty from long journeys, raising his hands to the sky: 'O Lord! O Lord!' — while his food is haram, his drink is haram, his clothing is haram, and he has been nourished with haram. How then can his du'a be answered?"*
> — Sahih Muslim 1015

---

## Disclaimer

This system presents scholarly opinions and fatwa sources as reference material. It is not itself a fatwa. When in doubt about a specific situation, consult a qualified scholar directly.

---

*Built for a Muslim professional who wants his rizq to be halal — in this dunya and the next.*

> *"O you who believe! Eat of the good things which We have provided for you and be grateful to Allah if it is Him that you worship."*
> — Quran 2:172
