# Live Citation Verification Protocol

Rule: nothing scriptural reaches the user unverified. Check `citations.md` ledger first (already verified); only run live checks for citations NOT in the ledger, then add them to it.

## Endpoints (all keyless unless noted)

### Quran — api.quran.com
```
# Translation (Saheeh International = resource 20):
GET https://api.quran.com/api/v4/quran/translations/20?verse_key={surah}:{ayah}
# Arabic (Uthmani):
GET https://api.quran.com/api/v4/verses/by_key/{surah}:{ayah}?fields=text_uthmani
```
Note: translation resource IDs vary — 20 (Saheeh Intl), 84 (T. Usmani), 85 (Abdel Haleem). If a resource returns `translations: []`, the ID is wrong; list via `/resources/translations?language=en`.

### Hadith text + grades — fawazahmed0 CDN
```
GET https://cdn.jsdelivr.net/gh/fawazahmed0/hadith-api@1/editions/eng-{collection}/{number}.json
# collections: bukhari, muslim, abudawud, tirmidhi, nasai, ibnmajah, malik
# Arabic: swap eng- for ara-
```
Response: `hadiths[0].text`, `.grades[]` (named scholars), `.arabicnumber`.

**⚠ Sahih Muslim numbering trap:** CDN `hadithnumber` ≠ standard Abd al-Baqi numbering. For Muslim, download the full edition (`editions/eng-muslim.json`) and match on `arabicnumber`. Always cite both numbers. Other collections' CDN numbers match standard (verified: bukhari, tirmidhi, ibnmajah, abudawud).

### Hadith explanation (sharh) — HadeethEnc (scholar-committee)
```
GET https://hadeethenc.com/api/v1/hadeeths/one/?language=en&id={id}
```
Own ID scheme (no collection-number lookup). Use when an explanation is needed and the hadith is findable via their site search; returns grade + attribution + explanation. Languages include en, ar, bn, ms, ur.

### Cross-check (optional 3rd source) — hadithapi.com
```
GET https://hadithapi.com/api/hadiths?apiKey={HADITH_API_KEY}&book={slug}&hadithNumber={n}
# slugs: sahih-bukhari, sahih-muslim, abu-dawood, al-tirmidhi, ibn-e-majah
```
Key from user's `.env` (HADITH_API_KEY). Optional — degrade gracefully if absent.

### Fatwas — islamqa.info / islamqa.org
WebFetch the answer URL; confirm the page's topic matches the claim before quoting. If blocked/unavailable: present as link labeled "reference — verify content", never assert its contents.

### Blocked (do not attempt): sunnah.com (Cloudflare 403 for bots — use only as human-readable links in output), dorar.net (blocked; skip).

## Languages

Verified per-language sources (IDs confirmed live 2026-06-16):

**Quran translations** — same endpoint, swap resource ID (`/quran/translations/{ID}?verse_key=…`). 69 languages exist; IDs below pulled from the live resource list 2026-06-16:

| Language | ID | Translation | | Language | ID | Translation |
|----------|----|--------------|-|----------|----|--------------|
| English | 20 | Saheeh International | | Russian | 78 | Ministry of Awqaf, Egypt |
| Bengali | 213 | Dr. Abu Bakr M. Zakaria | | Chinese | 109 | Muhammad Makin |
| Urdu | 54 | Maulana Junagarhi | | German | 27 | Bubenheim & Nadeem |
| Malay | 39 | Abdullah Basmeih | | Spanish | 83 | Sheikh Isa Garcia |
| Indonesian | 33 | Islamic Affairs Ministry | | Portuguese | 103 | Helmi Nasr |
| Turkish | 77 | Diyanet | | Italian | 153 | Hamza R. Piccardo |
| French | 31 | Muhammad Hamidullah | | Dutch | 144 | Sofian S. Siregar |
| Hindi | 122 | Azizul Haque al-Umari | | Japanese | 218 | Saeed Sato |
| Persian | 135 | IslamHouse.com | | Korean | 219 | Hamed Choi |
| Pashto | 118 | Zakaria Abulsalam | | Thai | 51 | King Fahad Complex |
| Dari | 785 | Mawlawi Badkhashani | | Vietnamese | 220 | Ruwwad Center |
| Uzbek | 55 | M. Sodiq M. Yusuf | | Tagalog | 211 | Dar Al-Salam Center |
| Kazakh | 222 | Khalifa Altay | | Tamil | 229 | Omar Sharif |
| Tajik | 139 | Khawaja Mirof & Mir | | Malayalam | 80 | Karakunnu & Elayavoor |
| Azeri | 75 | Alikhan Musayev | | Telugu | 227 | Abder-Rahim ibn Muhammad |
| Kurdish | 81 | Burhan Muhammad-Amin | | Gujarati | 225 | Rabila Al-Umry |
| **Uyghur** | 76 | Muhammad Saleh | | Marathi | 226 | M. Shafi'i Ansari |
| Bosnian | 214 | Dar Al-Salam Center | | Nepali | 108 | Ahl Al-Hadith Society |
| Albanian | 88 | Hasan Efendi Nahi | | Sinhala | 228 | Ruwwad Center |
| Somali | 46 | Mahmud M. Abduh | | Sindhi | 238 | Taj Mehmood Amroti |
| Hausa | 32 | Abubakar Gumi | | Amharic | 87 | Sadiq and Sani |
| Swahili | 231 | Dr. Abdullah Abu Bakr | | Yoruba | 125 | Shaykh Mikael Aykyuni |

Any other language: fetch `/resources/translations`, filter by `language_name`, prefer official / King-Fahd-complex / Ruwwad / Dar Al-Salam translations.

**Hadith CDN** — swap the `eng-` prefix: `ara-` `ben-` `urd-` `ind-` `tur-` `fra-` `rus-` `tam-` (Bengali 8 collections, Urdu 7, Indonesian 7, Turkish 8, French 9, Russian 3, Tamil 2 — verified). Not every collection exists per language; fall back to English + Arabic.

**HadeethEnc** — `?language=` supports 70 languages (verified list): ar, en, ur, es, id, **ug**, bn, fr, tr, ru, bs, si, hi, zh, fa, vi, tl, ku, ha, pt, ml, te, sw, ta, my (Burmese/Rohingya-relevant), th, de, ja, ps, as, sq, sv, am, nl, gu, ky, ne, yo, prs (Dari), sr, so, tg, ro, hu, cs, it, kn, bg, az, el, uz, uk, km, pa, mr, da, ms, and more — full list at `/api/v1/languages`. This is the deepest multilingual source for hadith explanations.

**Fatwas** — islamqa.info has parallel sections (/ur, /ar, etc.); link the user's language version when it exists.

## Verification steps for a new citation

1. Quran: fetch translation + confirm content matches the claim. 2 calls max.
2. Hadith: fetch from CDN; confirm text anchor matches claim; record grades verbatim with scholar names; note numbering scheme.
3. Mismatch found → numbering-mismatch protocol in `citations.md`.
4. Append verified entry to the ledger (both numbers, grade, anchor, date).
5. Windows note: pipe curl to `PYTHONIOENCODING=utf-8 python` for Arabic-safe output.
