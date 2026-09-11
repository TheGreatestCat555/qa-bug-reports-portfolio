# AMAZON-FLEX-001: Delivery cannot be completed at the correct apartment when map location states disagree

> **Status:** Draft

## Summary

During an apartment-complex delivery, the highlighted building, navigation destination, delivery confirmation zone, and actual apartment location can refer to different buildings. When manual location correction is unavailable, the driver cannot complete delivery at the correct door through the normal in-app workflow.

## Product and platform

- Product: Amazon Flex driver application
- Platform: iOS

## Environment

| Field | Value |
|---|---|
| Device | iPhone 14 Pro Max |
| OS version | Not recorded; the behavior was observed over an extended period while the application and OS received updates |
| Application version/build | Not recorded |
| Browser | Not applicable |
| Network | Not recorded |
| Account state | Active delivery block; other details not recorded |
| Region and language | United States; application language not recorded |
| Date and time | Exact occurrence not recorded; the detailed field account was documented on March 12, 2026 |

## Preconditions

- An active delivery stop is located in an apartment complex.
- The apartment address or unit information is available in the delivery details.
- The application's stored delivery/confirmation location does not correspond to the actual apartment location.
- Manual correction of the stored location is unavailable in the observed case.

## Steps to reproduce

The exact data conditions cannot currently be reproduced on demand. The observed field sequence was:

1. Open an active apartment-complex delivery stop in the Amazon Flex application.
2. Follow the in-app navigation destination.
3. Observe the building highlighted in blue and the stop/location marker shown on the map.
4. Compare those map references with the apartment information in the delivery details.
5. Locate the actual apartment manually within the complex.
6. Attempt to complete the delivery at the correct apartment door.
7. Attempt to correct or move the delivery location when the application does not recognize the correct door as an allowed confirmation location.

## Actual result

- The blue-highlighted building indicated an office or administrative building.
- Another map marker referred to a different building.
- The apartment specified in the delivery details was physically located elsewhere in the complex.
- In-app navigation led to the incorrect stored location.
- The stored delivery/confirmation location could not be manually moved in this case.
- At the correct apartment door, the normal delivery confirmation workflow could not be completed because the application required the driver to be near the incorrect stored location.

## Expected result

The highlighted building, navigation destination, and delivery confirmation zone should correspond to the apartment identified in the delivery details. If the stored location is incorrect, the driver should have a clear, reliable way to correct it and complete the delivery at the actual door without leaving that location or providing inaccurate proof of delivery.

## Reproducibility

Rare and intermittent for the severe end-to-end scenario based on field observation. Related location inconsistencies were observed over an extended period. Exact trigger and measured reproduction rate were not recorded, and the current product status has not been reverified.

## Severity

**High.** The issue blocks the correct end-to-end delivery workflow. It can force a choice between leaving a package at the wrong location and completing the physical delivery correctly while being unable to confirm it accurately in the application. Potential impact includes misdelivery, package loss, inaccurate proof of delivery, customer reimbursement or replacement, driver rating impact, and additional travel time.

## Priority

**To be assessed.** The impact is substantial when the issue occurs, but frequency, affected map data, and the population of affected apartment complexes are not known.

## Category

Functional / Navigation / State Management / Location

## Evidence

- Screenshot: A screenshot existed in the original private discussion but is not included because a safely redacted source file is not currently available.
- Video: Not available.
- Logs: Not available.

## Notes and follow-up

- Apartment addresses, unit numbers, stop numbers, route details, customer information, and account information have been intentionally omitted.
- The map may show several distinct location references: the delivery address, a blue-highlighted building, a numbered stop marker, the confirmation zone, and the actual apartment. This report does not assume that they share the same backend source.
- The internal cause is unknown. No claim is made about Amazon's mapping provider, customer-entered data, or backend implementation.
- Manual location adjustment has been available in some other delivery situations, but the conditions controlling its availability are unknown.
- The reporter recalls the broader location problem persisting across application and OS updates, but exact version boundaries were not recorded. This report therefore does not claim that every iOS version is affected.
- Similar behavior on Android is plausible but has not been observed or verified for this report; Android is intentionally excluded from the platform field.
- Apartment-unit labels sometimes appear at higher map zoom levels. It has not been established whether missing labels are a loading defect or unavailable source data, so that observation is not reported here as a separate bug.
- A future verification session should record the app version, device/OS, time, safely redacted screenshots, the exact blocked control or message, and whether each map reference disagrees independently.

