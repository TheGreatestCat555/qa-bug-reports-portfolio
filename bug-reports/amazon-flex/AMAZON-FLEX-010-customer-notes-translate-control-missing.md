# AMAZON-FLEX-010: Customer-notes translation control is no longer displayed

> **Status:** Draft

## Summary

Amazon Flex displayed English customer delivery notes while the application interface was in Russian, but the previously observed `Translate` / `Перевести` control was no longer visible. The missing control was shown in two field examples documented only a few days after the translation function had reportedly been available.

## Product and platform

- Product: Amazon Flex
- Component: Customer delivery notes and contextual translation control
- Platform: iOS

## Environment

| Field | Value |
|---|---|
| Device | iPhone; exact model not recorded in this source |
| OS version/build | Not recorded |
| Amazon Flex version/build | Not recorded |
| Application interface language | Russian |
| Customer-note language | English |
| Network conditions | Not recorded |
| Date documented | June 7, 2026 |
| Last-known-good date | Not recorded; described as a few days earlier |

## Preconditions

- Amazon Flex is displaying its interface in Russian.
- A delivery stop includes customer notes written in English.
- The customer-notes section is visible.

## Steps to reproduce

The feature's eligibility rules are unknown, so these steps describe the observed workflow rather than a guaranteed reproduction:

1. Open a delivery stop in Amazon Flex while the application interface is in Russian.
2. Open the customer delivery notes.
3. View notes written in English.
4. Inspect the contextual controls available for the notes.

## Actual result

- The English customer notes are displayed.
- No `Translate` / `Перевести` control is visible.
- Translation cannot be initiated from the displayed customer-notes area.
- The same absence is visible in two supplied field examples.

## Expected result candidate

If translation remains a supported feature for the account, locale, stop type, and application version, a visible translation control should allow English customer notes to be translated into the Russian interface language.

## Reproducibility

Observed in two field examples. No controlled attempt count was recorded, and the prior feature conditions are unknown.

## Severity

**Low candidate.** The core delivery workflow remained usable in the documented examples, and the translation function was described as a convenience. The comprehension and accessibility impact may be greater for drivers who cannot read the customer's language, but that broader impact was not measured.

## Priority

**To be assessed.** The prior feature contract, affected population, activation rules, duration, and affected-version range are unknown.

## Category

Potential Regression / Localization / Missing Contextual Control / Accessibility

## Evidence

- Two screenshots were supplied in the original field discussion.
- The screenshots are not included publicly because customer-written instructions and surrounding delivery UI can contain sensitive customer, route, stop, address, or access information.
- No earlier screenshot, application log, remote-configuration data, or product requirement proving universal availability of the translation control is available.

## Notes and limitations

- The owner remembered using the translation function only a few days earlier, but the last-known-good version and exact comparison conditions were not recorded.
- The observation does not establish whether the state was caused by a regression, temporary service issue, language detection, account or stop eligibility, remote configuration, an experiment, or intentional product change.
- It should not be claimed that an application or iOS update caused the change.
- A future verification should record the exact iOS and Amazon Flex builds, language settings, stop and order type, appearance on multiple stops in the same session, another device/account comparison, and a privacy-safe before/after capture.
