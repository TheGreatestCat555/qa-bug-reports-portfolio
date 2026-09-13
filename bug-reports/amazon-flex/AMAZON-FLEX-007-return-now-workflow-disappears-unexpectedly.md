# AMAZON-FLEX-007: `Return now` workflow disappears before packages are returned to the station

> **Status:** Draft

## Summary

After the driver selects `Return now` for packages that must be returned to the station, Amazon Flex can unexpectedly lose the active return workflow. The return route and the in-application path for scanning the packages at the station may no longer be available. The failure occurs at an unpredictable time and cannot currently be reproduced on demand.

## Product and platform

- Product: Amazon Flex driver application
- Platform: iOS

## Environment

| Field | Value |
|---|---|
| Device | iPhone 14 Pro Max |
| OS version | Not recorded |
| Application version/build | Not recorded |
| Network | Not recorded |
| Return reason | Omitted; not required to describe the state-loss failure |
| Station, block, route, package, and account data | Excluded for privacy and operational safety |
| Date and time | Exact occurrences not recorded |

## Preconditions

- The driver has one or more packages that the application requires to be returned to a station.
- Amazon Flex presents a `Return now` option.

## Steps to reproduce

The issue is intermittent and no deterministic trigger is known. The observed workflow was:

1. Reach the package-return workflow in Amazon Flex.
2. Select `Return now`.
3. Confirm that the application begins the return flow and provides the route to the station.
4. Continue normal use while travelling through the return workflow.
5. Reopen or inspect Amazon Flex before completing the package return.

## Actual result

- The active return workflow disappears unexpectedly.
- The route to the return station is no longer presented as the active workflow.
- The expected in-application path for scanning the returning packages at the station may no longer be available.

## Expected result

After `Return now` is selected, the return workflow should persist until the packages are scanned and the return is completed, explicitly cancelled through a supported action, or replaced by a clearly communicated system state. If recovery is required, the application should provide a visible way to resume the pending return.

## Reproducibility

Intermittent. The behavior has been observed in real use, but the occurrence time cannot be predicted and the issue cannot currently be reproduced on demand. A precise occurrence rate was not measured.

## Severity

**High candidate.** Losing the workflow can obstruct a required operational process and remove the normal route to station navigation and return scanning. The final severity should be confirmed against the application's fallback and support procedures.

## Priority

**To be assessed.** The workflow impact is potentially high, but affected versions, occurrence rate, recovery options, and backend persistence are unknown.

## Category

Functional / Workflow / State Management / Persistence / Intermittent

## Evidence

- Screenshot: Not available in safely redacted form.
- Video: Not available.
- Logs: Not available.

Because the event occurs at an unpredictable time, continuously recording the device solely to capture it would be disproportionate. The report preserves the field observation and explicitly marks the missing telemetry.

## Notes and follow-up

- The disappearance of navigation and the return-scanning path are documented as manifestations of one lost return-workflow state, not counted as separate defects.
- This report does not claim that minimizing the application, background refresh, relaunch, a network transition, or any other specific action is a reliable trigger.
- It is not known whether the backend retained the pending return after the interface stopped presenting it.
- No claim is made that compensation, mileage, working time, package tracking, or account standing was actually lost. Those are potential product risks requiring separate evidence.
- No customer address, station code, block time, route number, package identifier, screenshot, or account information is included.
- If encountered again, useful low-effort evidence would include the approximate time, whether the application had just changed foreground state, the last visible return screen, available recovery entry points, and versions recorded after the event. Continuous screen recording is not required.

