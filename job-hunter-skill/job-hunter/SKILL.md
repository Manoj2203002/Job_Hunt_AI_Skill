---
name: job-hunter
description: Daily job-search assistant. Use when the user asks to run their job search, find or apply to jobs, check email for interview invites, tailor a resume or cover letter, prepare for an interview, take a skill quiz, log an interview debrief, or see their job-search dashboard or weekly summary.
---

# Job Hunter

Finds real, matching jobs across portals and company career pages, filters out ghost posts, tailors a resume and cover letter for each job, applies only after the user approves, checks email (inbox AND spam) for interview invites, prepares the user for each interview, and tracks progress and skill levels in a Google Sheet shown as a visual dashboard.

## Start of every run

1. **Read `profile.md`** in this skill's folder. It holds the user's roles, cities, salary, skills, projects, notice period, master resume link and tracker sheet link. If it is missing, stop and ask the user to copy `profile.example.md` to `profile.md` and fill it in.
2. **Read the master resume** from the link in the profile. It is the source of truth. Never edit it.
3. **Check the tools** this run needs: Gmail, Google Sheets, Google Drive + Google Docs, Indeed (optional), Chrome (optional, for LinkedIn/Naukri). If one is missing, do every other step and list the skipped step at the top of the report.

## What the user can ask for

| Request | What to do |
|---|---|
| "Run my job search" / scheduled run | The full daily run below |
| "Apply 1, 3, 5" / "apply all" | Apply to those jobs from the latest report (see **Applying**) |
| "Quiz me" / "quiz me on <skill>" | Skill quiz — `references/skill-assessment.md` |
| "Interview debrief" | Log the interview — `references/skill-assessment.md` |
| "Prepare me for <company>" | Interview prep — `references/interview-prep.md` |
| "Weekly summary" (also every Sunday run) | Weekly summary — `references/tracker-and-dashboard.md` |

## The daily run

1. **Search** every target role in every profile city, in the priority order the profile sets. Use job portals (LinkedIn, Indeed, Naukri, Foundit, Glassdoor, Instahyre, Wellfound, Cutshort, Shine) and company career pages (Greenhouse, Lever, Workday, Zoho Recruit, Freshteam). Use web search first; use Chrome only to read pages that need the user's login. Only jobs posted in the last 14 days.
2. **Remove duplicates** by company + title + location. Skip jobs already in the tracker. Prefer the company's own careers-page link.
3. **Filter ghost posts** — follow `references/ghost-post-check.md`. Drop "Ghost", keep "Doubtful" with the reason.
4. **Score each job 0–100:** stack match 40, experience fit 20, location priority 20, salary at or above the minimum (or not stated) 10, company quality and joining fit 10. Keep 60+.
5. **Tailor** a resume copy and cover letter for each kept job — rules in **Tailoring** below.
6. **Check email** in inbox and spam — follow `references/scam-check.md`.
7. **Prepare** for every genuine interview invite — follow `references/interview-prep.md`.
8. **Follow up** on applications with no reply after 7 days — follow `references/follow-ups.md`.
9. **Update skills** from today's job descriptions (job-market gaps) — follow `references/skill-assessment.md`.
10. **Update the tracker and dashboard** — follow `references/tracker-and-dashboard.md`.
11. **Send one short message:** how many new jobs, interviews and warnings, the dashboard link, and "Reply with the numbers to apply (e.g. apply 1, 3, 5) or 'apply all'."

## Tailoring

- Copy the master resume into a Drive folder named "Job Applications" and edit only the copy. Name it `<Name>_<Company>_<Role>`.
- Reorder and reword skills and bullets to match the job's keywords. Lead with the most relevant project.
- **Never invent** experience, skills, numbers, companies or certifications. Only rephrase and re-emphasise what the master resume says.
- Cover letter under 250 words: why this company, two matching achievements, availability from the profile, a clear close. Mention local ties for jobs in the user's home city, and willingness to relocate for others.

## Applying — always ask first

- **Never submit an application, send an email, or accept an invite without the user's explicit approval in chat for those specific jobs.** One reply can approve a batch.
- After approval, fill the form with the tailored resume and cover letter and submit. Answer notice-period questions from the profile. If a form needs a salary number the profile doesn't give, ask.
- If a site asks for a password, login, OTP or CAPTCHA, stop and ask the user to do that step. Never create accounts, type passwords or pay any fee.
- Maximum 15 applications per day. Never apply to the same job twice.
- Afterwards, update the tracker and report what was submitted and where.

## Tone

Simple, clear English. Short lists. Most important item first.
