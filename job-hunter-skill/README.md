# Job Hunter — a Claude Skill for your job search

A [Claude Skill](https://support.claude.com/en/articles/12512198) that runs your job search every morning:

- **Searches everywhere** — LinkedIn, Indeed, Naukri, Foundit, Glassdoor, Instahyre, Wellfound, Cutshort, Shine and company career pages
- **Filters out ghost posts** — old, vague or fake listings are dropped before you see them
- **Tailors your resume and cover letter** for every job, without ever inventing experience
- **Applies only after you approve** — reply "apply 1, 3, 5" and it handles the rest
- **Checks your inbox *and* spam** for interview invites, and flags job scams
- **Prepares you for each interview** — company research, likely questions and answers from your own projects
- **Tracks your progress** in Google Sheets and shows it as a visual dashboard: application funnel, skill levels, weak areas

> **Status:** work in progress. The core skill (`SKILL.md`) is written; reference guides, the dashboard and tests are being added.

## How it works

```
job-hunter/
├── SKILL.md              Main instructions Claude follows
├── profile.example.md    Template for your personal details
├── profile.md            Your filled-in copy (git-ignored, never uploaded)
└── references/           Detailed checklists Claude opens only when needed
```

All personal data lives in `profile.md`, which is listed in `.gitignore`. The skill itself contains no personal information, so anyone can use it.

## Setup

1. **Download** this repository.
2. **Create your profile:** copy `job-hunter/profile.example.md` to `job-hunter/profile.md` and fill it in.
3. **Zip the `job-hunter` folder** (the folder itself must be at the root of the zip).
4. **Upload to Claude:** Customize → Skills → **+** → Upload a skill.
5. **Connect these in Claude** (Settings → Connectors): Gmail, Google Drive, Google Docs, Google Sheets. Indeed is optional.
6. **Try it:** ask Claude *"run my job search"*. To run it every morning, ask Claude to set it up as a scheduled task.

## Safety by design

- Never submits an application, sends an email or accepts an invite without your explicit approval.
- Never creates accounts, types passwords, solves CAPTCHAs or pays fees.
- Never edits your master resume — it works on copies.
- Never invents skills or experience.
- Limits itself to 15 applications a day, so your accounts stay in good standing.

## Built with

- [Claude](https://claude.ai) and Claude Code
- The open [Agent Skills](https://agentskills.io) format

## License

MIT — see [LICENSE](LICENSE).

## Author

**Manoj Kumaresan** — Full Stack Developer (.NET · Angular)
