# UBER-DRIVER-IOS-001: Dynamic Island continues to show the driver online after the driver goes offline

> **Status:** Draft

## Summary

After the driver deliberately went offline in Uber Driver, the application itself showed the offline state, but the Uber activity in Dynamic Island continued to indicate that the driver was online. The stale status remained after the application was dismissed and removed from the iOS app switcher.

Selecting the activity reopened Uber Driver, where the driver still appeared offline. Dynamic Island and the application's primary interface therefore presented contradictory availability states.

## Product and platform

- Product: Uber Driver, used for Uber Eats delivery work
- Component: Driver availability status / Dynamic Island activity
- Platform: iOS

## Environment

| Field | Value |
|---|---|
| Device | iPhone 14 Pro Max |
| OS version | iOS 26.6, based on the owner's contemporaneous device record |
| Uber Driver version/build | Not recorded |
| Network | Not recorded |
| Environment | Production |
| Account and market | Withheld for privacy |

## Preconditions

- Uber Driver has been active and is displaying driver availability through Dynamic Island.
- The driver is online before beginning the observed sequence.

## Steps to reproduce

The following steps document the field observation. A controlled reproduction has not yet been completed.

1. Open Uber Driver while the driver is online.
2. Use the application's control to go offline.
3. Confirm that Uber Driver displays the offline state.
4. Dismiss the application.
5. Remove Uber Driver from the iOS app switcher.
6. Observe the Uber activity in Dynamic Island.
7. Select the activity to reopen Uber Driver.
8. Compare the status shown in Dynamic Island with the status shown inside the application.

## Actual result

- Uber Driver shows that the driver is offline.
- Dynamic Island continues to display an Uber activity indicating that the driver is online.
- The stale activity remains after Uber Driver is removed from the app switcher.
- Selecting the activity reopens Uber Driver, but the application still shows the offline state.

## Expected result

When the driver goes offline, the Dynamic Island activity should promptly update to the offline state or end. It should not continue to indicate that the driver is online after Uber Driver has confirmed the offline transition.

Removing the application from the app switcher is supporting context rather than the primary expectation: the availability indicator should synchronize when the driver selects the application's offline control.

## Reproducibility

Observed in real use. Exact frequency and deterministic reproducibility are not established.

The driver checked the offline state more than once during the incident, but the complete sequence was not repeated under controlled conditions.

## Severity

**Medium candidate.** Driver availability is a time-sensitive state, and contradictory status information makes it unclear whether the driver can receive new work. The incident did not confirm that the server-side account remained online or that an offer was received, missed, or assigned incorrectly.

## Priority

**To be assessed.** The duration, occurrence rate, affected versions, and relationship between the displayed activity and the authoritative account state are unknown.

## Category

Functional / State Synchronization / Dynamic Island / Driver Availability / Lifecycle

## Evidence

- The report is based on a firsthand production observation.
- No screenshot, screen recording, application log, or server-side status record is available for public inclusion.
- Account, market, earnings, offer, and location details are not required to describe the defect and are excluded.

## Investigation notes

The following are investigation areas, not confirmed causes:

- the Dynamic Island or Live Activity lifecycle may not end after the offline transition;
- the system activity may retain a cached availability state;
- the in-app status and system-level presentation may receive different state updates;
- an existing activity may survive application termination without being refreshed.

The observation proves a display-state contradiction. It does not establish that Uber's backend considered the driver online.

A future occurrence should record:

- the exact Uber Driver build and iOS build;
- the duration of the stale Dynamic Island status;
- whether reopening the application changes or ends the activity;
- whether toggling online and offline again clears it;
- whether the status survives a device restart;
- a privacy-safe screen recording showing both states without account, offer, earnings, map, or location information.

