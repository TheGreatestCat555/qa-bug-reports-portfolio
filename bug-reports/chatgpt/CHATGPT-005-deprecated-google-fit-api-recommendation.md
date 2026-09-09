# [CHATGPT-005] Technical guidance recommends Google Fit API for a new Android application after new developer access was closed

> **Status:** Draft — historical observation; the original platform and current model behavior need verification.

## Summary

When asked how a new Android application could connect game progress with real-world travel data, ChatGPT recommended the Google Fit API as an implementation option. At the time of the response, new developers had already been unable to register for Google Fit APIs since May 1, 2024, and Google was directing developers toward Android Health APIs such as Health Connect.

## Product and platform

- Product: ChatGPT
- Platform: Not confirmed
- Feature: Technical guidance / Android API recommendations
- Subject: Health and travel data integration for a new Android application

## Environment

| Field | Value |
|---|---|
| Device | Not recorded |
| Operating system | Not recorded |
| ChatGPT version/model | Not recorded |
| Interface language | Russian |
| Date of observation | September 28, 2025 |

## Preconditions

1. Open a ChatGPT conversation.
2. Describe a new Android application that needs to derive progress from real-world travel or activity data.

## Steps to reproduce

1. Ask ChatGPT how to implement synchronization between an Android application and real-world distance traveled.
2. Review the recommended Android data sources and APIs.
3. Compare the recommendation with Google's developer-access and migration documentation that applied at the time.

## Actual result

ChatGPT recommends `Google Fit API` as an Android implementation option without warning that:

- new developers had been unable to sign up for Google Fit APIs since May 1, 2024;
- the APIs were scheduled for deprecation;
- Google recommended Android Health APIs, including Health Connect, for relevant new mobile integrations.

The answer therefore presents an unavailable or unsuitable starting point as a practical option for a new project.

## Expected result

ChatGPT should identify Google Fit APIs as a legacy integration with restricted new-developer access and recommend a currently supported implementation path. Depending on the application's actual requirements, the answer should distinguish between:

- Health Connect or another current Android Health API for supported health and activity records;
- Android location APIs for direct trip tracking;
- the permissions, privacy disclosures, background-execution limits, battery impact, and user-safety requirements associated with location collection.

## Reproducibility

Observed once in a historical conversation. Current behavior has not been retested.

## Severity

**Medium.** The recommendation can send a developer toward an integration that was already closed to new registrations, causing wasted implementation time and an avoidable redesign.

## Priority

**Medium.** Deprecated-platform guidance is actionable and time-sensitive, although the issue may already be corrected in current models.

## Category

Content Accuracy / Technical Guidance / Deprecated API

## Evidence

- The privacy-reviewed conversation excerpt records the implementation question and the recommendation to use Google Fit API.
- Google states that developers have been unable to sign up for Google Fit APIs since May 1, 2024: [Google Fit Migration FAQ](https://developer.android.com/health-and-fitness/health-connect/migration/fit/faq).
- Google's migration guidance recommends supported alternatives such as Health Connect for relevant new mobile integrations: [Fit migration guide](https://developer.android.com/health-and-fitness/health-connect/migration/fit).
- Screenshots and the complete conversation are not included in the public repository because they contain unrelated private project material.
- Logs: Not available.

## Notes and follow-up

- Retest with a prompt that explicitly states that the application is a new Android project.
- Record whether ChatGPT warns about Google Fit API access and deprecation without being prompted to verify recency.
- Verify that the response selects an API based on the required data rather than treating health records and direct GPS trip tracking as interchangeable.
- Platform policies and API timelines can change; verify them against current official documentation during retesting.
