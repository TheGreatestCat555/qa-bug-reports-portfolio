# AMAZON-FLEX-003: Package-scanner flashlight state resets between delivery stops

> **Status:** Draft

## Summary

The flashlight enabled on the package-scanning screen no longer preserves its state between delivery stops. During night deliveries, the driver must enable it again each time the scanner is opened at a new stop, adding a repeated action to the delivery workflow.

## Product and platform

- Product: Amazon Flex driver application
- Platform: iOS

## Environment

| Field | Value |
|---|---|
| Device | iPhone 14 Pro Max |
| OS version/build | Not recorded |
| Official release context | On March 21, iOS 26.3.1 was the latest standard release compatible with iPhone 14 Pro Max; released March 4, 2026. A Background Security Improvement became available March 17, but its installation was not verified. |
| Application version/build | Not recorded |
| Workflow | Multi-stop delivery block in dark conditions |
| Flashlight control | Package-scanning screen |
| Network | Not recorded |
| Date and time | Observed and documented on March 21, 2026; exact time not recorded |

## Preconditions

- An active delivery block contains at least two stops.
- Ambient lighting is low enough that the scanner flashlight is useful.
- The driver can open the package-scanning screen and enable its flashlight control.

## Steps to reproduce

1. Arrive at a delivery stop and select the control indicating that the vehicle is parked.
2. Open the package-scanning screen.
3. Enable the scanner flashlight.
4. Scan the package and complete the remaining delivery workflow.
5. Proceed to the next delivery stop.
6. Indicate that the vehicle is parked and open the package-scanning screen again.
7. Observe the flashlight state.

## Actual result

- The package-scanner flashlight is `Off` when the scanning screen is opened at the next stop.
- The driver must enable it manually again at every stop.
- The changed behavior was noticed repeatedly during the delivery block in which it was observed.

## Expected result

The package-scanner flashlight should preserve the driver's selected state between consecutive delivery stops until the driver explicitly changes it, or the application should provide and communicate a deliberate alternative behavior if the state must reset.

## Previous observed behavior

Based on long-term use of the application, enabling the scanner flashlight previously caused it to remain enabled when the package-scanning screen was opened at subsequent stops. Disabling it manually caused later scanner sessions to open with it disabled. The changed behavior was first noticed on the documented day and had not been noticed the previous day.

## Reproducibility

Observed repeatedly across multiple stops during one delivery block. The exact number of stops and measured reproduction rate were not recorded. The behavior has not yet been retested on the current application version.

## Severity

**Medium.** The issue does not block package scanning, but it adds a repetitive manual action at every stop, slows the workflow, and is especially disruptive during night deliveries when consistent illumination is required.

## Priority

**To be assessed.** The repeated workflow cost can accumulate across a route, but the affected versions, duration, and driver population are unknown.

## Category

Functional / State Management / Workflow / UX Regression

## Evidence

- Screenshots were referenced in the private source discussion but are not included because safely reviewed source files are not currently available.
- Video: Not available.
- Logs: Not available.

## Notes and limitations

- The exact application and iOS versions were not recorded.
- Release timing is based on Apple's [official security-release history](https://support.apple.com/en-ca/100100). Automatic Updates were reportedly enabled, but the installed standard build and optional background response remain unconfirmed.
- The report describes a behavioral regression relative to long-term field use; product requirements for flashlight persistence are not available.
- It is unknown whether the reset was an intentional product change, a temporary experiment, or an unintended regression.
- This report concerns only the flashlight control on the package-scanning screen. A separate flashlight control used later in the delivery-photo workflow may have independent state and is outside this report.
- Battery level, application relaunch state, memory pressure, and whether the delivery block crossed a day boundary were not recorded.
- A future verification should capture the app and OS versions, record at least five consecutive stops, note whether the app was backgrounded or relaunched, and use privacy-safe video that excludes labels, addresses, package codes, and customer data.
