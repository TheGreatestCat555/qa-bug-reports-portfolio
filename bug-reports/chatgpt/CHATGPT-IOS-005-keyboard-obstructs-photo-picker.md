# CHATGPT-IOS-005: On-screen keyboard remains visible over the photo picker and obstructs image selection

> **Status:** Draft

## Summary

When the image-attachment workflow is used to browse a folder or album and select multiple images, the iOS keyboard remains visible over the picker even though no text field is visibly being edited. The keyboard cannot be dismissed within the picker, obscures a substantial part of the thumbnail grid, and reappears after the workflow is exited and repeated.

## Product and platform

- Product: ChatGPT for iOS
- Component: Image attachment / photo picker / multi-selection
- Platform: iOS

## Environment

| Field | Value |
|---|---|
| Device | iPhone 14 Pro Max |
| OS version | iOS 26.6, as shown in the source evidence |
| ChatGPT version | 1.2026.188 |
| ChatGPT build | 29133674010 |
| Visible keyboard layout | Russian |
| Orientation | Not recorded |
| Accessibility and display settings | Not recorded |
| External or third-party keyboard state | Not recorded |

## Preconditions

- A conversation is open in ChatGPT for iOS.
- The image-attachment interface is opened.
- The user browses to an album or folder and selects multiple images.

It is not known whether the conversation composer had keyboard focus immediately before the attachment workflow was opened.

## Steps to reproduce

1. Open a conversation in ChatGPT for iOS.
2. Open the workflow for attaching images.
3. Browse to a folder or album containing screenshots or photos.
4. Select multiple images.
5. Observe the lower portion of the image-selection interface.
6. Attempt to dismiss the keyboard without leaving the picker.
7. Exit the picker and repeat the workflow.

## Actual result

- The iOS keyboard is displayed over the image picker while no visible text field is being edited.
- The keyboard covers a substantial part of the thumbnail grid and reduces the available selection area.
- Fewer thumbnails can be reviewed at the same time.
- The keyboard cannot be dismissed while remaining in the affected selection workflow.
- Exiting the picker abandons or resets the current workflow, but the keyboard appears again when the process is repeated.

## Expected result

Opening the image-selection interface should dismiss the keyboard unless the user intentionally activates a visible text or search field. The full available screen area should remain usable for browsing and selecting thumbnails.

If text input is intentionally active, the interface should provide a clear way to dismiss the keyboard without abandoning the current selection.

## Reproducibility

Consistently reproduced in the reporter's tested attempts. The exact number of attempts was not recorded, so no measured percentage is claimed.

## Severity

**Medium candidate.** The obstruction directly interferes with a core attachment workflow and makes multi-image review and selection slower and more error-prone. The workflow was not shown to be completely blocked, and no crash or data loss was established.

## Priority

**To be assessed.** The affected user population, device and iOS ranges, configuration dependencies, and responsible component are unknown.

## Category

Functional / UI / Keyboard State / Attachment Workflow / Interoperability

## Evidence

- A screenshot was supplied in the original field discussion and reportedly shows the Russian iOS keyboard covering the lower portion of a multi-selection photo grid.
- The source screenshot is not included publicly because unrelated thumbnails and surrounding UI may expose private information from other applications or workflows.
- No application logs, screen recording, or exact attempt count is available.

## Notes and follow-up

- Retained input focus from the conversation composer is one possible investigation area, not a confirmed cause.
- Ownership is not established between ChatGPT, the iOS picker, keyboard state, or their integration.
- Future verification should compare composer keyboard open versus dismissed before attachment, single versus multiple selection, Recents versus a named album, Russian versus English keyboards, portrait versus landscape, fresh launch versus a long-running session, and the same picker workflow in another iOS application.
- A future evidence capture should be created with non-sensitive test images so the keyboard overlap can be shown without exposing unrelated thumbnails.
