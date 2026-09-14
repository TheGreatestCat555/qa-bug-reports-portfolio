# APPLE-FILES-IOS-001: Files freezes after an edge gesture during inline rename

> **Status:** Draft

## Summary

While a file is being renamed inline near the left edge of the Files application, a slight rightward gesture beginning at the screen edge can leave the application unresponsive. The application must be force-closed to recover.

## Product and platform

- Product: Apple Files
- Platform: iOS

## Environment

| Field | Value |
|---|---|
| Device | iPhone 14 Pro Max |
| iOS version | 26.3.1, as reported for the observed session |
| Storage location | On My iPhone |
| Orientation | Portrait |
| File name and contents | Excluded |
| Date and time | Not recorded |

## Preconditions

- A file is visible in an `On My iPhone` folder.
- The file supports inline renaming.

## Steps to reproduce

1. Open Files in portrait orientation.
2. Navigate to an `On My iPhone` folder.
3. Begin renaming a file inline.
4. While the rename field is active near the left screen edge, make a slight rightward gesture beginning at or close to the left edge.
5. Attempt to continue editing or interacting with Files.

## Actual result

Files becomes unresponsive after the gesture. Normal interaction does not recover the screen, and the application must be force-closed.

## Expected result

Files should either continue the inline rename, dismiss editing cleanly, or perform the recognized navigation gesture without entering an unresponsive state.

## Reproducibility

Reproduced in 3 of 3 reported attempts under the observed conditions. Reproduction on other devices, iOS versions, storage providers, orientations, or file types has not been tested.

## Severity

**Medium.** The failure blocks the current Files session and requires a force-close. No file corruption or permanent data loss was reported.

## Priority

**To be assessed.** Reproduction was consistent in the reported session, but the affected scope and current-version behavior are unknown.

## Category

Functional / Gesture Handling / Inline Editing / Application Freeze

## Evidence

- Screenshot or video: Not available.
- Crash or diagnostic logs: Not available.

## Notes and limitations

- The report describes the application becoming unresponsive, not merely difficulty placing the text cursor at the beginning of a file name.
- The exact gesture distance, duration, rename-field position, file type, and folder path were not measured.
- No file name, folder name, account, document contents, or personal data is included.
- A future retest should compare list/grid presentation, local/iCloud storage, file-name lengths, left-edge distances, cancelled/committed rename state, and whether the system back gesture begins before the freeze.

