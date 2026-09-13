# FIND-MY-IOS-001: Location sharing stops without an alert after one device becomes signed out

> **Status:** Draft

## Summary

Location sharing between two iPhones stopped updating without a noticed warning. The receiving device continued to show the other device's last known location with an increasingly old timestamp before reporting that data was unavailable. Inspection of the source device later showed a sign-in prompt, indicating that its account session was no longer active and location sharing could not continue.

## Product and platform

- Product: Find My / Apple Account services
- Platform: iOS

## Environment

| Field | Value |
|---|---|
| Devices | Two iPhone 14 Pro Max devices |
| OS version/build | Not recorded |
| Official release context | On the March 16 documentation date, iOS 26.3.1 was the latest standard release compatible with iPhone 14 Pro Max; released March 4, 2026. Automatic Updates were reportedly enabled, but installation on either device was not verified. |
| Application | Find My; version not recorded |
| Configuration | Continuous mutual location sharing between two accounts/devices |
| Network | Not recorded |
| Date and time | Exact occurrence not recorded; the field account was documented on March 16, 2026 |

## Preconditions

- Two iPhones are configured to share their locations with each other in Find My.
- Location sharing previously updates dynamically during normal use.
- At least one of the devices receives an iOS update before the observed failure.

## Steps to reproduce

The account/session condition cannot currently be reproduced on demand. The observed field sequence was:

1. Maintain continuous location sharing between the two devices.
2. Allow the affected device to complete an iOS update.
3. Continue using both devices normally.
4. Later in the day, open Find My on the receiving device.
5. Observe the displayed location and its age over several hours.
6. After the location remains stale, inspect Find My or the relevant account state on the source device.

## Actual result

- The receiving device displayed a fixed last-known location instead of current movement.
- The age of that location increased from approximately three hours to five hours.
- The interface then showed loading or unavailable data while the same last location remained visible.
- The stale location condition persisted for approximately 22–24 hours.
- On the source device, a sign-in prompt was displayed and active location sharing was no longer available.
- No clear warning about the sign-out or loss of location sharing was noticed before the source device was inspected.

## Expected result

Location sharing should continue while the required account and permissions remain valid. If an account session becomes invalid or location transmission stops, both the source and receiving user should receive a clear and timely indication that live sharing is no longer active and that sign-in or another recovery action is required.

## Reproducibility

Observed once across one pair of iPhone 14 Pro Max devices. The sign-out condition and update sequence have not been reproduced in a controlled test.

## Severity

**High.** The failure disables a core location-sharing workflow and may delay recognition that live location data is unavailable. The displayed timestamps did indicate that the location was old, so the report does not claim that stale data was presented as current. Potential safety uses involving family members, vulnerable people, or lost devices increase the impact, but no injury or emergency is asserted.

## Priority

**To be assessed.** The potential impact is substantial, but frequency, affected account states, and the relationship to the OS update are unknown.

## Category

Functional / Account Session / Location Sharing / Error Communication

## Evidence

- A historical user account documents the timeline from a location approximately three hours old to five hours old, later unavailable data, and a stale point persisting for roughly one day.
- Screenshots were referenced in the private discussion but are not included because safely reviewed and redacted source files are not currently available.
- Logs: Not available.

## Notes and limitations

- The exact iOS version/build was not retained.
- Release timing is based on Apple's [official security-release history](https://support.apple.com/en-ca/100100). Because the occurrence date was not retained and two devices were involved, it does not establish either installed build.
- The source device showed a generic requirement to sign in; the precise service, screen, account state, and message text were not recorded. The report therefore does not claim which internal credential or token was invalidated.
- The issue was noticed after an iOS update, but the update is only a temporal correlation and is not presented as the proven cause of the sign-out.
- No notification was noticed. This does not prove that the system generated no notification; notification settings, Focus state, and Notification Center history were not recorded.
- The receiving interface showed timestamps such as approximately three and five hours ago. The report does not claim that the stale location was labelled as live.
- It is unknown whether the affected device still had network access, Location Services permission, Find My network settings, or location sharing enabled at the moment updates stopped.
- A future verification should capture the exact OS build, Apple Account and Find My status before and after an update, notification settings, connectivity, permissions, safely redacted screenshots, and the exact recovery steps required.
