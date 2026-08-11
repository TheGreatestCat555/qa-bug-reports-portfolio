# [MOBILE-IOS-001] Mixed-script character appears in a generated title

> **Status:** Draft — environment, reproduction details, and evidence still need verification.

## Summary

A generated title contains a Cyrillic character in a word that otherwise uses Latin characters. The characters look similar but have different Unicode values, which can cause inconsistent search, copying, comparison, or text processing.

## Product

Consumer mobile application (anonymized for the public portfolio)

## Platform

iOS

## Environment

| Field | Value |
|---|---|
| Device | Not recorded |
| iOS version | Not recorded |
| Application version/build | Not recorded |
| Account state | Not recorded |
| Region and language | Not recorded |
| Date and time | Not recorded |

## Preconditions

Not recorded.

## Steps to reproduce

Not recorded. The issue must be reproduced in a new test session before this report can be marked ready.

## Actual result

The generated title contains a visually similar Cyrillic character inside text expected to use the Latin script.

## Expected result

Characters in a generated title should use the intended script consistently unless mixed scripts are required by the source text or user context.

## Reproducibility

Not recorded.

## Severity

To be assessed after the affected behavior, frequency, and user impact are confirmed.

## Priority

To be assessed with product context. No delivery or release information was available at the time of observation.

## Category

Localization / Content

## Evidence

Not available in the public repository. Any future screenshot must be redacted before it is added to the [`evidence`](evidence/README.md) directory.

## Follow-up

- Reproduce the issue on a recorded device and application build.
- Identify the exact Unicode character and expected character.
- Check whether the result affects search, sorting, copying, or title matching.
- Record the reproduction rate.
- Add redacted evidence if the behavior is reproduced.
