# YOUTUBE-IOS-002: Leaving YouTube sometimes stops playback without opening the PiP window

> **Status:** Draft

## Summary

When the user leaves YouTube with an active video, the application sometimes remains in the iOS app switcher but does not create the expected Picture in Picture window and does not continue playback.

## Product and platform

- Product: YouTube mobile application
- Platform: iOS

## Environment

| Field | Value |
|---|---|
| Device | iPhone 14 Pro Max |
| OS version | Not recorded |
| Official release context | On the March 17 documentation date, iOS 26.3.1 was the latest standard release compatible with iPhone 14 Pro Max; released March 4, 2026. Automatic Updates were reportedly enabled, but actual installation was not verified. |
| Application version/build | Not recorded |
| Interacting application | Observed during workflows involving navigation applications |
| Network | Not recorded |
| Account state | Picture in Picture playback available and normally functional; other account details omitted |
| Region and language | United States; application language not recorded |
| Date and time | Exact occurrence not recorded; detailed field account documented on March 17, 2026 |

## Preconditions

- A video is actively playing in YouTube.
- Picture in Picture is available and normally starts when leaving the application.
- A navigation application has been or will be used in the same workflow.

## Steps to reproduce

The issue is intermittent and cannot currently be reproduced on demand. The observed action was:

1. Start a video in YouTube.
2. Swipe up from the bottom of the screen to leave YouTube.
3. Observe whether the PiP window appears and playback continues.
4. Open the iOS app switcher and verify that YouTube is still present as a recent application.

## Actual result

- The expected PiP window does not appear.
- Video playback stops instead of continuing in the small overlay.
- YouTube remains present in the iOS app switcher, so the application was not intentionally closed by the user.
- Repeatedly closing and reopening YouTube may be required; in some occurrences, a device restart was used to restore normal behavior.

## Expected result

When a playing video is eligible for Picture in Picture and the user leaves YouTube, playback should continue in the PiP window consistently, as it does in the normal workflow.

## Reproducibility

Intermittent. Observed in workflows involving navigation applications. Exact rate and trigger were not recorded.

## Severity

**Medium.** Background playback is lost and the user may need to restart the application or device, but foreground YouTube use and the rest of the device remain available.

## Priority

**To be assessed.** Version scope, account/PiP eligibility conditions, interaction with navigation applications, and reproduction frequency require verification.

## Category

Functional / State Management / Picture in Picture / Interoperability

## Evidence

- Screenshot: Not available in safely redacted form.
- Video: Not available.
- Logs: Not available.

## Notes and follow-up

- Release timing is based on Apple's [official security-release history](https://support.apple.com/en-ca/100100) and is contextual evidence only; the exact occurrence date and installed build remain unknown.

- This report does not include viewed content, account details, navigation routes, addresses, or delivery information.
- The presence of YouTube in the app switcher is recorded only as a user-visible state; no conclusion is made about process lifecycle, memory pressure, cache, or the internal cause.
- A future session should confirm PiP eligibility before the test, record iOS/YouTube versions, identify the preceding application transitions, capture a redacted screen recording, and test with and without a navigation application.
