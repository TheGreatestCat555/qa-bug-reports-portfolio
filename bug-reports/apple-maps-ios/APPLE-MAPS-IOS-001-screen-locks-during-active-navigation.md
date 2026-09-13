# APPLE-MAPS-IOS-001: Device locks immediately after starting turn-by-turn navigation

> **Status:** Draft

## Summary

Immediately after turn-by-turn navigation is started in Apple Maps, an iPhone unexpectedly enters the lock-screen state. The user cannot interact with the map until the device is unlocked again. The behavior occurs whether navigation is launched from a third-party delivery application or directly in Apple Maps.

## Product and platform

- Product: Apple Maps / iOS
- Platform: iOS

## Environment

| Field | Value |
|---|---|
| Device | iPhone 14 Pro Max |
| OS version/build | Not recorded |
| Official release context | On March 20–21, iOS 26.3.1 was the latest standard release compatible with iPhone 14 Pro Max; released March 4, 2026. A Background Security Improvement became available March 17. The exact build/response installation was not verified. |
| Application | Apple Maps; version not recorded |
| Navigation state | Turn-by-turn navigation started with `Go` |
| Low Power Mode | Off |
| CarPlay | Not used |
| Charging state | Probably not charging; not confirmed |
| Auto-Lock setting | Disabled (`Never`) |
| Network and location conditions | Not recorded |
| Comparison device | Another iPhone 14 Pro Max on the same iOS version did not show the issue |
| Date and time | Exact occurrence not recorded; the field accounts were documented on March 20–21, 2026 |

## Preconditions

- The device is unlocked.
- Apple Maps is available on the device.
- Low Power Mode is disabled.
- CarPlay is not in use.
- System Auto-Lock is disabled (`Never`).
- A route can be calculated and started.

## Steps to reproduce

1. On the affected iPhone, open a destination in a third-party delivery application and tap its navigation action, or enter a destination directly in Apple Maps.
2. Confirm that Apple Maps opens with the selected destination.
3. Tap `Go` to start turn-by-turn navigation.
4. Observe the device immediately after navigation starts without pressing the hardware lock button.
5. Unlock the device and return to Apple Maps.

## Actual result

- Immediately after navigation starts, the device enters the lock-screen state as though the hardware lock button had been pressed, despite system Auto-Lock being disabled.
- The user must unlock the device again.
- The user cannot interact with the map while the lock screen is active.
- The behavior occurred frequently during the same day, estimated from memory at approximately 80–90% of navigation starts, but no counted sample was recorded.

## Expected result

Starting turn-by-turn navigation should leave Apple Maps visible and interactive. The device should not enter the lock-screen state when the user has not requested a lock and system Auto-Lock is disabled.

## Reproducibility

Observed frequently during one day on one iPhone 14 Pro Max. The reporter estimated approximately 80–90% of navigation starts, but the exact number of attempts was not counted. Another iPhone 14 Pro Max running the same iOS version did not show the issue. The behavior has not yet been retested on the current OS version.

## Severity

**High.** The issue interrupts active navigation, removes visible route guidance, and requires the user to unlock the phone. This can create a distraction risk if it occurs while the user is travelling. No accident or physical harm is asserted.

## Priority

**To be assessed.** The workflow impact is substantial, but the affected OS range, frequency across devices, and exact trigger are unknown.

## Category

Functional / Navigation / Power Management / State Management

## Evidence

- Environment screenshots existed in the private source discussion but are not included because safely reviewed and redacted source files are not currently available.
- Video of the lock event: Not available.
- Logs: Not available.

## Notes and limitations

- The exact iOS version/build was not retained and must not be reconstructed from memory. Both the affected and comparison devices were confirmed to be on the same version.
- Apple's [official security-release history](https://support.apple.com/en-ca/100100) makes iOS 26.3.1 the likely standard-release context for the documented dates, but does not override the missing device telemetry. Automatic Updates were reportedly enabled; rollout and installation timing remain unknown.
- System Auto-Lock was disabled (`Settings → Display & Brightness → Auto-Lock → Never`), so the observed lock was not the configured inactivity timeout.
- The report records that the device entered the lock-screen state; it does not assume which timer, application, framework, or OS component initiated it.
- The behavior appeared on the same day as an iOS update on the affected device, but this is only a temporal correlation. The update is not presented as a proven root cause.
- The unaffected comparison device had the same hardware model and iOS version. This excludes neither iOS nor Apple Maps; it only shows that the issue was not universal under the limited comparison.
- Google Maps and other navigation applications were not tested.
- The affected phone was probably not charging, but this condition was not confirmed.
- A separate recollection that automatic updates became enabled without user action is not part of this report because the earlier setting was not documented and the behavior was not independently reproduced.
- A future verification should capture the exact iOS build, a screenshot confirming `Auto-Lock → Never`, a counted reproduction rate, charging state, post-unlock route state, and a privacy-safe video recorded by a second device.
