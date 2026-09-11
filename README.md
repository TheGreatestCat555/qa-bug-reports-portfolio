# Manual QA Portfolio

This repository is a working collection of my manual testing practice: bug reports, test documentation, checklists, and exploratory testing notes.

I focus on clear reproduction steps, verifiable observations, practical risk assessment, and evidence that is safe to share publicly. Missing information is marked honestly instead of being reconstructed from memory.

## Selected work

| Area | Example |
|---|---|
| Bug reporting | [Localization issue in an iOS title](bug-reports/mobile-ios/MOBILE-IOS-001-cyrillic-title-character.md) |
| Bug reporting — ChatGPT | [Missing final response after completed tool execution on iOS](bug-reports/chatgpt/CHATGPT-IOS-001-empty-response-after-tool-execution.md) |
| Field workflow testing | [Amazon Flex apartment-location state desynchronization](bug-reports/amazon-flex/AMAZON-FLEX-001-apartment-location-state-desync.md) |
| Cross-application mobile testing | [YouTube PiP playback becomes unresponsive after switching to navigation](bug-reports/youtube-ios/YOUTUBE-IOS-001-pip-playback-unresponsive-after-app-switch.md) |
| Test design | [Test cases](test-cases/README.md) and [test scenarios](test-scenarios/README.md) |
| Exploratory testing | [Charters and session reports](exploratory-testing/README.md) |
| Checklists | [Localization testing checklist](checklists/localization-checklist.md) |

## How I work

- I separate observations from assumptions.
- I write steps that another tester can follow.
- I assess severity by user and product impact.
- I treat priority as a product decision, not a synonym for severity.
- I redact personal and account information before publishing evidence.
- I keep drafts clearly marked until the missing details are verified.

## Repository guide

| Directory | Contents |
|---|---|
| [`bug-reports`](bug-reports/README.md) | Defect reports grouped by product area |
| [`test-cases`](test-cases/README.md) | Detailed, execution-ready test cases |
| [`test-scenarios`](test-scenarios/README.md) | High-level coverage and end-to-end flows |
| [`exploratory-testing`](exploratory-testing/README.md) | Charters and time-boxed session notes |
| [`checklists`](checklists) | Reusable testing checklists |
| [`templates`](templates) | Templates used across the portfolio |
| [`documentation`](documentation) | Reporting standards and assessment rules |

## Current status

The repository is actively maintained. New material is added when it is supported by a real test session, reproducible behavior, or documented evidence.
