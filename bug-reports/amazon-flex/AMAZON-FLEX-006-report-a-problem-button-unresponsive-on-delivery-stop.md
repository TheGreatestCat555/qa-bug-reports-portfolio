# AMAZON-FLEX-006: `Report a problem` button is unresponsive on a delivery-stop screen

> **Status:** Draft

## Summary

On an active delivery-stop screen, selecting the `Report a problem` control produces no visible response. The problem-category list does not open, no error or loading state appears, and reopening the stop or restarting the application does not restore the control. In the documented occurrence, this prevented the driver from using the in-app workflow to report a dog-related safety concern.

## Product and platform

- Product: Amazon Flex driver application
- Platform: iOS

## Environment

| Field | Value |
|---|---|
| Device | iPhone 14 Pro Max |
| OS version/build | Not recorded |
| Application version/build | Not recorded |
| Workflow | Active route; individual delivery-stop screen |
| Intended report type | Dog-related safety concern |
| Network | Not recorded |
| Date and time | Documented on April 6, 2026; exact occurrence time not recorded |

## Preconditions

- An active route is in progress.
- An individual delivery stop is open.
- The `Report a problem` control is visible near the bottom of the stop screen.

## Steps to reproduce

The failure was repeatedly observed on one delivery stop. Applicability to other stops has not been verified.

1. Open the affected stop in an active Amazon Flex route.
2. Scroll to the `Report a problem` control.
3. Select the control.
4. Observe the screen response.
5. Navigate back, reopen the same stop, and select the control again.
6. Restart Amazon Flex, return to the same stop, and retry the control.

## Actual result

- Selecting `Report a problem` produces no visible response.
- The list of reportable problem or safety categories does not open.
- No error message, loading state, or disabled-state explanation is displayed.
- Navigating back and reopening the stop does not resolve the failure.
- Restarting the application does not resolve the failure for the affected stop.

## Expected result

Selecting `Report a problem` should open the available reporting categories or provide a clear error and an alternative reporting path. A safety-reporting control should not fail silently during an active delivery.

## Reproducibility

Repeated on one documented delivery stop, including after reopening the stop and restarting the application. It has not been established whether the issue affects other stops, routes, accounts, devices, or the current application version.

## Severity

**High candidate.** The defect blocks an in-app safety-reporting workflow during an active delivery. The observed route could continue, but the driver could not submit the intended dog-related concern through the visible control. The final severity should be reassessed after confirming alternative reporting paths and rollout scope.

## Priority

**To be assessed.** Silent failure of a safety-related control warrants timely investigation, but frequency and affected population are unknown.

## Category

Functional / Input Handling / Safety Reporting / Error Handling

## Evidence

- One screenshot showing the affected delivery-stop screen and control was referenced in the private source discussion.
- The screenshot is not included publicly because a safely redacted copy has not been prepared and stop or route data may be visible.
- Video: Not available.
- Logs: Not available.

## Notes and limitations

- Customer, address, route, stop, package, account, and precise location information are intentionally excluded.
- Exact application and iOS versions were not recorded.
- The intended dog-related report is mentioned only to establish workflow impact; no details about a customer, animal, property, or incident are published.
- The report does not claim that every stop exposes the failure. The original observation explicitly allowed that it might be specific to the affected stop.
- It is unknown whether the control failed locally, a destination screen failed to load, or a backend request was rejected; no internal cause is asserted.
- It is unknown whether support contact, a different screen, or a later workflow step provided an alternative way to submit the same concern.
- A future verification should record the app and OS versions, connectivity, tap feedback, behavior across multiple stops, accessibility state, recovery attempts, and privacy-safe screen recording.
