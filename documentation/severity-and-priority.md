# Severity and Priority

Severity describes the effect of a defect on the product or user. Priority describes how urgently the team should address it. They are related but not interchangeable.

## Severity

| Level | Guidance |
|---|---|
| Critical | Data loss, security-critical impact, widespread outage, or a core flow is impossible with no workaround. |
| High | Major functionality is unavailable or seriously incorrect; the workaround is absent or impractical. |
| Medium | A feature is impaired, but the main task can be completed with a reasonable workaround. |
| Low | Minor visual, content, or usability impact that does not block the task. |

## Priority

| Level | Guidance |
|---|---|
| High | Needs prompt attention because of user reach, business risk, release timing, or escalation. |
| Medium | Should be planned for an upcoming cycle but does not require immediate action. |
| Low | Can be scheduled after higher-value work or handled opportunistically. |

## Assessment rules

- Base severity on observed impact, not how surprising the issue appears.
- Base priority on current product and delivery context; mark it `To be assessed` when that context is unknown.
- Explain each rating in the report.
- Do not label an observation a vulnerability without sufficient evidence.
