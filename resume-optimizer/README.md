# 📄 Resume Optimizer — Setup Guide (read me first)

This skill does three things for any job you're applying to:
1. **Tailors your resume** to the posting (ATS-friendly).
2. **Writes a cover letter** — only when you ask.
3. **Logs the application** to your Google Sheets tracker (company, title, date, + your custom columns).

Setup takes about 10 minutes. You only do it once.

---

## ✅ Step 1 — Get your resume into the skill (two easy ways)

**Option A — Import your existing resume (no typing):**
Start a chat with the skill on, upload your real resume (`.docx`, `.pdf`, `.tex`, or paste it), and say *"import this as my master resume."* Claude converts it into the right format and hands you the text — paste that into `references/master-resume.md` (or save locally and re-upload). Best formats: **.docx, .tex, or paste**; PDF works but confirm the result if your layout is fancy.

**Option B — Just upload each time:**
Skip the stored file entirely. Whenever you run the skill, drag your resume into the chat and it'll use that. Zero setup; you re-upload each session.

**Option C — Fill in the template by hand:**
Open `references/master-resume.md` and replace the [brackets].

Then fill in this too (optional):
- [ ] `references/tracker-columns.md` — your tracker's columns + date format (or leave blank to auto-read your sheet).

> 💡 Keep these files as plain `.md` text — don't convert them to Word.

---

## ✅ Step 2 — Turn on the right settings

In Claude's **Settings**:
- [ ] **Code execution & file creation** = ON → lets the skill hand you a downloadable Word (.docx) resume.
- [ ] **Google Drive connector** = connected → lets the skill find and read your tracker spreadsheet.

---

## ✅ Step 3 — Package & upload

1. [ ] Zip the **`resume-optimizer` folder itself** (right-click → Compress / Send to → Zipped folder).
   - ✔️ Correct: the zip opens to one `resume-optimizer` folder with `SKILL.md` inside it.
   - ❌ Wrong: loose files at the top, or a doubled `resume-optimizer/resume-optimizer/`.
2. [ ] In Claude: **Customize → Skills → "+" → "+ Create skill"** → upload the zip.
3. [ ] Toggle the skill **ON** in your Skills list.

To change anything later: edit the file in this folder, re-zip, re-upload (it replaces the old version). Keep this folder as your master copy.

---

## ✅ Step 4 — Run it

Just start a normal chat and talk naturally. The skill loads itself. Examples:

- "Here's a job posting — tailor my resume." *(paste the posting)*
- "Tailor my resume **and** write a cover letter for this role."
- "Now log this to my tracker — it's the sheet called *Job Applications 2026*."

It will: show keyword matches + gaps → give you the tailored resume (and cover letter if asked) → then either log the row to your sheet or hand you a ready-to-paste row.

---

## 🔧 If something's off

| Problem | Fix |
|---|---|
| Skill doesn't activate | Make sure it's toggled ON. Or just say "use my resume optimizer skill." |
| Asks for my resume every time | Either store it in `references/master-resume.md`, or just upload your resume at the start of each chat (both work). |
| Can't find my tracker | Tell it the exact sheet name or paste the link. |
| Doesn't write to the sheet automatically | Expected for now — Google Drive can read but not write rows. It'll give you a paste-ready row instead. |
| .docx not generated | Turn on Code execution & file creation in Settings. |

---

## 🤷 What you can ignore

- This `README.md` is just for you — Claude doesn't use it when running the skill.
- You don't type any special command. Plain English triggers the skill.
