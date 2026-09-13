# AMAZON-FLEX-005: Delivery urgency status is missing from the itinerary list after being added to the map

> **Status:** Draft

## Summary

Delivery stops approaching or exceeding their displayed delivery deadline are identified by urgency indicators on the route map, but the corresponding `Due soon` and `Late` status labels are no longer shown in the scrollable itinerary list. A driver reviewing stops in list form therefore cannot distinguish urgent stops without switching back to the map or comparing each displayed deadline manually.

## Product and platform

- Product: Amazon Flex driver application
- Platform: iOS

## Environment

| Field | Value |
|---|---|
| Device | iPhone 14 Pro Max |
| OS version/build | Not recorded |
| Official release context | On the March 30 documentation date, iOS 26.4 was the latest standard release compatible with iPhone 14 Pro Max; released March 24, 2026. Automatic Updates were reportedly enabled, but actual installation was not verified. |
| Application version/build | Not recorded |
| Workflow | Active multi-stop delivery block |
| Views compared | Route map and scrollable itinerary list |
| Network | Not recorded |
| Date and time | Documented on March 30, 2026; exact observation time not recorded |

## Preconditions

- An active route contains multiple delivery stops.
- At least one stop is approaching or has passed its displayed delivery deadline.
- Both the route map and itinerary list are available.

## Steps to reproduce

1. Open an active multi-stop route in Amazon Flex.
2. View the route map when one or more stops are approaching their displayed delivery deadline.
3. Observe the urgency indicator shown on the relevant map marker.
4. Open the scrollable itinerary list for the same route.
5. Locate the same stop and inspect the status information shown in its list row.
6. Repeat the comparison for a stop that has passed its displayed deadline, if available.

## Actual result

- The route map displays a visual urgency indicator on affected stop markers.
- The itinerary list displays the stop's expected-delivery time but does not show the previously observed `Due soon` or `Late` status label.
- Urgency is therefore communicated differently across two views of the same route.
- Determining priority from the list requires manual comparison of individual times or returning to the map.

## Expected result

Urgency information for a stop should remain clear and consistent across the route map and itinerary list. Adding a map indicator should not remove an equivalent accessible status from the list. Stops approaching or exceeding their displayed deadline should retain a prominent text or visual state in both views.

## Previous observed behavior

Based on repeated field use before the interface change, the itinerary list previously displayed a yellow `Due soon` state for stops approaching their deadline and a red `Late` state after the deadline passed. The route map did not previously provide the newly observed clock-style marker indicator.

## Reproducibility

Observed in one documented route after an apparent interface change. The number of affected stops, rollout scope, current product status, and behavior on other devices or platforms have not been verified.

## Severity

**Medium.** The route remains usable, but removing urgency status from the list makes time-sensitive stop prioritization less efficient and increases the risk that a driver overlooks a stop requiring attention while reviewing the itinerary.

## Priority

**To be assessed.** The issue affects an active delivery workflow, but the rollout scope, accessibility impact, and rate of resulting late deliveries are unknown.

## Category

UX Regression / Information Architecture / Cross-View Consistency / Time-Critical Status

## Evidence

- Two screenshots comparing the map and itinerary views were referenced in the private source discussion.
- The screenshots are not included publicly because a safely redacted copy has not been prepared and delivery-route data may be visible.
- Video: Not available.
- Logs: Not available.

## Notes and limitations

- Exact application and iOS versions were not recorded.
- Release timing is based on Apple's [official security-release history](https://support.apple.com/en-ca/100100). The documentation date is not necessarily the exact occurrence date, and proximity to the March 24 release does not establish causation.
- The report describes a regression relative to long-term field use; internal product requirements and rollout notes are unavailable.
- It is unknown whether the changed presentation is permanent, an experiment, or an unintended regression.
- Some displayed stop deadlines reportedly extend beyond the scheduled block end. That is a separate scheduling or data-consistency concern and is not asserted as part of this report.
- A previously observed late-delivery prompt asking the driver to confirm whether the customer still wanted the delivery was also reported as absent. Because its trigger conditions and requirement are not verified, it is retained as an adjacent observation rather than included in the reproduction result.
- No claim is made about company intent, performance metrics, support policy, or the implementation cause.
- A future verification should record the app and OS versions, compare the same stops in both views, test `Due soon` and `Late` states separately, inspect accessibility labels, and capture privacy-safe evidence with all addresses, names, stop identifiers, and route geometry redacted.
