# Halal-Rizq — Halal Jobs, Verified

**🌍 Read this in:** [🇸🇦 العربية](README.ar.md) · [🇧🇩 বাংলা](README.bn.md) · [🇵🇰 اردو](README.ur.md) · [🇮🇳 हिन्दी](README.hi.md) · [🇮🇩 Bahasa Indonesia](README.id.md) · [🇲🇾 Bahasa Melayu](README.ms.md) · [🇹🇷 Türkçe](README.tr.md) · [🇮🇷 فارسی](README.fa.md) · [🇦🇫 پښتو](README.ps.md) · [🇦🇫 دری](README.prs.md) · [☪️ ئۇيغۇرچە](README.ug.md) · [🇫🇷 Français](README.fr.md) · [🇩🇪 Deutsch](README.de.md) · [🇪🇸 Español](README.es.md) · [🇧🇷 Português](README.pt-BR.md) · [🇷🇺 Русский](README.ru.md) · [🇨🇳 简体中文](README.cn.md) · [🇹🇼 繁體中文](README.zh-TW.md) · [🇯🇵 日本語](README.ja.md) · [🇰🇷 한국어](README.ko-KR.md) · [🇹🇭 ไทย](README.th.md) · [🇻🇳 Tiếng Việt](README.vi.md) — [see all / contribute](#languages)

---

> **Check if a job is halal before you check if it fits your CV.**
> The first job-search system for Muslims that screens every opportunity for Islamic permissibility — the employer's business, your specific role, and their complicity in oppression — with verified Quran, hadith, and fatwa citations. Only then does it run the full career evaluation: CV match, salary analysis, tailored documents, interview prep.

---

## Why This Was Created

A Muslim professional asking "should I take this job?" is really asking two questions, and the more important one comes first:

1. **Is this rizq halal?** — Is the employer's business permissible? Would *my* work feed something haram? Is this company supplying weapons or surveillance used against innocent people — in Gaza, East Turkestan, Kashmir, Arakan, or anywhere?
2. Only then: *does it fit my skills and pay fairly?*

Every job tool on the market answers the second question. None answer the first. Halal stock screeners exist for *investing* (Zoya, Musaffa); boycott apps exist for *shopping* (Boycat); nothing existed for the decision that shapes your entire income stream — **employment**.

The Prophet ﷺ said:

> *"The halal is clear and the haram is clear, and between them are doubtful matters about which many people do not know. Whoever guards against the doubtful matters has protected his religion and his honour."*
> — Sahih Bukhari 52; Sahih Muslim 1599 ([sunnah.com/bukhari:52](https://sunnah.com/bukhari:52))

And he ﷺ warned of the man whose du'a is not answered *"while his food is haram, his drink is haram, his clothing is haram, and he has been nourished with haram"* — Sahih Muslim 1015.

Halal-Rizq exists so that no Muslim has to choose between career tooling and their akhirah.

---

## How It Works

```
Paste a job description (or URL, or just a company name)
        │
        ▼
┌────────────────────────────────────────────┐
│  STAGE 1 — HALAL GATE (mandatory)          │
│  1. Your madhab loaded (asked once)        │
│  2. Company researched — real revenue,     │
│     real owners, from filings not marketing│
│  3. Oppression watchlists checked          │
│     (Palestine · Uyghurs · Kashmir ·       │
│      Rohingya — auto-updated every 2 days) │
│  4. Islamic rulings applied — your madhab  │
│     first, all schools shown, every        │
│     citation verified against source APIs  │
│  5. Your personal red lines checked        │
└──────────────────┬─────────────────────────┘
                   │
        ❌ HARAM → report + reasons + sources. STOP.
                   │
        ✅ 🟡 🟠 → continue
                   ▼
┌────────────────────────────────────────────┐
│  STAGE 2 — CAREER FIT                      │
│  CV match · seniority strategy · salary    │
│  (sourced) · personalization plan ·        │
│  interview stories · posting legitimacy    │
│  → Score /5 + recommendation               │
└──────────────────┬─────────────────────────┘
                   ▼
┌────────────────────────────────────────────┐
│  STAGE 3 — APPLICATION LIFECYCLE           │
│  Tailored ATS CV + cover letter · form &   │
│  screening answers · LinkedIn outreach ·   │
│  follow-up cadence · interview prep incl.  │
│  DEEN READINESS (prayer, Jumu'ah, Ramadan  │
│  accommodations) · tracker · patterns      │
└────────────────────────────────────────────┘

Plus: portal scanning with a haram pre-filter (watchlisted
weapons/surveillance companies never enter your pipeline),
batch evaluation, offer comparison, and a du'a from the
Sunnah at the end of every report.
```

### The integrity rules that govern everything

- **No unsourced claims.** Every verse, hadith, fatwa, company fact, watchlist flag, and salary figure carries a verifiable reference — or is explicitly labeled `[analysis — no source]`.
- **Scripture is never quoted from the model's memory.** Citations come from a pre-verified ledger or are verified live against the source APIs at evaluation time. Sahih Muslim citations carry dual numbering (Abd al-Baqi / CDN). Hadith gradings name the grading scholar (e.g. "Al-Albani: Sahih").
- **The tool reports scholarship; it never issues rulings.** Where scholars differ, all positions are presented — your madhab's first — and you are reminded of Salat al-Istikharah (Sahih Bukhari 1166).

---

## How To Use It

### Option A — The skill (lightest)
1. Copy `skill/halal-rizq/` into your Claude Code skills directory (`~/.claude/skills/halal-rizq/`) or upload it zipped to Claude.ai (Settings → Capabilities → Skills).
2. Paste any job description and say **"is this halal?"** or **"evaluate this job."**
3. First run asks your madhab (Hanafi / Shafi'i / Maliki / Hanbali / present all) — answered once, saved forever.

### Option B — The full system (this repository)
1. Clone the repo, run `npm install`, then `node doctor.mjs` to verify setup.
2. Open the folder in Claude Code — onboarding will set up your CV, profile, and tracker if missing.
3. Everything the skill does, plus zero-token portal scanning (`node scan.mjs`), PDF/LaTeX CV generation, batch evaluation, follow-up cadence tooling, and pattern analysis.

Works in your language — evaluations respond in whatever language you write in, and scripture is served from **verified translations in 44+ languages** (Bengali, Urdu, Malay, Indonesian, Turkish, Arabic, and more — including Uyghur), never machine-translated.

---

## Sources

### Quran & Hadith (verification APIs)
| Source | Used for | Link |
|--------|----------|------|
| Quran.com API | Verse text + verified translations (69 languages) | https://api.quran.com |
| Sunnah.com | Canonical hadith reference links | https://sunnah.com |
| Hadith API (fawazahmed0) | Hadith text + gradings by named scholars, 9 languages | https://github.com/fawazahmed0/hadith-api |
| HadeethEnc | Scholar-committee hadith explanations, 70 languages | https://hadeethenc.com |

### Fatwa & Scholarship
| Source | Link |
|--------|------|
| IslamQA (Sheikh Muhammad Al-Munajjid) | https://islamqa.info/en |
| IslamQA.org | https://islamqa.org |
| Islamic Fiqh Academy (OIC) resolutions | via https://aaoifi.com and academy publications |
| Referenced scholars | Ibn Uthaymeen, Ibn Baz, Mufti Taqi Usmani, Yusuf Al-Qaradawi (رحمهم الله), Darul Uloom Deoband |

### Oppression Watchlists (evidence sources)
| Source | Covers | Link |
|--------|--------|------|
| BDS Movement | Palestine | https://bdsmovement.net |
| Who Profits | Palestine — corporate database | https://www.whoprofits.org |
| AFSC Investigate | Palestine, prisons, borders | https://investigate.afsc.org |
| UN OHCHR settlement business database | Palestine (official UN list) | https://www.ohchr.org |
| ASPI Uyghurs for Sale | Xinjiang forced labor | https://www.aspi.org.au/report/uyghurs-sale |
| Human Rights Watch | All regions | https://www.hrw.org |
| Amnesty International | All regions | https://www.amnesty.org |
| Justice for Myanmar | Rohingya | https://www.justiceformyanmar.org |
| Citizen Lab | Kashmir (spyware) | https://citizenlab.ca |

### Company Research
| Source | Used for | Link |
|--------|----------|------|
| SEC EDGAR | Revenue truth from sworn filings | https://www.sec.gov/edgar |
| GLEIF LEI | Legal entities + ownership chains | https://www.gleif.org |
| USAspending | US government/defense contracts | https://www.usaspending.gov |
| Business & Human Rights Resource Centre | Allegations + company responses | https://www.business-humanrights.org |
| Violation Tracker | US corporate misconduct | https://violationtracker.goodjobsfirst.org |

### Base System
The career-evaluation engine builds on **[career-ops](https://github.com/santifer/career-ops)** by Santiago Fernández de Valderrama (MIT License — retained in `LICENSE` and `skill/halal-rizq/scripts/NOTICE.md`). May Allah reward him for open-sourcing it.

---

## Key Verses & Duas In This System

**Foundations** *(all verified against quran.com / hadith APIs — full ledger: `skill/halal-rizq/references/citations.md`)*

- *"Allah has permitted trade and forbidden riba."* — **Quran 2:275**
- *"Help one another in righteousness and piety, but do not help one another in sin and aggression."* — **Quran 5:2**
- *"O you who believe! Eat of the good things We have provided for you."* — **Quran 2:172**
- The Messenger of Allah ﷺ *"cursed the one who consumes riba, the one who pays it, the one who records it, and the two witnesses to it."* — **Sahih Muslim 1598** (Abd al-Baqi)
- *"The believers, in their mutual love and compassion, are like one body."* — **Sahih Bukhari 6011; Sahih Muslim 2586**

**Duas for the jobseeker** *(Arabic + transliteration + grading in `skill/halal-rizq/references/duas.md`)*

1. **Halal sufficiency:** *Allahumma-kfini bi-halalika 'an haramika…* — "O Allah, suffice me with Your halal against Your haram" — Tirmidhi 3563 (Hasan)
2. **Against worry & debt:** *Allahumma inni a'udhu bika minal-hammi wal-hazan…* — Bukhari 6369
3. **Morning rizq:** *Allahumma inni as'aluka 'ilman nafi'an, wa rizqan tayyiban, wa 'amalan mutaqabbalan* — Ibn Majah 925 (Sahih)
4. **When in need:** *Rabbi inni lima anzalta ilayya min khayrin faqir* — Quran 28:24 (Musa عليه السلام)
5. **Before interviews:** *Rabbi-shrah li sadri…* — Quran 20:25–28
6. **Tawakkul:** *"He will provide from where he does not expect…"* — Quran 65:2–3
7. **When unsure:** Salat al-Istikharah — Bukhari 1166

---

## Disclaimer

Halal-Rizq presents verified scholarship as reference material — **it is not a fatwa, and it is not a mufti.** Rulings differ by situation and madhab; the system shows you the sources and the disagreements, but for your specific circumstance, consult a qualified scholar. Scholar review of the rulings library is planned before wide release.

> *"And do not say about what your tongues assert of untruth, 'This is lawful and this is unlawful,' to invent falsehood about Allah."* — Quran 16:116

---

## Languages

The full README is in **English**; the linked language pages are stubs awaiting community translation. **The tool itself already works in your language** — evaluations respond in whatever language you write in, and scripture is served from verified translations (Quran: 69 languages · hadith explanations: 70 languages via HadeethEnc), never machine-translated. [Full scripture language support →](skill/halal-rizq/references/verification.md#languages)

| Status | Languages |
|--------|-----------|
| ✅ Complete | 🇬🇧 English |
| 🚧 Stub — **help translate!** | العربية (ar) · বাংলা (bn) · اردو (ur) · हिन्दी (hi) · Bahasa Indonesia (id) · Bahasa Melayu (ms) · Türkçe (tr) · فارسی (fa) · پښتو (ps) · دری (prs) · ئۇيغۇرچە (ug) · Français (fr) · Deutsch (de) · Español (es) · Português (pt-BR) · Русский (ru) · 简体中文 (cn) · 繁體中文 (zh-TW) · 日本語 (ja) · 한국어 (ko-KR) · ไทย (th) · Tiếng Việt (vi) |

### How to contribute a translation

1. Copy `README.md` → `README.<code>.md` (codes above; [ISO 639-1](https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes) for new languages).
2. Translate faithfully — preserve every Quran verse and hadith reference **with its exact numbering**, all links, and the Disclaimer. **Never machine-translate scripture**: quote from the verified translations listed in [verification.md](skill/halal-rizq/references/verification.md#languages).
3. Open a pull request; after review we link it in the selector at the top.

---

## Contact

**Arifuzzaman Moin**
📧 arifuzzamanmoin@gmail.com · 💼 [linkedin.com/in/arifuzzaman-moin](https://linkedin.com/in/arifuzzaman-moin)

*Built for every Muslim who wants their rizq halal — in this dunya and the next.*
