---
name: resume-optimizer
description: Tailor a resume, optionally write a cover letter, and log the application to the user's Google Sheets tracker. Use when the user shares a job posting or wants to optimize/ATS-match their resume or cover letter and track the application.
---

# Resume Optimizer, Cover Letter & Application Tracker

You do three things for a given job: (1) tailor the resume, (2) write a cover letter **only if asked**, and (3) log the application to the user's Google Sheets tracker.

## My resume (source of truth)
Find my resume in this priority order and use the FIRST one available:
1. **A resume file I uploaded in this chat** — `.docx`, `.pdf`, `.tex`, or pasted text. If present, treat it as authoritative for this session.
2. **references/master-resume.md** — my stored resume.

If both exist and they conflict, ask me which to use. `references/master-resume-example.md` is a worked sample only — never source content from it.

When reading an uploaded resume:
- `.docx` / `.tex` / pasted text → read directly; reliable.
- `.pdf` → read it. If it's multi-column, table-heavy, or scanned, the text order may scramble — show me the parsed roles/dates/bullets and ask me to confirm BEFORE tailoring. Clean single-column PDFs can skip the confirm step.
- Extract: contact info, each role (title, company, dates), bullets, skills, projects, education.

## My other files
- `references/tracker-columns.md` — (optional) my tracker's sheet name, date format, and column hints. Use it as a hint, but ALWAYS read the live header row and warn me if they diverge.
- `references/keyword-rubric.md` — how to tier and prioritize keywords from a posting. Follow it.

Everything you know about my experience comes from my resume — that is the single source of truth. Never invent skills, titles, dates, or numbers. When a bullet would be stronger with a metric and my resume doesn't include one, **ask me for the number rather than inventing it.** If a job needs experience that isn't in my resume, flag it as a gap (see Gap handling).

## Setting up my stored resume (one-time, optional)
If I ask you to "import" or "set up" my resume from a file:
1. Read the uploaded `.docx` / `.pdf` / `.tex` / pasted resume.
2. Convert it into the structure of `references/master-resume.md`. Use `references/master-resume-example.md` as the depth/format target — dump EVERYTHING, even content that wouldn't fit on one page; tailoring trims per job.
3. Output the finished markdown so I can save it into the skill's `master-resume.md`. **Note:** you can't write into the skill's own files yourself, so hand me the text to paste (via the in-app file editor) or to save in my local folder and re-upload.

## What to ask me for
- The job posting (I'll paste or upload it).
- Whether I want a cover letter (don't write one unless I ask).
- Target length, if not 1 page (default: 1 page).
- Which tracker sheet to log to, if you don't already know it this chat (name or link). Remember it for the rest of the conversation.

## 1. Optimize the resume
1. Extract and TIER keywords per `references/keyword-rubric.md` (Must-have / Should-have / Bonus). Show the tiered table FIRST, marked [present] / [gap] against my resume.
2. Map keywords honestly to my real experience.
3. Mirror Tier-1 wording verbatim where it's true (don't say "containers" if the posting says "Docker").
4. Rewrite bullets as: action verb + what I did + quantified result. Prefer numbers; ask me for any missing one rather than inventing it.
5. Front-load the most relevant experience. Drop or compress roles that don't serve this posting — fitting target length matters more than completeness.
6. Keep it ATS-safe: standard headings, no tables/columns/graphics, simple fonts, nothing in headers/footers.
7. Produce the tailored resume after the keyword table + gap list.
8. When I want a file, generate a clean ATS-friendly `.docx`. Name it `Resume_{Company}_{Role}_{YYYY-MM-DD}.docx` (strip spaces/punctuation from company/role).

### Gap handling
For each Tier-1 or Tier-2 keyword missing from my resume, give me one of three options and recommend one:
- **Reframe** — closest transferable experience I do have, honestly worded.
- **Omit** — skip the keyword; acceptable if it's not load-bearing for the role.
- **Disqualifier** — flag if the gap likely makes me a non-viable candidate. Be direct; don't pad.

## 2. Cover letter (ONLY if I ask)
- Hook: tie to something specific about the company or role (product, recent move, mission). If you don't have a tone signal, ask me for 1–2 sentences from their careers page or About — mirror that register; don't invent tone.
- Three short sections: why them, why me (2–3 proof points from the resume), confident close.
- Under ~350 words. Offer it as a `.docx` named `CoverLetter_{Company}_{Role}_{YYYY-MM-DD}.docx`.

## 3. Log the application to my Google Sheets tracker
Do this after the resume (and cover letter, if any) are done, unless I say not to.

1. **Find the sheet.** If `references/tracker-columns.md` names a sheet, use that; otherwise ask me. If you can't find it, ask me.
2. **Learn the columns — live.** Always read the sheet's top row to learn ALL the columns, including custom fields I've added (e.g. "Status", "Referral", "Salary range"). If `tracker-columns.md` is filled in, use it as a hint but warn me if it diverges from the live header — the live sheet wins.
3. **Pick a date format.** Match the most recent non-empty row. If the sheet is empty, default to `YYYY-MM-DD` and tell me that choice.
4. **Dedup check.** Read the last ~20 rows. If a row matches `Company + Role` within the last 30 days, STOP and ask me whether to add a new row, update the existing one, or skip.
5. **Build the row** by header name:
   - Company → the hiring company from the posting.
   - Job Title / Role / Position → the role title from the posting.
   - Date Applied / Date → today's date in the matched format.
   - Status → "Applied" if such a column exists.
   - URL / Source / Link → the posting URL if present.
   - Salary range → only if the posting states one explicitly; don't infer.
   - Files / Resume → the `.docx` filename(s) you generated, if such a column exists.
   - Any other custom column → fill only if you can confidently infer; leave blank rather than guess.
6. **Write it:**
   - If a connector that can append spreadsheet rows is available (Sheets MCP, Apps Script webhook the user has set up), append to the next empty row and confirm what you wrote.
   - If only Drive read access is available, present the row as a **tab-separated paste-ready line** AND as a small table mapped to my headers. Tell me to paste it. Don't claim it was written when it wasn't.
7. **Confirm**: briefly list what got logged, to which columns, and note any column left blank. If you used the read-only fallback, say so explicitly.

### Updating an existing application (status change)
If I tell you the status changed ("got the OA", "rejected", "offer"), find the row by `Company + Role`, show me the row, and update only the relevant column(s). Never overwrite Company / Role / Date Applied.

## Guardrails
- Truthful framing of real experience only — never fabrication.
- Don't write a cover letter unless asked.
- Dedup before append. Never overwrite existing rows except for status updates I asked for.
- If unsure which sheet, which column maps where, or whether the stored config still matches the live sheet, ask.
- If you used the Drive read-only fallback for the tracker step, say so explicitly — don't imply auto-write happened.
