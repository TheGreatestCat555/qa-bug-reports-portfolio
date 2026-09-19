# Bug Reporting Guidelines

## Core rules

- Record observed facts and clearly separate them from assumptions.
- Use one Markdown file per bug and a sequential product-specific ID.
- Write public reports in clear professional English.
- Prefer direct, case-specific language over generic filler, exaggerated conclusions, or repetitive template phrasing. Reports should read like careful human QA work, not automated prose.
- Use only the sections that help explain the defect; do not inflate a small observation into several artificial issues.
- Vary sentence structure naturally while keeping terminology consistent, and remove meta-commentary about drafting, generation, or assistant involvement.
- Use `Not recorded` or `Not available` instead of inventing missing data.
- Keep steps atomic, ordered, and reproducible.
- Separate Actual Result from Expected Result.
- Explain severity and priority independently.
- Link each report from the product README and central index.
- Redact sensitive evidence before it enters Git history.

## File naming

Use `PRODUCT-PLATFORM-NNN-short-description.md`, for example:

```text
MOBILE-IOS-001-cyrillic-title-character.md
```

Use Latin characters, hyphens, and a concise description.

## Definition of Done

A report is portfolio-ready when its unique ID, title, product, platform, known environment, preconditions, reproduction steps, actual and expected results, reproducibility, severity, priority, evidence state, privacy review, index entry, product README entry, links, and English have all been checked.
