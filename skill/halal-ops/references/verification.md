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

## Verification steps for a new citation

1. Quran: fetch translation + confirm content matches the claim. 2 calls max.
2. Hadith: fetch from CDN; confirm text anchor matches claim; record grades verbatim with scholar names; note numbering scheme.
3. Mismatch found → numbering-mismatch protocol in `citations.md`.
4. Append verified entry to the ledger (both numbers, grade, anchor, date).
5. Windows note: pipe curl to `PYTHONIOENCODING=utf-8 python` for Arabic-safe output.
