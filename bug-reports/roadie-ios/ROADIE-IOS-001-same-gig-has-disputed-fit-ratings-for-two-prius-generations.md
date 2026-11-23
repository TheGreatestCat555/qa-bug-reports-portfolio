# ROADIE-IOS-001: The same Gig receives disputed Tight Fit and Easy Fit ratings for two Prius generations

> **Status:** Draft — capacity-classification candidate; physical fit and calculation inputs not independently verified

## Summary

Two drivers viewed the same tire-delivery Gig at approximately the same time. Roadie displayed `TIGHT FIT FOR TOYOTA PRIUS` for the user's NHW20-generation Prius and `EASY FIT FOR TOYOTA PRIUS` for a 2025 Prius. The user disputes the ranking based on the vehicles' usable cargo space.

Four screenshots confirm different fit labels on the map cards and Gig details. The detail screens share the same Support ID and item summary. They establish a vehicle-dependent classification difference, but do not by themselves prove that either vehicle's physical fit was calculated incorrectly.

## Product and platform

- Product: Roadie driver application
- Platform: iOS, identified from the supplied screenshots
- Component: Vehicle-fit estimate on the map card and Available Gig details

## Environment

| Field | Value |
|---|---|
| Devices | Two iPhones; exact models not recorded |
| OS versions | Not recorded |
| Roadie versions | Not recorded |
| Vehicle A | Toyota Prius, NHW20 generation, identified by the user; exact model year and trim not confirmed |
| Vehicle B | Toyota Prius, 2025, identified by the user; exact trim not confirmed |
| Interface language | English on both Roadie screens |
| Account context | Two drivers/devices; active vehicle records and existing Gig loads were not captured |
| Date documented | November 23, 2026 |
| Timing | Reportedly viewed simultaneously; screenshot clocks are within approximately one minute |

## Preconditions

- Both drivers can view the same available Gig.
- Each driver intends to offer with the Prius described above.
- The Gig contains tires and has vehicle-fit estimates available.

## Steps to reproduce

This is a reconstruction of the field comparison, not a controlled reproduction with all calculation inputs held constant.

1. Locate the same available tire-delivery Gig on both devices.
2. Compare its fit label on each map card.
3. Open the Available Gig details on both devices.
4. Confirm privately that the Support ID and item summary match.
5. Compare the fit labels and the displayed offering vehicle.
6. Before attempting a controlled repeat, verify each account's active vehicle year/trim and current delivery load.

## Actual result

| View | NHW20-generation Prius | 2025 Prius |
|---|---|---|
| Map card | Tight Fit | Easy Fit |
| Available Gig details | Tight Fit | Easy Fit |
| Displayed vehicle name | Toyota Prius | Toyota Prius |
| Submit Offer control | Visible | Visible |

The detail screens show matching Support IDs and the same summarized item count, total-weight limit, and maximum-dimension limit. The displayed completion deadlines differ by one minute, so the images are not treated as a precisely synchronized capture.

The user reports that the older vehicle has more usable cargo space and considers the warning counterintuitive. No measurement or loading trial for this particular cargo was supplied.

## Expected result

Fit estimates should reflect the correctly configured vehicle and relevant cargo/load constraints. If both vehicles can accommodate the same items under equivalent conditions, the older vehicle should not receive a more restrictive estimate solely because of an incorrect vehicle record or capacity model.

Different vehicles or different existing loads can legitimately produce different labels. Identical ratings are not asserted as an unconditional requirement. This report requests validation of the disputed ranking rather than assuming that the same model name means the same available space.

## Reproducibility

One comparative observation of one Gig, documented across four screenshots. Both the map and detail views repeat the classification for their respective device. This is not four independent reproductions; no wider failure rate is known.

## Severity

**Medium candidate, conditional on validation.** An inaccurate warning could discourage a driver from offering for suitable work or mislead loading decisions. Both screens still show `SUBMIT OFFER`; no blocked submission, rejected application, failed loading attempt, missed earnings, or proven matching disadvantage was recorded.

## Priority

**To be assessed.** The fit calculations and account-specific inputs need checking before assigning remediation priority.

## Category

Functional Candidate / Vehicle Capacity / Data Quality / Fit Classification / Cross-Account Comparison

## Evidence and privacy

- Firsthand description and four screenshots reviewed: a map card and a detail screen for each vehicle context.
- The matching Support ID was checked privately; the identifier, merchant, payment, route, precise locations, and original screenshots are excluded from the public repository.
- The screenshots show the model name but not configured model years or trims. The year/generation association comes from the user's description, not the visible label alone.
- No vehicle-profile captures, full per-item measurements, fit-help contents, calculation trace, or loading-test evidence were provided.

## Notes and follow-up

1. Verify the active vehicle record on each account, including year, trim, and any capacity setting.
2. Compare existing assigned loads and other inputs used by the fit estimator.
3. Inspect full item dimensions, quantity, and packaging rather than relying on an aggregate maximum dimension.
4. Compare usable loading geometry and hatch openings under the seat configuration actually assumed by Roadie; document a safe loading trial if available.
5. Check whether the fit-help control explains the warning and whether the estimate changes when verified inputs are corrected.

Catalog cargo volumes from different markets, trims, or measurement methods do not prove physical fit for this load. The earlier discussion's vehicle-volume comparisons and suggested algorithm causes are not adopted as verified findings. No internal Roadie capacity source or specific root cause is established.

Roadie's published [Gig and vehicle sizing guide](https://www.roadie.com/blog/2024/05/a-quick-guide-to-roadie-gig-and-delivery-vehicle-sizes-ent) states that size selection is one of multiple matching variables. It does not establish that this warning reduced either driver's selection probability in the observed case.
