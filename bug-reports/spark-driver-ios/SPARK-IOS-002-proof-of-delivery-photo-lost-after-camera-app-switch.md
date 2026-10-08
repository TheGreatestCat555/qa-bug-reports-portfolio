# SPARK-IOS-002: Proof-of-delivery photo is lost after switching to the iPhone Camera

> **Status:** Draft

## Summary

After capturing a delivery photo in Spark Driver, the user backgrounded the application, took a separate photo with the iPhone Camera, and returned. Spark no longer retained the delivery photo and required another one. The issue occurred three times during one multi-stop delivery trip, including two consecutive occurrences.

## Product and platform

- Product: Spark Driver
- Component: Proof-of-delivery photo and delivery-confirmation state
- Platform: iOS

## Environment

| Field | Value |
|---|---|
| Device | iPhone 14 Pro Max |
| OS version | Not independently verified; the contemporaneous report lists iOS 26.6.2 |
| Installed application version | Not verified |
| Version mentioned in the contemporaneous report | 4.48.1, described as the store version; affected installed build not established |
| Trip type | Multi-stop Pickup & Drop-off; no shopping |
| Other application used | Native iPhone Camera |
| Network | Not recorded |
| Date documented in the observation | October 2, 2026 |
| Exact occurrence times | Not recorded |

## Preconditions

- An active Pickup & Drop-off trip is in progress.
- The current delivery requires a proof-of-delivery photo.
- The user has taken that photo but has not finished all remaining confirmation steps.

## Steps to reproduce

The user reported this sequence repeatedly in the same trip. It has not been reproduced in a controlled test.

1. Leave the order at the delivery location.
2. Capture the required delivery photo within Spark Driver.
3. Before finishing delivery confirmation, send Spark Driver to the background.
4. Open the native iPhone Camera.
5. Take a separate photo, such as the house number.
6. Return to Spark Driver.
7. Check whether the delivery photo remains attached.

Spark Driver was backgrounded, not intentionally force-closed. Whether iOS terminated its process while in the background is unknown.

## Actual result

The previously captured delivery photo was no longer available in the workflow. Spark Driver required a new photo, preventing the user from continuing with the one already taken.

By that time, the user could have walked away from the door and the customer could have collected the order, making the original scene difficult or impossible to photograph again.

## Expected result

A captured delivery photo should survive a temporary application switch and remain associated with the current delivery-confirmation step. If the session must be reset or the photo becomes unavailable, the application should clearly explain the recovery needed.

The observation confirms capture in the workflow, not successful upload to Spark's servers.

## Reproducibility

Intermittent. Three occurrences during the same multi-stop trip, including two consecutive occurrences. The total number of attempts was not recorded.

## Severity

**High candidate.** Loss of the photo interrupts a core proof-of-delivery step. Retaking it may require returning to the door, and the delivered items may already have been collected. No customer dispute, lost server record, or financial consequence is established.

## Priority

**To be assessed.** Repeated failure in one trip warrants investigation, but build range, broader prevalence, and exact lifecycle conditions remain unknown.

## Category

Functional / Delivery Workflow / Photo Persistence / Application Lifecycle / State Restoration

## Workaround

Complete the full delivery-confirmation flow before switching applications. This is a proposed avoidance measure, not a verified fix. If the photo has already been lost, retake an accurate delivery photo only if the delivered items are still available.

## Evidence and limitations

- Firsthand description of three incidents and the application-switching sequence.
- No controlled screen recording, process-lifecycle logs, or upload status is available.
- Customer identities, addresses, orders, house-number photos, and private conversation links are excluded.
- The observation does not establish whether the image was deleted, its reference was lost, or the workflow reset.
- Memory pressure, process termination, session refresh, temporary-image storage, and network state are untested possibilities.

## Follow-up verification

On a privacy-safe test delivery, record photo capture and attachment state before and after switching to Camera. Compare a simple background/foreground transition with taking another photo, and test process restoration separately. Confirm whether the original image exists locally or server-side when the workflow requests a replacement.
