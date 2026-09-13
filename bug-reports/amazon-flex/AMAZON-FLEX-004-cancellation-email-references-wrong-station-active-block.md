# AMAZON-FLEX-004: Cancellation email references a different station while the scheduled block remains active

> **Status:** Draft

## Summary

An Amazon Flex email stated that an upcoming block had been canceled, that the driver did not need to attend, and that payment would still be provided. The station identified in the email did not match the station of the driver's only block scheduled for that time. The actual block remained active in the application, and the driver was able to complete the normal arrival, identity-verification, and check-in steps at the correct station.

## Product and platform

- Product: Amazon Flex driver application and block-notification email
- Platform: iOS and email

## Environment

| Field | Value |
|---|---|
| Device | iPhone 14 Pro Max |
| OS version/build | Not recorded |
| Official release context | iOS 26.4 was released for iPhone 11 and later on March 24, during the documented March 24–25 window. Automatic Updates were reportedly enabled, but it is unknown whether this report occurred before or after installation; iOS 26.3.1 therefore also remains plausible. |
| Application version/build | Not recorded |
| Account state | One scheduled early-morning block at the relevant time |
| Network | Not recorded |
| Date | March 24–25, 2026 |

## Preconditions

- The driver has exactly one block scheduled for the relevant start time.
- The scheduled block is associated with one station.
- Email notifications for block changes are enabled and deliverable.

## Steps to reproduce

The notification-generation condition cannot currently be reproduced on demand. The observed field sequence was:

1. Maintain one scheduled block for the relevant start time in the Amazon Flex application.
2. Receive an email stating that a block for that time has been canceled, attendance is not required, and payment will still be provided.
3. Observe that the email references a different station from the station shown for the scheduled block.
4. Open the Amazon Flex schedule and inspect the block.
5. Observe that the block remains present and active.
6. Travel to the station shown for the active block and begin the arrival workflow.
7. Complete the parking confirmation, selfie verification, and driver-license scan.

## Actual result

- The email described the block as canceled and instructed the driver not to attend.
- The station referenced by the email did not match the station attached to the only scheduled block at that time.
- The scheduled block remained visible and active in the application.
- At the correct station, the application accepted the normal arrival workflow, selfie verification, and driver-license scan.
- Support did not provide a definitive explanation or confirm which system state should be trusted before the block.

## Expected result

- A cancellation email should be sent only for the block and station that were actually canceled.
- A canceled block should have a consistent state across email, push notifications, the in-app schedule, and station check-in systems.
- If the email refers to a different block or station, it should contain enough unambiguous non-sensitive identifiers for the driver to distinguish it from an active assignment.
- Support should be able to confirm whether the scheduled block remains valid when notification channels conflict.

## Reproducibility

Observed once. The erroneous notification-mapping condition has not been reproduced in a controlled test.

## Severity

**High.** Trusting the cancellation email could cause a driver to miss an active block, lose expected earnings, or receive an attendance-related penalty. Ignoring a valid cancellation could instead cause unnecessary travel. The driver avoided the immediate impact only by checking the application and attending the active block.

## Priority

**High candidate.** The observation is currently isolated, but conflicting instructions concerning attendance and payment require timely investigation because either interpretation can materially affect the driver.

## Category

Functional / Data Integrity / Cross-Channel Consistency / Notification Mapping

## Evidence

- A historical field account records the cancellation wording, station mismatch, active in-app schedule, and successful station check-in.
- The original email, screenshots, station codes, address, and account information are intentionally excluded from the public report to protect privacy.
- Support correspondence and logs: Not available in a safely redacted form.

## Notes and limitations

- Compatible release context is based on Apple's [official security-release history](https://support.apple.com/en-ca/100100). The release boundary falls inside the reported date window, so neither iOS 26.3.1 nor iOS 26.4 may be recorded as confirmed.

- The report does not establish whether the email belonged to another driver, another block, a station-wide cancellation batch, or an incorrectly mapped notification record.
- The exact push-notification wording and its relationship to the email were not retained clearly enough to treat them as independent evidence.
- Successful arrival and identity verification strongly indicate that the in-app block was active, but internal scheduling and payment records are unavailable.
- Receipt of payment and the final attendance standing were not independently verified in the retained account.
- A future verification should preserve privacy-safe copies of the email and schedule, message headers or notification identifiers, exact timestamps, application version, support case ID, final earnings entry, and attendance history.
