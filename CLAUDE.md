# CLAUDE.md - Actua Learning (ACTUA-TUTORIAL)

Instructions for AI assistants working in this repository.

## What this is

Actua Learning is the multipage training website of Actua Business Services Limited, Shaun's accountancy firm. It hosts visual tutorials for both clients and staff.

- Live: https://connex222.github.io/ACTUA-TUTORIAL/ (GitHub Pages, updates automatically from `main`)
- Title is the ACTUA logo; the main colour is the logo's teal lettering.

## Architecture

| Part | Location |
|---|---|
| Home, about, course list, paths, progress | root `*.html` |
| Learning paths | `path-*.html` |
| One self-contained file per course | `courses/*.html` (34 courses) |

## Staff-only courses (security)

- 13 courses are encrypted with AES-GCM; the key comes from the staff password via PBKDF2 (SHA-256, 310,000 iterations). They are: anti-money-laundering, client-onboarding, cyber-security-gdpr, excel-for-accountants, iris-accounts-production, iris-business-tax, iris-company-secretarial, iris-personal-tax, iris-practice-management, microsoft-365, sage-50-payroll, staffology-payroll, year-end-close.
- **The repository is public.** Never commit a staff course unencrypted, never commit the password, and never put it in a comment, file name or commit message.
- The password is kept only for the browser session (`sessionStorage`, key `actua.staff.pw`).
- Protection is only as strong as the password. It should be a long passphrase, and changed (with all 13 courses re-encrypted) when a member of staff leaves.

## Content rules

- Every tutorial carries the credit "By Shaun Ellison & Actua Business Services Limited, with AI".
- All tutorials share one house style: they should look related but not identical, to a premium standard.
- **Accuracy and compliance matter.** Tax rates, thresholds, deadlines and software steps must be checked against current official sources (GOV.UK, HMRC, the software vendor's own help) before publishing, with the date checked noted in the course.
- Name trademarks correctly and keep the trademark notice.
- UK English; plain language for clients; no jargon without an explanation.

## Working with Shaun (the owner)

- Shaun is not a programmer. Explain every step in plain English, in order, and assume no prior knowledge.
- Always return complete files, never partial snippets or "..." placeholders.
- Use UK English.
- Never delete files to tidy up; move old notes into `docs/` instead.
- Never force-push, rewrite history or rename the repository.
