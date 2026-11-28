# AMAZON-FLEX-011: Delivery QR scanner gives no result until the app is restarted

> **Status:** Draft

## Summary

During delivery stops, Amazon Flex intermittently fails to respond when the driver scans a package QR code. There is no recognition result or error, and the delivery cannot proceed through the normal scan step until the application is restarted. The driver reports several affected stops in every recently worked block over approximately the last four or five days.

## Product and platform

- Product: Amazon Flex driver application
- Platform: iOS
- Component: Package QR scanning after confirming the vehicle is parked at a delivery stop

## Environment

| Field | Value |
|---|---|
| Device | iPhone 14 Pro Max |
| Installed OS | iOS 26.6.1, explicitly reported by the driver |
| Application version | 2.617.206, shown on the supplied App Store page; driver reports the app is updated |
| Application version evidence | Store page shows Open and version 2.617.206; an in-app installed-build screen was not supplied |
| Network | Poor mobile connectivity is frequent during the workflow; connectivity at each individual failure was not measured |
| Date documented | November 27, 2026 |
| Observation period | Approximately November 22–27, 2026; onset recalled as four or five days before documentation |

The driver has not upgraded to iOS 27. The report retains the explicitly supplied installed OS rather than replacing it with a current-release estimate. No causal connection between the older OS and this defect is established.

## Preconditions

- An active delivery block is in progress.
- Initial package scanning at the station has worked normally in the affected delivery workflow.
- The driver has reached a delivery stop and confirmed that the vehicle is parked.
- A package must be scanned before delivery can continue.

## Steps to reproduce

The triggering condition is unknown. These steps describe the repeatedly observed field workflow, not a guaranteed way to cause the failure.

1. Start a delivery block and complete the station scanning workflow.
2. Travel to a delivery stop and select the control confirming that the vehicle is parked.
3. Open the required package scanner.
4. Present the package QR code to the camera.
5. If scanning produces no result, observe whether any error or recovery action appears.
6. Restart Amazon Flex and attempt to resume package scanning for the delivery.

## Actual result

- At affected stops, presenting the QR code produces no visible scan result.
- No error message or error code explains the lack of progress.
- The driver cannot proceed with delivery through this required step and has not found another usable completion path in this state.
- The driver reports needing to restart the application to resume the workflow.
- Reopening the app is especially time-consuming where connectivity is poor.

The observation does not establish whether QR decoding fails, a recognized result is not displayed, or a subsequent operation is waiting silently.

## Expected result

A valid package scan should identify the package and allow the delivery flow to continue. If scanning or validation cannot finish, the app should communicate the failure or waiting state and provide an appropriate retry/recovery path, without requiring an unexplained restart.

## Reproducibility

Repeated across every recently worked block in the reported four-to-five-day period, typically at three or four stops per block and sometimes more. The driver does not work every day. Block count, total stop count, exact failure rate, and restart success rate were not measured. The driver’s prediction that it would also happen on unworked days is not counted as an observation.

## Severity

**High candidate.** A required delivery step is blocked until the application is restarted, repeatedly interrupting active work. Delays are reported but not timed; no lost package, missed delivery, earnings impact, or server-side data loss is asserted.

## Priority

**To be assessed.** Repetition across blocks and recovery cost support investigation, but wider prevalence and affected build range are unknown.

## Category

Functional / QR Scanning / Delivery Workflow / Error Communication / Recovery

## Workaround

Restart Amazon Flex and return to the affected delivery. This is the driver's reported recovery, not a controlled reliability test. Poor connectivity can make this recovery slow.

## Evidence and limitations

- Firsthand description of recurrence, lack of scanner feedback, and restart recovery.
- Supplied App Store screenshot shows Amazon Flex 2.617.206 and an Open control. It documents version context, not the scanner failure or an independently read installed build.
- No failure recording, scanner logs, QR contents, network measurements, or precise timing is available.
- Station identity, customer details, package identifiers, route information, and private source links are excluded.

## Related observations and follow-up

[AMAZON-FLEX-012](AMAZON-FLEX-012-station-scanner-shows-one-for-every-package.md) records a separate station-scanner episode in which packages were recognized but all displayed 1. No common cause is established. The existing [flashlight-state report](AMAZON-FLEX-003-scanner-flashlight-state-resets-between-stops.md) concerns a different behavior and does not duplicate this failure.

Record QR detection feedback, validation/loading state, network status, and lifecycle events before and after a restart. Compare scans at the station and delivery stops. A network dependency, scanner-session defect, or OS compatibility issue is a diagnostic possibility, not a verified cause.
