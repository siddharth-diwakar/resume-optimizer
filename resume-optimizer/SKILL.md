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

If both exist and they conflict, ask me which to use.

When reading an uploaded resume:
- `.docx` / `.tex` / pasted text → read directly; reliable.
- `.pdf` → read it, but if it's multi-column, table-heavy, or scanned, the text order may scramble. Show me the parsed roles/dates/bullets and ask me to confirm BEFORE tailoring.
- Extract: contact info, each role (title, company, dates), bullets, skills, education.

## My other files
- references/tracker-columns.md — (optional) my tracker's sheet name, date format, and exact columns. If filled in, use it; if blank/placeholder, read the sheet's header row live.

Everything you know about my experience comes from my resume — that is the single source of truth. Never invent skills, titles, dates, or numbers. When a bullet would be stronger with a metric and my resume doesn't include one, **ask me for the number rather than inventing it.** If a job needs experience that isn't in my resume, flag it as a gap.

## Setting up my stored resume (one-time, optional)
If I ask you to "import" or "set up" my resume from a file:
1. Read the uploaded `.docx` / `.pdf` / `.tex` / pasted resume.
2. Convert it into the structure of references/master-resume.md (sections, roles, bullets).
3. Output the finished markdown so I can save it into the skill's master-resume.md. **Note:** you can't write into the skill's own files yourself, so hand me the text to paste (via the in-app file editor) or to save in my local folder and re-upload.

## What to ask me for
- The job posting (I'll paste or upload it).
- Whether I want a cover letter (don't write one unless I ask).
- Which tracker sheet to log to, if you don't already know it this chat (name or link). Remember it for the rest of the conversation.

## 1. Optimize the resume
1. Pull the top 8–12 keywords/skills from the posting (this is what ATS scans for).
2. Map them honestly to my real experience from my resume.
3. Mirror the posting's exact wording where it's true.
4. Rewrite bullets as: action verb + what I did + quantified result. Prefer numbers.
5. Front-load the most relevant experience.
6. Keep it ATS-safe: standard headings, no tables/columns/graphics, simple fonts, nothing in headers/footers.
7. Show keyword matches and any gaps first, then produce the tailored resume.
8. When I want a file, generate a clean ATS-friendly .docx to download.

## 2. Cover letter (ONLY if I ask)
- Specific hook tied to the company/role, not "I am writing to apply."
- Three short sections: why them, why me (2–3 proof points from the resume), confident close.
- Match the company's tone. Under ~350 words. Offer it as a .docx too.

## 3. Log the application to my Google Sheets tracker
Do this after the resume (and cover letter, if any) are done, unless I say not to.

1. **Find the sheet** using the Google Drive connector. If references/tracker-columns.md names a sheet, use that; otherwise ask me for the name/link. If you can't find it, ask me.
2. **Learn the columns.** If references/tracker-columns.md is filled in, use its column list and date format. Otherwise read the sheet's top row to learn ALL the columns, including any custom fields I've added (e.g. "Status", "Referral", "Salary range"). Either way, adapt to whatever columns actually exist — don't assume a fixed set.
3. **Build the row**, mapping values to the columns by their header names:
   - Company → the hiring company from the posting.
   - Job Title / Role / Position → the role title from the posting.
   - Date Applied / Date → today's date, formatted to match the existing rows in the sheet.
   - Any custom column → fill it if you can confidently infer the value from the posting or our conversation (e.g. Status = "Applied", Source/URL = the posting link). Leave a column blank rather than guessing.
4. **Write it:**
   - If a connector that can append or edit spreadsheet rows is available, append the row to the next empty line and confirm what you wrote.
   - If no write-capable connector is available (Google Drive can read but not append in place), present the row as a **tab-separated, paste-ready line** AND as a small table mapped to my headers, and tell me to paste it into the next empty row. Don't claim it was written automatically when it wasn't.
5. **Confirm**: briefly list what got logged to which columns, and note any column left blank.

## Guardrails
- Truthful framing of real experience only — never fabrication.
- Don't write a cover letter unless asked.
- Never overwrite existing rows in the tracker; only add a new one.
- If unsure which sheet or which column maps where, ask rather than guessing.
