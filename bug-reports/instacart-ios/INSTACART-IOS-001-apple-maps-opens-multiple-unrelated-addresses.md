# INSTACART-IOS-001: Apple Maps opens multiple unrelated addresses instead of the customer destination

> **Status:** Draft

## Summary

After shopping is completed in Instacart Shopper, selecting the navigation control for delivery opens Apple Maps with approximately five to eight unrelated addresses instead of one route destination matching the customer delivery address. The handoff therefore does not provide a usable or trustworthy delivery route.

## Product and platform

- Source product: Instacart Shopper
- Destination product: Apple Maps
- Component: External-navigation handoff after shopping completion
- Platform: iOS

## Environment

| Field | Value |
|---|---|
| Device | iPhone 14 Pro Max |
| OS version | iOS 26.5, as reported in the field account |
| Instacart Shopper version/build | Not recorded |
| Apple Maps version/build | Not recorded |
| Navigation provider | Apple Maps |
| Network and location conditions | Not recorded |
| Date documented | June 18, 2026 |

## Preconditions

- An Instacart Shopper order has been accepted and shopping has been completed.
- The workflow has advanced to customer delivery.
- Apple Maps is selected or configured as the navigation provider.
- The delivery-navigation control is available in Instacart Shopper.

## Steps to reproduce

These steps describe the recorded field workflow; repeatability was not measured:

1. Complete shopping for an Instacart Shopper order.
2. Advance to the customer-delivery stage.
3. Select the in-app navigation control intended to open the delivery destination.
4. Observe the destination information displayed in Apple Maps.

## Actual result

- Apple Maps opens a list containing approximately five to eight addresses.
- The listed addresses are unrelated to the customer delivery destination shown in Instacart Shopper.
- A single route to the customer address is not prepared.
- The driver cannot safely rely on the in-app navigation handoff.

## Expected result

Selecting delivery navigation should transfer one customer destination to the configured navigation provider. Apple Maps should display or prepare a route to that same destination rather than presenting multiple unrelated addresses.

## Reproducibility

A field occurrence was recorded, but the source does not provide controlled attempts, a measured rate, or a confirmed trigger beyond the normal post-shopping delivery workflow.

## Severity

**High candidate.** The failure removes a trusted route to the customer, can send a driver toward an incorrect location if one of the results is selected without verification, and can create delay and driving distraction. No collision, physical incident, privacy disclosure, or completed delivery to a wrong address is asserted.

## Priority

**To be assessed.** The operational impact is substantial when the failure occurs, but frequency, affected population, geographic scope, application-version range, and available recovery paths are unknown.

## Category

Functional / Cross-Application Integration / Navigation Handoff / Destination Data / Workflow

## Workaround

No verified workaround was recorded. Manually checking and entering the delivery address may be a possible recovery path, but it was not documented as part of the observed occurrence.

## Evidence

- Firsthand verbal field account: available.
- Screen recording: reported as available, but excluded from the public repository because it may expose customer addresses, routes, order details, or precise location.
- Screenshots: potentially available, but not included for the same privacy reasons.
- Outgoing navigation URL or payload, application logs, Apple Maps diagnostics, and network traces: not available.

## Notes and limitations

- `Unrelated addresses` describes the user-visible mismatch. Their selection mechanism is unknown, so this report does not call them technically random.
- The observation does not establish whether Instacart Shopper sent multiple or malformed destination values, Apple Maps interpreted the handoff incorrectly, a search-results view opened instead of a route, or stale state was reused.
- The responsible product cannot be assigned from the available evidence.
- A future verification should capture a privacy-safe recording from before the navigation control is selected, the destination shown in Instacart, the Apple Maps result, application builds, outgoing navigation data when safely accessible, manual entry of the same address, and comparison with another navigation provider.
