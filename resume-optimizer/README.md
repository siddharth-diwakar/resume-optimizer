# 📄 Resume Optimizer — Setup Guide (read me first)

This skill does three things for any job you're applying to:
1. **Tailors your resume** to the posting — keyword-tiered (must-have / should-have / bonus), ATS-mechanical (heading whitelist, single-column, no tables), bullet craft uses the XYZ formula with strong verbs and quantified impact, and there's a pre-delivery diff against your master resume so you can catch anything you don't want claimed.
2. **Writes a cover letter** — only when you ask. Not a prose version of your resume: one specific story from your experience that demonstrates the behavior the JD actually rewards, plus a qualitative read on why you'd be good to work with.
3. **Logs the application** to your Google Sheets tracker (company, title, date, status, + your custom columns).

Setup takes about 10 minutes. You only do it once.

---

## ✅ Step 1 — Get your resume into the skill (three options)

**Option A — Import your existing resume (no typing):**
Start a chat with the skill on, upload your real resume (`.docx`, `.pdf`, `.tex`, or paste it), and say *"import this as my master resume."* Claude converts it into the right format and hands you the text — paste that into `references/master-resume.md` (or save locally and re-upload). Best formats: **.docx, .tex, or paste**; PDF works but confirm the result if your layout is fancy.

**Option B — Just upload each time:**
Skip the stored file entirely. Whenever you run the skill, drag your resume into the chat and it'll use that. Zero setup; you re-upload each session.

**Option C — Fill in the template by hand:**
Open `references/master-resume.md` and replace the [brackets]. See `references/master-resume-example.md` for a filled-in example showing the depth and bullet style that tailors well.

> 💡 The skill works best when your master resume includes EVERYTHING — extra roles, extra bullets, projects you wouldn't normally fit on one page. Tailoring trims; it can't add what isn't there.

Then fill in this too (optional):
- [ ] `references/tracker-columns.md` — your tracker's columns + date format (or leave blank to auto-read your sheet).

> 💡 Keep these files as plain `.md` text — don't convert them to Word.

---

## ✅ Step 2 — Turn on the right settings

In Claude's **Settings**:
- [ ] **Code execution & file creation** = ON → lets the skill hand you a downloadable Word (.docx) resume.
- [ ] **Google Drive connector** = connected → lets the skill find and read your tracker spreadsheet.

> 💡 **Want true auto-write to your tracker?** The Google Drive connector can read your sheet but can't append rows to it. If you want the row written automatically (instead of the paste-ready fallback), the simplest fix is a tiny **Google Apps Script webhook**: add a script to your sheet, deploy it as a web app, and tell the skill the URL. Otherwise it'll hand you a paste-ready row — perfectly fine for most people.

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

- "Here's a job posting — tailor my resume." *(paste the posting; skill may ask follow-ups for any gap it finds in your master resume before tailoring, and will show you a diff before delivering)*
- "Tailor my resume **and** write a cover letter for this role." *(skill may ask you a few questions about the story behind one of your resume bullets — that's how it avoids resume-rehash mode)*
- "Now log this to my tracker — it's the sheet called *Job Applications 2026*."
- "Update the Acme application — I got the OA."  *(status update on an existing row)*

It will: show a tiered keyword table (must-have / should-have / bonus) with gaps → give you the tailored resume (and cover letter if asked) → then either log the row to your sheet or hand you a ready-to-paste row.

Generated files are named `Resume_{Company}_{Role}_{YYYY-MM-DD}.docx` and `CoverLetter_{Company}_{Role}_{YYYY-MM-DD}.docx`.

---

## 🔧 If something's off

| Problem | Fix |
|---|---|
| Skill doesn't activate | Make sure it's toggled ON. Or just say "use my resume optimizer skill." |
| Asks for my resume every time | Store it in `references/master-resume.md`, or just upload it at the start of each chat. |
| Can't find my tracker | Tell it the exact sheet name or paste the link. |
| Doesn't write to the sheet automatically | Expected with just the Drive connector (read-only). It'll give you a paste-ready row. For true auto-write, see the Apps Script webhook note in Step 2. |
| Duplicate row got added | Shouldn't happen — the skill dedups by Company + Role within 30 days. If it did, file a note for yourself; otherwise tell the skill to clean it up. |
| .docx not generated | Turn on Code execution & file creation in Settings. |
| Stored tracker columns don't match my sheet | The skill always re-reads the live header and flags drift — update `tracker-columns.md` when convenient, or just leave it blank. |

---

## 🤷 What you can ignore

- This `README.md` is just for you — Claude doesn't use it when running the skill.
- `references/master-resume-example.md` is a reference example only; the skill never sources content from it.
- `references/cover-letter-guide.md`, `references/keyword-rubric.md`, `references/bullet-craft.md`, and `references/ats-format-spec.md` are reference rules the skill follows — you don't need to touch them unless you want to customize the playbook.
- You don't type any special command. Plain English triggers the skill.
