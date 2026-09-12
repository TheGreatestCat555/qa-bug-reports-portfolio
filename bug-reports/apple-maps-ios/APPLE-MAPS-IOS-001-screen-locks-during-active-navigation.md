# APPLE-MAPS-IOS-001: Screen locks and map state resets during active turn-by-turn navigation

> **Status:** Draft

## Summary

During active turn-by-turn navigation in Apple Maps, an iPhone can unexpectedly enter the lock-screen state after several minutes. After the user unlocks the device, the visible map/navigation state is reset, interrupting the navigation workflow.

## Product and platform

- Product: Apple Maps / iOS
- Platform: iOS

## Environment

| Field | Value |
|---|---|
| Device | iPhone 14 Pro Max |
| OS version/build | Not recorded |
| Application | Apple Maps; version not recorded |
| Navigation state | Turn-by-turn navigation started with `Go` |
| Low Power Mode | Off |
| CarPlay | Not used |
| Charging state | Probably not charging; not confirmed |
| Auto-Lock setting | Not recorded |
| Network and location conditions | Not recorded |
| Date and time | Exact occurrence not recorded; the field account was documented on March 20, 2026 |

## Preconditions

- The device is unlocked.
- Apple Maps is available on the device.
- Low Power Mode is disabled.
- CarPlay is not in use.
- A route can be calculated and started.

## Steps to reproduce

1. Open or launch a route in Apple Maps from the originating application.
2. Tap `Go` to start turn-by-turn navigation.
3. Begin following the route with Apple Maps active.
4. Continue navigation for several minutes without manually pressing the device lock button.
5. Observe the display and device state.
6. If the lock screen appears, unlock the device and return to the map.

## Actual result

- After approximately several minutes of active navigation, the device enters the lock-screen state as though the hardware lock button had been pressed.
- The user must unlock the device again.
- After unlocking, the previously visible map/navigation state is reset.
- The behavior occurred multiple times during the same day.

## Expected result

While active turn-by-turn navigation is running in the foreground, the device should preserve the visible navigation experience and should not unexpectedly enter the lock-screen state. If the device is locked for an intentional or system-defined reason, the active route and navigation state should remain recoverable after unlocking.

## Reproducibility

Observed multiple times during one day on one iPhone 14 Pro Max. The exact number of attempts, time-to-lock, and reproduction rate were not recorded. The behavior has not yet been retested on the current OS version.

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

- The exact iOS version/build was not retained and must not be reconstructed from memory.
- The configured system Auto-Lock interval was not recorded. `Auto-Lock` refers to the setting under `Settings → Display & Brightness → Auto-Lock`, which controls how long an inactive display remains on.
- The report records that the device entered the lock-screen state; it does not assume which timer, application, framework, or OS component initiated it.
- The behavior appeared after an iOS update on the affected device, but this is only a temporal correlation. The update is not presented as a proven root cause.
- Google Maps and other navigation applications were not tested.
- The affected phone was probably not charging, but this condition was not confirmed.
- A separate recollection that automatic updates became enabled without user action is not part of this report because the earlier setting was not documented and the behavior was not independently reproduced.
- A future verification should capture the exact iOS build, Auto-Lock value, time-to-lock, charging state, route-state behavior after unlocking, and a privacy-safe video recorded by a second device.
