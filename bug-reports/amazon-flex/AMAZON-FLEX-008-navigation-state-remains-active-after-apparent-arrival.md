# AMAZON-FLEX-008: Navigation remains in route-recalculation state after apparent arrival

> **Status:** Draft — observation-based candidate; arrival and location accuracy were not independently verified.

## Summary

At an apparent delivery destination, the Amazon Flex map can continue to display `Recalculating route` and an estimated one minute remaining instead of transitioning clearly from navigation to the delivery workflow. The visible driver position, numbered stop marker, and parking indicators can make the current state difficult to interpret.

## Product and platform

- Product: Amazon Flex driver application
- Platform: iOS

## Environment

| Field | Value |
|---|---|
| Device | iPhone 14 Pro Max |
| iOS version | 26.3.1, reported for the source session |
| Application version/build | Not recorded |
| Network | LTE, reported for the source session |
| Route, address, stop, package, and account data | Excluded |
| Date and time | Historical screenshot sequence; exact occurrence time not published |

## Preconditions

- An active Amazon Flex delivery route is in progress.
- Navigation to an individual delivery stop is open.

## Observed sequence

1. Navigate to a delivery destination in Amazon Flex.
2. Stop at the location believed to be the destination.
3. Inspect the map and delivery-state interface.

## Actual result

- The interface displays `Recalculating route`.
- The estimated time remains at approximately one minute.
- The screen does not clearly communicate that the driver has arrived or provide a consistent transition to the delivery state.
- The visible current-position indicator, numbered stop marker, and multiple parking indicators produce an ambiguous arrival state.

## Expected result

When the application has sufficient location confidence that the driver reached the destination, it should transition to the appropriate delivery state. If it does not have sufficient confidence, it should clearly explain the remaining distance or location discrepancy instead of presenting an ambiguous recalculation state.

## Reproducibility

Observed in one documented screenshot sequence. Not reproduced on demand.

## Severity

**Medium candidate.** Ambiguous arrival state can delay the delivery workflow and require additional navigation or location checking. No failed or incorrect delivery was established by this observation.

## Priority

**To be assessed.** The frequency, GPS accuracy, geofence state, route geometry, and affected build are unknown.

## Category

Functional / Navigation / Arrival State / Cross-View Consistency / UX

## Evidence

- Source screenshots exist privately but are not included because they expose customer, address, route, stop, package, or location information.
- No safely redacted evidence is currently available.
- Logs: Not available.

## Notes and limitations

- Apparent physical arrival does not prove that the device GPS position was inside the configured delivery geofence.
- A numbered stop marker differing from the current-position indicator can result from GPS error, map data, destination placement, or route recalculation; no cause is assigned.
- Parking indicators are contextual map data and are not independently treated as a defect.
- This report does not claim that package completion was blocked.
- The report records an inconsistent or unclear visible state rather than asserting a backend geofence failure.

