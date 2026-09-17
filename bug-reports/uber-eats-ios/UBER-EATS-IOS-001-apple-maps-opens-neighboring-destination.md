# UBER-EATS-IOS-001: Apple Maps opens a neighboring destination after navigation is launched from Uber Eats

> **Status:** Draft

## Summary

When external navigation is launched from an Uber Eats delivery workflow, the destination displayed and reached in Apple Maps can differ from the delivery address shown in Uber Eats. In the documented occurrence, Apple Maps used a neighboring street number on the same street, causing the driver to arrive at the wrong residence.

## Product and platform

- Source product: Uber Eats driver delivery workflow
- Destination product: Apple Maps
- Platform: iOS

## Environment

| Field | Value |
|---|---|
| Device | iPhone; exact model not recorded in this source |
| OS version/build | Not recorded |
| Uber Eats version | Not recorded |
| Apple Maps version | Not recorded |
| Navigation provider selected | Apple Maps |
| Network conditions | Not recorded |
| Date observed | May 1, 2026 |

## Preconditions

- An Uber Eats delivery is active.
- The delivery workflow displays a destination address.
- Apple Maps is available as an external navigation option.

## Steps to reproduce

The issue is intermittent, so this sequence describes the observed workflow rather than a guaranteed reproduction:

1. Accept an Uber Eats delivery order.
2. Open the delivery route in the Uber Eats driver workflow.
3. Start external navigation and select Apple Maps.
4. Follow Apple Maps to the displayed destination.
5. Compare the destination shown in Apple Maps with the delivery address shown in Uber Eats.

## Actual result

- Apple Maps displays a different street number from the delivery address shown in Uber Eats.
- The street number corresponds to a neighboring residence on the same street.
- The generated route ends at that neighboring residence.
- The mismatch becomes apparent when the driver returns to Uber Eats and compares the two addresses.

For privacy, this report labels the values generically:

- Uber Eats: `Delivery address A`
- Apple Maps: `Neighboring address B`

## Expected result

Apple Maps should receive and navigate to the same destination selected in Uber Eats. If only approximate coordinates can be transferred, the handoff should not silently present a neighboring postal address as though it were the exact delivery destination.

## Reproducibility

Intermittent and recurring during real delivery work. The behavior was described as occurring frequently, but no controlled sample or occurrence count was recorded. An informal estimate mentioned in the field account is intentionally not treated as a measured reproduction rate.

## Severity

**High candidate.** The mismatch can direct a driver to the wrong residence, delay the delivery, require cross-checking two applications, and create a safety or privacy concern when the driver approaches an uninvolved property. No physical incident or completed delivery to the wrong customer is asserted.

## Priority

**To be assessed.** The user impact is substantial when the mismatch occurs, but the affected population, exact frequency, geographic scope, and responsible component are unknown.

## Category

Functional / Cross-Application Integration / Navigation Handoff / Data Consistency / Map Addressing

## Evidence

- The field account included a concrete side-by-side address mismatch.
- Original screenshots and literal location values are excluded because they contain a real delivery address and location information.
- Outgoing handoff payload, application logs, and map/geocoding diagnostics are not available.

## Notes and limitations

- The observation proves a user-visible mismatch between Uber Eats and Apple Maps; it does not establish which product owns the defect.
- It is unknown whether Uber Eats transferred a postal address, geographic coordinates, a map pin, or another destination representation.
- Possible explanations such as incorrect handoff data, coordinate-to-address conversion, map-data error, or a delivery-pin mismatch remain unverified hypotheses.
- Google Maps and other navigation providers were not compared in a controlled test.
- The exact device model, OS build, application versions, route conditions, and network state were not retained.
- A future verification should capture privacy-safe screen recordings, the destination before and after handoff, the result of entering the same address manually in Apple Maps, comparison with another navigation provider, and—if available without exposing customer data—the outgoing navigation URL or activity payload.
