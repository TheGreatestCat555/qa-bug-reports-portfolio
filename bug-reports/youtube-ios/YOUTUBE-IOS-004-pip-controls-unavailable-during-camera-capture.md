# YOUTUBE-IOS-004: PiP controls are unavailable while another application is using the camera

> **Status:** Draft — UX/interoperability candidate; expected iOS behavior has not been established.

## Summary

When a hidden YouTube Picture in Picture window is restored while the Amazon Flex delivery camera is active, the PiP window appears but its playback controls are unavailable and the Play control is greyed out with a diagonal unavailable indicator. Playback resumes automatically after the camera workflow ends, but the interface does not explain the temporary disabled state.

## Product and platform

- Product: YouTube mobile application
- Platform: iOS
- Interacting application: Amazon Flex

## Environment

| Field | Value |
|---|---|
| Device | iPhone 14 Pro Max |
| iOS version | Not recorded |
| YouTube version/build | Not recorded |
| Amazon Flex version/build | Not recorded |
| Network | Not recorded |
| Date observed | Historical observation; exact date not recorded |

## Preconditions

- A YouTube video is available in Picture in Picture.
- Amazon Flex has an active delivery workflow that opens the camera for package scanning or a delivery photo.

## Steps to reproduce

1. Start a YouTube video and move it to Picture in Picture.
2. Swipe the PiP panel to the edge so it remains represented by its restore arrow.
3. In Amazon Flex, proceed through a delivery until its camera is active for package scanning or a delivery photo.
4. Restore the hidden YouTube PiP panel while the camera remains active.
5. Inspect and attempt to use the PiP playback controls.
6. Hide the PiP panel again and complete the camera workflow.

## Actual result

- The PiP panel is restored, but playback does not resume.
- The Play control is greyed out and displays a diagonal unavailable indicator.
- Playback controls are not actionable while the camera is active.
- No explanation for the unavailable state is displayed.
- After the camera workflow ends, YouTube playback resumes automatically, including while the PiP panel is still hidden at the screen edge.

## Expected result

If playback must be suspended while another application captures camera or audio resources, the PiP interface should communicate that temporary state clearly and indicate that playback will become available after capture ends. Controls should not appear broken without an explanation.

## Reproducibility

Reported as reproducible through the described Amazon Flex camera workflow. Independent comparison with other camera and PiP applications has not been performed.

## Severity

**Low candidate.** The media interruption is temporary and the delivery workflow remains usable. The principal observed impact is ambiguous disabled-state feedback rather than loss of data or core functionality.

## Priority

**To be assessed.** Product ownership and expected iOS behavior are unknown.

## Category

UX / Picture in Picture / Interoperability / Resource State

## Evidence

- Screenshot or video: Not available in safely redacted form.
- Logs: Not available.

## Notes and limitations

- This is not the persistent unresponsive state in `YOUTUBE-IOS-001`: here playback automatically recovers when camera use ends.
- This is not the unexpected video change in `YOUTUBE-IOS-003`.
- The report does not assert that video playback must continue during camera capture. Temporary suspension may be expected iOS or application resource arbitration.
- It is not known whether YouTube, Amazon Flex, iOS, or their interaction owns the disabled-state presentation.
- Camera, microphone, audio-session, and resource-priority explanations remain hypotheses rather than established causes.
- No video title, account, address, route, stop, package, customer, or precise-location data is included.

