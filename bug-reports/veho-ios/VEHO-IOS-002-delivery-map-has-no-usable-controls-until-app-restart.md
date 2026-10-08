# VEHO-IOS-002: Delivery map has no usable workflow controls until the app is restarted

> **Status:** Draft

## Summary

During an active delivery route, Veho Driver occasionally displayed a map and stop marker without usable controls to continue or leave the delivery workflow. Selecting the marker opened a package screen, but the scan flow did not proceed and returning led to the same map. Force-closing and reopening the application allowed work to continue.

## Product and platform

- Product: Veho Driver
- Component: Active delivery stop, map navigation, and package scanning
- Platform: iOS

## Environment

| Field | Value |
|---|---|
| Device | iPhone 14 Pro Max |
| OS version | Not independently verified; the contemporaneous report lists iOS 26.6.2 |
| Installed application version | Not recorded; automatic updates were enabled according to the user |
| Version mentioned in the contemporaneous report | 3.5.0, described as the store version; installation on the affected device was not verified |
| Network | Not recorded |
| Date documented in the observation | October 7, 2026 |
| Exact occurrence time | Not recorded |

## Preconditions

- The driver is signed in and has an active delivery route.
- A delivery-stop map is open.

## Steps to reproduce

The issue is intermittent and its initial trigger is unknown. The actions after entering the affected state were reported directly.

1. Open a delivery stop during an active route.
2. If the map appears without usable Back, Next, or continuation controls, select the stop marker.
3. Observe the package screen, including the previous-delivery image and `Scan package` control.
4. Attempt to continue the package-scanning workflow.
5. Leave that screen and observe the delivery map again.
6. Force-close Veho Driver.
7. Reopen it and check whether the delivery workflow can continue.

## Actual result

The initial map offered no usable navigation or continuation controls. The stop marker could still be selected. It opened a package screen displaying a previous-delivery image and a scan control, but the user could not proceed through that workflow. Returning led back to the same blocked map.

Restarting the application restored a usable delivery flow in the reported incidents.

## Expected result

An active delivery stop should provide a usable route to the required scan and delivery-confirmation steps, or a way back to the route. If the stop cannot load, the application should present an explicit recoverable error rather than a map with no workable exit or continuation.

## Reproducibility

Occasional and observed more than once during delivery work. No exact count or success rate was recorded.

## Severity

**High candidate.** The issue blocks the current delivery workflow until the application is restarted, interrupting active work. Delay was not measured, and no failed delivery or financial loss is established.

## Priority

**To be assessed.** The workflow impact warrants investigation, but affected builds, prevalence, and the initial trigger remain unknown.

## Category

Functional / Delivery Workflow / Navigation / Package Scanning / State Management / Recovery

## Workaround

Force-close the application and reopen it. This restored the workflow according to the user; a broader reliability test has not been performed.

## Evidence and limitations

- Firsthand description and source screenshots of the map and package screen.
- Original screenshots are withheld because delivery locations and operational details may be visible.
- Stop numbers, addresses, customer data, account data, and private conversation links are excluded.
- There is no controlled recording of the failed scan action or restart recovery.
- The previous-delivery image is context, not evidence that another customer's image was displayed incorrectly.
- Network state, loading failures, and a specific navigation or synchronization cause have not been established.

## Follow-up verification

Capture the transition into the affected state on a privacy-safe test route. Check map controls, marker navigation, scan activation, and return navigation. Record the installed build, route-restoration behavior, network state, and timestamps before and after restarting.
