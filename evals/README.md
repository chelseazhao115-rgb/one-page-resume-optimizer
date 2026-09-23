# Continuous Evaluation

Run the relevant cases after every modification to the Skill. A change is incomplete until its results are appended to `results.md`.

## Required checks

For each case, inspect the final rendered document and record:

1. **Page count** — must be exactly 1.
2. **Tail-line failures** — count content-bearing multi-line items whose final rendered line occupies less than 60% of usable width. Exempt metadata must not be counted.
3. **Typography and geometry** — compare font size, line spacing, section spacing, and margins with the source; fail visibly cramped or disproportionate output.
4. **Format preservation** — compare colors, emphasis, bullets, icons, photos, hyperlinks, alignment, tables, and custom macros/styles with the source.
5. **Content integrity** — verify that core experiences and hard evidence were retained, or that any material removal was explicitly disclosed.
6. **JD relevance** — when a JD exists, verify that high-relevance evidence is retained and ordered ahead of lower-relevance content.
7. **Privacy** — verify the case and generated artifacts contain no real phone number, personal email, government identifier, or other private resume data.

## Procedure

1. Copy `cases/case-template.md` to a new, descriptive case file.
2. Use only synthetic or fully anonymized content.
3. Produce the optimized source and render it in its native authoring system.
4. Measure tail-line utilization after bullet indentation: `final-line width / usable text width * 100`.
5. Complete every applicable expected check in the case file.
6. Append a result block to `results.md` using the required schema.
7. Mark `Verdict: PASS` only when all applicable hard requirements pass.

## Result schema

```yaml
Version: 1.0.0
Case: descriptive-case-name
Before: concise baseline and measurements
After: concise final state and measurements
Changes: concise description of behavior or edits evaluated
Verdict: PASS
```

Use `Verdict: FAIL` if any hard requirement fails. Do not overwrite historical entries; append a new entry for every evaluation run.

