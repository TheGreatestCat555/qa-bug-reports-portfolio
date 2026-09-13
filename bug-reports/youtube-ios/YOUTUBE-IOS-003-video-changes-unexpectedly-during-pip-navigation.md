# YOUTUBE-IOS-003: Video changes unexpectedly during PiP playback while navigation is in use

> **Status:** Draft

## Summary

While a YouTube video is playing in Picture in Picture and a navigation application is in use, playback can unexpectedly change to another video without an intentional user action. The failure occurs at an unpredictable time and cannot currently be reproduced on demand.

## Product and platform

- Product: YouTube mobile application
- Platform: iOS

## Environment

| Field | Value |
|---|---|
| Device | iPhone 14 Pro Max |
| OS version | Not recorded |
| YouTube version/build | Not recorded |
| Interacting application | Navigation application; exact dependency not established |
| Network | Not recorded |
| Account state | Picture in Picture playback available; other account details omitted |
| Date and time | Exact occurrences not recorded |

## Preconditions

- A video is playing in the YouTube iOS application.
- Playback is active in the Picture in Picture window.
- A navigation application is in use.

## Steps to reproduce

The issue is intermittent and no deterministic trigger is known. The observed workflow was:

1. Start a video in YouTube.
2. Leave YouTube so the video continues in Picture in Picture.
3. Use a navigation application while PiP playback continues.
4. Continue normal use and observe the currently playing video.

## Actual result

At an unpredictable point, YouTube changes from the video selected by the user to another video without an intentional Next action or other known user input.

## Expected result

The selected video should remain active until the user changes it, the video reaches its normal end, or another clearly communicated playback rule takes effect.

## Reproducibility

Intermittent. The behavior has been observed in real use, but its occurrence time cannot be predicted and it cannot currently be reproduced on demand. A precise occurrence rate was not measured.

## Severity

**Medium.** The failure interrupts the selected media session and may require the user to return to YouTube to recover the intended video. Navigation itself was not reported to stop functioning.

## Priority

**To be assessed.** User impact is established, but the frequency, affected builds, ownership across applications, and trigger remain unknown.

## Category

Functional / Media Playback / Picture in Picture / State Management / Interoperability

## Evidence

- Screenshot: Not available.
- Video: Not available.
- Logs: Not available.

Because the event occurs at an unpredictable time, continuously recording the device solely to capture it would be disproportionate. The absence of a recording is documented rather than replaced with reconstructed evidence.

## Notes and follow-up

- This report is separate from `YOUTUBE-IOS-001`, in which PiP playback becomes unresponsive and its Play control cannot resume the video. Here, the observed failure is an unexpected change of the active video.
- It is not known whether YouTube, iOS, the navigation application, an advertisement transition, a network event, or another condition owns or triggers the failure.
- The exact destination video relationship, playback position, advertisement state, audio-interruption state, network transition, and application versions were not recorded and are intentionally not inferred.
- No viewed-content title, account information, route, address, customer information, or other personal data is included.
- If the issue is encountered again, useful low-effort evidence would be the original and resulting video titles, approximate playback position, whether an advertisement or navigation announcement had just occurred, and versions recorded after the event. Continuous screen recording is not required.

