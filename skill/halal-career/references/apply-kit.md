# Application Kit — Documents & Form Answers

Triggered when the user says "generate the CV/cover letter", "help me apply", shares application form questions, or confirms they're applying.

## Ethics (non-negotiable)
- Draft everything; **submit nothing**. The user reviews and sends. Never present a draft as sent.
- Never invent experience, metrics, tools, or dates. Reformulation is rewording real experience in the JD's vocabulary — if the JD says "stakeholder management" and the CV shows client discovery workshops, that's legitimate; adding a skill the CV can't support is not.
- Truthfulness is also a deen matter: the Prophet ﷺ said the truthful merchant is with the martyrs — deception has no place in a halal rizq search (see duas.md; principle: Quran 2:172 chain).

## Tailored CV
1. Read the Stage 2 Personalization Plan (section E) — it is the spec.
2. Extract 15–20 JD keywords; inject them **only** where the CV genuinely supports them: summary (top 5), first bullet of each role, skills section.
3. ATS rules: single column, standard section headers (Professional Summary / Work Experience / Education / Skills / Certifications / Projects), no text in images, selectable text, no critical info in header/footer, ASCII punctuation (no smart quotes/em-dashes).
4. Order for the 6-second scan: header+links → keyword-dense summary (3–4 lines) → competency tags (6–8) → experience (relevance-ordered bullets) → projects (top 3) → education/certs → skills.
5. Output: if the user has an existing template/pipeline (e.g. an HTML template + PDF script), use theirs; else produce clean markdown or self-contained HTML for print-to-PDF. Save under a per-company folder in user data: `{data}/output/{Company}/`.

## Cover Letter
- 1 page, 3–4 paragraphs: (1) a specific hook proving you understand what the role actually is, (2) proof — 2–3 quantified results mapped to JD requirements, (3) the gap addressed honestly if one exists, (4) direct close. Same visual family as the CV.
- Mirror the JD's exact vocabulary. Reference something real and specific about the company (from the Stage 1 dossier).
- **Banned phrases:** passionate about, results-oriented, proven track record, leveraged, spearheaded, synergies, robust, seamless, cutting-edge, innovative, fast-paced world, demonstrated ability to, best practices (name the practice instead). Prefer "built/ran/cut" over "developed/led/reduced". Vary sentence length and bullet openers.

## Writing Voice
If `{data}/writing-samples/` exists: on first use, extract the user's style (tone, sentence length, punctuation habits, vocabulary preferences, voice patterns) into `profile.yml → writing_style` and reuse it thereafter — regenerate only when samples change. Store abstract descriptors only, never verbatim sentences. No samples → default: short sentences, active voice, concrete verbs, zero corporate-speak.

## Screening & Form Questions
When the user shares application form questions (text or screenshot):
1. Load the evaluation report for this company (context + proof points).
2. Answer each question type:
   - **Expected salary** → the recommended ask from section D (sourced) — never volunteer the floor.
   - **Notice period / availability / work authorization** → from `profile.yml`; flag visa needs honestly, framed factually.
   - **Self-ratings** ("rate your Excel 1–10") → honest number backed by one line of evidence; recommend the defensible-high end, never inflation.
   - **"Why us" / free text** → cover-letter rules, 3–5 sentences, one specific company fact + one proof point.
3. Present answers formatted for copy-paste, one block per question.
4. If the on-screen role differs from the evaluated one → say so, offer re-evaluation before answering.

## After Submission
User confirms sent → update tracker status to `Applied` (+date). Suggest outreach (`outreach-followup.md`) and record the first follow-up date (+7 days).
