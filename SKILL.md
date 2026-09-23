---
name: one-page-resume-optimizer
description: Optimize an editable resume into a polished one-page layout while preserving its native format, visual system, evidence density, and role relevance. Use for XeLaTeX/Overleaf, Word/DOCX, or other editable resume formats when the user wants one-page pagination, high line utilization, JD-aware prioritization, and no destructive reformatting.
metadata:
  version: 1.0.0
---

# One-Page Resume Optimizer

## Purpose

Turn an existing resume into a strong, readable, visually balanced one-page resume without destroying its original design language or reducing content quality.

This is a render-aware layout optimizer, not a generic resume rewriter. Jointly optimize pagination, role relevance, evidence density, line-end utilization, readability, and preservation of the original formatting system. The final rendered output is the source of truth; source-code line count is not.

## One-page constraint

The resume must finish on one rendered page. If it overflows, use this order:

1. remove redundant wording;
2. improve low-utilization tail lines;
3. merge duplicated or parallel claims;
4. reorder content for more efficient wrapping;
5. compress lower-priority bullets or experiences;
6. with a JD, remove low-relevance content before high-relevance evidence;
7. make small spacing adjustments;
8. only as a last resort, make minimal font-size, line-spacing, or margin adjustments.

Never force one page by making the resume visibly cramped. If essential evidence cannot fit readably, cut lower-value content instead of crushing typography.

## Tail-line utilization

Apply this rule to content-bearing items whose purpose is to demonstrate the value of an experience, including product/project, internship/work, relevant, research, and substantial education/project items.

Do not apply it to short metadata or list-like content such as languages, skills, honors, course lists, contact information, title rows, dates, or one-line factual labels.

For every content-bearing item that wraps to two or more rendered lines:

- the final line must occupy at least 60% of the usable text width after indentation;
- 65%–85% is preferred when it produces a balanced wrap;
- one-line items are exempt.

Fix a short tail by deleting redundancy, reordering or merging clauses, shortening verbose phrases, or adding genuinely useful missing evidence. Useful additions include decision logic, user insight, validation, metrics, trade-offs, mechanisms, business impact, or AI reliability logic. Never add filler merely to stretch a line.

## Preserve the original visual system

Treat the existing design as protected unless the user explicitly requests a redesign. Preserve, where present:

- colors, rules, and visual hierarchy;
- bold, italic, and highlighted text;
- bullets, icons, and hyperlinks;
- project/company title hierarchy and date alignment;
- school tags, photos, tables, grids, and indentation;
- custom macros, style commands, and heading levels.

Do not silently replace the resume with a new template or flatten formatted text into plain text.

## JD-aware prioritization

When a job description is provided, prioritize:

1. hard evidence directly relevant to the target role;
2. projects and experience demonstrating core role competencies;
3. quantified outcomes and validation;
4. technical or product mechanisms that can survive interview follow-up;
5. transferable business, data, and user insight.

Low-relevance content may be shortened, moved down, or removed to meet the one-page constraint. However, do not silently delete a core experience, remove the strongest evidence merely because it is long, fabricate relevance, add unearned technologies, or upgrade “learning” to “proficient.” Explain any removed or materially de-emphasized experience.

## Semantic compression before visual compression

Remove repeated generic claims, replace long summaries with concrete mechanisms or metrics, merge bullets that describe the same problem or workflow, and delete details implied by stronger evidence. Preserve the core logic of strong bullets.

For strong product or AI bullets, preserve when supported:

**Problem → Mechanism / Product decision → Validation / Evidence / Outcome**

For AI product roles, also preserve relevant capability boundaries, guardrails, evaluation, and user validation.

## Anti-cramping rules

Only adjust layout after content optimization. Make small, incremental changes to section spacing, item spacing, paragraph spacing, line spacing, or margins.

By default:

- preserve the original body font size;
- do not reduce body font by more than about 0.3 pt in one optimization cycle without a strong reason;
- do not reduce line spacing by more than about 3%–5% from the readable baseline;
- do not collapse section spacing until headings touch adjacent content;
- do not use unprofessional margins merely to fit one page;
- do not create dense walls of text.

If the source already uses compact typography, prefer content cuts. Balanced bottom whitespace is acceptable.

## Format-aware editing

Identify the native format before editing and modify the resume in its original authoring system whenever possible.

### XeLaTeX / Overleaf

Edit the existing `.tex` source. Preserve its document class, packages, macros, colors, icons, emphasis, links, list structures, and section styles. Compile with XeLaTeX when available and judge pagination and tail-line utilization from the rendered PDF. Do not rebuild it in a new template unless explicitly requested.

### Word / DOCX

Preserve native paragraph styles, fonts, emphasis, bullets, tabs, tables, text boxes, images, and page geometry. Edit text inside the existing structure and judge the result from the rendered Word/PDF layout. Avoid destructive conversion between Word and LaTeX.

### Other formats

Preserve the native format and evaluate the rendered output. If only a screenshot or PDF is available, explain what can be optimized conceptually and request an editable source before direct modification.

## Render-review loop

For every meaningful layout revision:

1. render or compile the resume;
2. confirm it is exactly one page;
3. inspect clipping, overlap, balance, and readability;
4. inspect every content-bearing multi-line item;
5. count final lines under 60%;
6. fix them through meaningful restructuring, expansion, or compression;
7. verify no new short tail lines appeared elsewhere;
8. verify protected formatting and core evidence remain intact;
9. when a JD exists, verify high-relevance content is retained and prioritized.

Do not stop after source edits if a rendered preview is available.

## Content density audit

Classify content as core evidence, supporting evidence, low-priority evidence, or metadata. Keep core evidence; keep supporting evidence if space allows; compress or remove low-priority evidence first; keep metadata concise and exempt from the tail-line rule. With a JD, classification must reflect the target role.

## Final quality gate

A finished resume must pass `CHECKLIST.md`. At minimum, verify:

- exactly one page with no clipping, overlap, or overflow;
- zero unexplained content-bearing multi-line items below 60% final-line utilization;
- no filler or invented facts;
- no destructive formatting changes;
- no tiny fonts, crushed spacing, or unprofessional margins;
- original hierarchy, colors, emphasis, bullets, icons, photos, links, alignment, and macros preserved;
- core experience and hard evidence retained, with material removals disclosed;
- JD-aware ordering and retention when a JD is provided;
- edits remain defensible in an interview.

## Response behavior

Return the revised source/document or exact replacement blocks, a concise explanation of major space-saving choices, any content removed or materially deprioritized and why, and whether the final render passed pagination and tail-line checks. Prefer surgical edits when only a few lines must be saved. When a complete source file is requested, return a complete source file.

## Repository evaluation

For changes to this Skill itself, follow `AGENTS.md`, run all relevant cases described in `evals/README.md`, and append every result to `evals/results.md`. Never add real resume PII to evaluation fixtures or repository history.
