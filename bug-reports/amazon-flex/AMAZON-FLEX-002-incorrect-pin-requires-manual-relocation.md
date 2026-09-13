# AMAZON-FLEX-002: Incorrect apartment delivery pin requires manual relocation before completion

> **Status:** Draft

## Summary

During an apartment-complex delivery, the initial delivery pin points to the wrong location and the intended building is not highlighted on the map. The driver must locate the correct building independently and manually relocate the delivery pin before the application allows the delivery workflow to continue.

## Product and platform

- Product: Amazon Flex driver application
- Platform: iOS

## Environment

| Field | Value |
|---|---|
| Device | iPhone 14 Pro Max |
| OS version | Not recorded |
| Official release context | On the March 18 documentation date, iOS 26.3.1 was the latest standard release compatible with iPhone 14 Pro Max; released March 4, 2026. A Background Security Improvement became available March 17, but its installation was not verified. |
| Application version/build | Not recorded |
| Browser | Not applicable |
| Network | Not recorded |
| Account state | Active delivery block; other details not recorded |
| Region and language | United States; application language not recorded |
| Date and time | Exact occurrence not recorded; the field account was shared on March 18, 2026 |

## Preconditions

- An active delivery stop is located in an apartment complex.
- The delivery details identify an apartment, but the map does not provide a reliable visual association between that apartment and its building.
- The initial delivery pin does not correspond to the actual delivery building.

## Steps to reproduce

The data conditions cannot currently be reproduced on demand. The observed field sequence was:

1. Open the apartment-complex delivery stop in the Amazon Flex application.
2. View the initial delivery location on the in-app map.
3. Attempt to identify the intended building using the pin, building highlighting, and available building or apartment labels.
4. Locate the correct building independently.
5. Move the delivery pin from its initial location to the correct location.
6. Observe the pin or location-state color change.
7. Continue the delivery workflow, take the delivery photo, and confirm delivery.

## Actual result

- The initial delivery pin pointed to the wrong location.
- The intended building had no blue map highlight.
- Building or apartment labels were not available for every building shown on the map.
- The driver had to search the complex independently and manually relocate the pin.
- The location state changed from orange to green after relocation, after which the application allowed the workflow to continue.

## Expected result

The initial delivery pin and any building highlight should identify the building associated with the apartment in the delivery details. The driver should be able to navigate to the correct location and continue the delivery without first correcting stored location data manually.

## Reproducibility

Observed in one documented field delivery. Exact trigger, recurrence rate, affected map data, and current product status have not been verified.

## Severity

**Medium.** The delivery could be completed after manual correction, but the defect increased search time and created a risk of navigation to or delivery at the wrong building. Severity could be higher in complexes where the correct building cannot be identified independently.

## Priority

**To be assessed.** User impact is meaningful, but frequency and the number of affected apartment complexes are unknown.

## Category

Functional / Navigation / Map Data / UX

## Evidence

- Screenshots existed in the private source discussion but are not included because they contain precise delivery-location information and no safely redacted copies are currently available.
- Video: Not available.
- Logs: Not available.

## Notes and follow-up

- The precise address, apartment number, building identifier, route details, customer information, and account information have been intentionally omitted.
- This report records observed UI behavior without attributing the underlying coordinates or labels to a particular internal or third-party data source.
- Missing labels alone are not asserted as an independent defect because it is unknown whether label data exists for every building at the observed zoom level.
- The meaning of the orange and green states was inferred from the workflow transition; the application wording and accessibility treatment of those states were not recorded.
- This manifestation differs from `AMAZON-FLEX-001`: manual pin relocation was available here and allowed the workflow to finish, whereas the earlier report documents a case in which location correction was unavailable and correct completion was blocked.
- A future verification session should capture the application and OS versions, map zoom level, safely redacted before-and-after screenshots, displayed instructions, correction controls, and whether the corrected location persists for later deliveries.
- Release timing is based on Apple's [official security-release history](https://support.apple.com/en-ca/100100). It is not proof of the installed build or of a relationship between an update and the map behavior.
