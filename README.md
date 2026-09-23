# One-Page Resume Optimizer

A Codex Skill for turning an editable resume into a polished one-page document while preserving its original format, visual system, evidence density, and role relevance.

## Core guarantees

- The target is exactly one rendered page.
- A content-bearing item that wraps to two or more lines must use at least 60% of the available width on its final line; 65%–85% is preferred.
- Languages, skills, honors, courses, contact details, dates, and similar metadata are exempt from the tail-line rule.
- Semantic compression—removing redundancy, rewriting, merging parallel information, and reordering—comes before visual compression.
- Tiny fonts, crushed line spacing, and unprofessional margins are not acceptable ways to fit one page.
- With a JD, the Skill prioritizes relevant experience and hard evidence, and never silently removes core experience.
- Native formatting is protected, including color, emphasis, bullets, icons, photos, macros, alignment, and hyperlinks.
- XeLaTeX/Overleaf resumes are edited in their existing `.tex` structure and judged from the rendered PDF. Word resumes retain their native styles and structure.

## Repository contents

- `SKILL.md` — Skill instructions and decision rules.
- `CHECKLIST.md` — final resume QA checklist.
- `evals/` — continuous evaluation protocol, sanitized cases, and recorded results.
- `CHANGELOG.md` — behavior and release history.
- `AGENTS.md` — mandatory repository workflow for future changes.

## Versioning

This project follows Semantic Versioning:

- **patch** — small rule corrections or clarifications;
- **minor** — new evaluation rules or format support;
- **major** — incompatible or substantial changes to core behavior.

## Development workflow

After changing behavior, run every relevant case in `evals/cases/`, record the result in `evals/results.md`, update `CHANGELOG.md`, inspect `git diff`, and use a descriptive conventional commit such as:

```text
feat: add JD-aware content prioritization
fix: prevent aggressive line-spacing compression
eval: add XeLaTeX resume case
docs: clarify tail-line utilization rule
```

Never commit real phone numbers, personal email addresses, government identifiers, or unredacted resume data. Evaluation cases must be synthetic or fully anonymized.

## Example invocation

> 用 One-Page Resume Optimizer 帮我把这份 XeLaTeX 简历收成一页，保留现有蓝色、bullet、加粗和照片。

