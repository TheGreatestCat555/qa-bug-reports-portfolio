# APPLE-MAPS-IOS-002: Active route terminates after network connection is lost

> **Status:** Draft

## Summary

During active turn-by-turn navigation in Apple Maps, complete loss of the internet connection can terminate the active route instead of preserving the already displayed route. The navigation interface disappears and only the destination remains on the map, resembling the result of manually ending navigation.

## Product and platform

- Product: Apple Maps / iOS
- Platform: iOS

## Environment

| Field | Value |
|---|---|
| Device | iPhone 14 Pro Max |
| OS version/build | Not recorded |
| Application | Apple Maps; version not recorded |
| Navigation state | Active turn-by-turn driving navigation |
| Low Power Mode | Off |
| CarPlay | Not used |
| Charging state | Probably not charging; not confirmed |
| Network transition | Internet connection became completely unavailable during travel |
| Offline Maps configuration | Not recorded |
| Date and time | Exact occurrence not recorded; the field account was documented on March 20–21, 2026 |

## Preconditions

- Apple Maps has calculated a route.
- Turn-by-turn navigation has been started with `Go`.
- Route guidance, ETA, maneuver instructions, and the route line are visible.
- The device initially has an internet connection.

## Steps to reproduce

The connection-loss condition was encountered during real travel and was not triggered in a controlled test. The observed sequence was:

1. Start turn-by-turn navigation in Apple Maps.
2. Follow the active route while the navigation interface is visible.
3. Continue into an area where the internet connection becomes completely unavailable.
4. Observe the active navigation state after connectivity is lost.

## Actual result

- The active navigation interface disappears.
- The route line, ETA, and maneuver guidance are no longer shown.
- Only the destination point remains visible on the map.
- The resulting state resembles manually selecting `End` for the active route.

## Expected result

A temporary loss of connectivity should not silently terminate an already active route. Apple Maps should preserve usable cached route guidance where supported, or clearly communicate any offline limitation while retaining enough state for the user to understand and recover the navigation session.

## Reproducibility

Observed a few times during one day when internet connectivity was lost during real travel. The number of connection-loss events was not counted, and it is unknown whether the issue occurred on every complete network loss. The condition has not been reproduced in a controlled test.

## Severity

**High.** The issue removes active guidance during travel, can cause missed turns and delivery delays, and may distract the user while attempting to recover the route. No accident or physical harm is asserted.

## Priority

**To be assessed.** Impact is substantial when it occurs, but reproducibility, offline-map state, geographic coverage, and affected OS range are unknown.

## Category

Functional / Navigation / Network Resilience / State Management

## Evidence

- Screenshot or video of the transition: Not available.
- Network logs: Not available.
- Exact connectivity state and radio transition logs: Not available.

## Notes and limitations

- The exact iOS version/build was not retained.
- The report describes observed UI state and does not assume that the route was deleted from storage or that Apple Maps internally invoked the same action as the `End` control.
- It is unknown whether Offline Maps had been downloaded for the affected area. The expected result therefore does not claim that full offline rerouting or live traffic information must remain available.
- It is unknown whether GPS remained available during the network interruption.
- The connection loss occurred naturally during work; Airplane Mode and controlled network conditioning were not tested.
- Google Maps and other navigation applications were not tested.
- The issue appeared after a recent iOS update on the affected device, but the update is not presented as a proven root cause.
- A future verification should record Offline Maps coverage, exact iOS build, cellular/Wi-Fi state, GPS availability, the loss and restoration timestamps, and a privacy-safe video that hides the destination and route.
