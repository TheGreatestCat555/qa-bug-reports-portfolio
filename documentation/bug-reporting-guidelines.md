# Bug Reporting Guidelines

## Core rules

- Record observed facts and clearly separate them from assumptions.
- Use one Markdown file per bug and a sequential product-specific ID.
- Write public reports in clear professional English.
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
