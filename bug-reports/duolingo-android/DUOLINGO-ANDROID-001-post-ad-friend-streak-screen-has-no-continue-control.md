# DUOLINGO-ANDROID-001: Post-ad friend-streak screen has no visible Continue or Skip control

> **Status:** Draft

## Summary

After completing a lesson/test and dismissing the subsequent advertisement, a free Duolingo user reaches a friend-streak celebration screen with no visible way to continue or skip it. The same missing-control behavior has been observed over two or three consecutive days on a Samsung Galaxy S25 Ultra.

## Product and platform

- Product: Duolingo
- Platform: Android
- Component: Post-lesson flow following an advertisement / friend-streak celebration

## Environment

| Field | Value |
|---|---|
| Device | Samsung Galaxy S25 Ultra, as identified by the user |
| Duolingo version | 6.103.6, reported by the user |
| OS release reference | Android 17; latest stable major Android release identified in the official release information checked on November 5, 2026 |
| Subscription | Free account; no paid subscription |
| Interface language | Russian |
| Navigation mode | Android three-button navigation visible in the photo |
| Network at photo capture | Wi-Fi indicator visible; connection quality not measured |
| Date documented | November 5, 2026 |
| Observation period | Repeated over the preceding two or three days; exact first occurrence not recorded |

The OS entry is release context, not a device reading. The user described the OS as current but did not provide its version screen. Samsung's availability can vary by model variant, region, and carrier; no installed OS build or One UI version is assigned. Duolingo 6.103.6 is the reported affected version, not an independently verified claim that it is the newest store release.

## Preconditions

- A signed-in free Duolingo account is used on the affected phone.
- Completing the lesson/test triggers an advertisement.
- The post-completion sequence includes the friend-streak celebration screen.

## Steps to reproduce

These steps reconstruct the reported sequence. The exact lesson/test type and conditions for showing this celebration are not yet isolated.

1. Complete a lesson/test on the free account.
2. Allow the post-completion advertisement to appear.
3. Dismiss or skip the advertisement when its dismissal control becomes available.
4. Advance through the preceding results/rewards screen to the friend-streak celebration.
5. Inspect the screen for a Continue, Skip, Close, or equivalent in-app navigation control.

The user identified the affected page as the second post-ad page, following a results/rewards page. The complete transition sequence was described verbally, not captured in a recording.

## Actual result

The screen headed `Лучшие друзья навсегда!` ("Best friends forever!") displays friend avatars and a streak indicator, but no visible in-app button to continue, skip, or close it. The supplied photo includes the lower part of the screen and the Android system navigation bar; no continuation button is visible above that bar.

The user cannot identify the normal in-app action for proceeding beyond this page. A full application freeze, an unresponsive system Back button, or loss of lesson credit has not been established.

## Expected result

The post-completion flow should provide a visible, accessible way to continue or dismiss an optional celebration. If the page is meant to advance automatically, it should complete that transition without leaving the user unable to proceed; a static photo does not establish whether automatic advancement was intended.

## Reproducibility

Reported on two or three consecutive days on the same device. Exact attempt count, waiting time on the page, and controlled reproduction rate are unknown. The issue is not labelled 100% reproducible.

## Severity

**Medium candidate.** The missing control interrupts normal post-lesson navigation repeatedly. Lesson completion, progress persistence, access through Android Back, and restart recovery have not been tested, so this is not classified as total application failure or progress loss.

## Priority

**To be assessed.** Recurrence across multiple days makes the issue worth investigating, but the number of affected users and the availability of a recovery path are unknown.

## Category

Functional / UI / Post-Lesson Navigation / Missing Control / Advertisement Transition

## Workaround

No verified workaround was provided. System Back, reopening the app, and rotation are follow-up checks, not established fixes.

## Evidence and privacy

- One user-supplied photograph of the affected phone screen supports the absence of a visible continuation control at capture time.
- The user supplied the application version and the recurring sequence leading to this screen.
- The original photo remains private because it includes friend avatars, notification indicators, and surrounding background content. It is not added to the public repository.
- The photo does not show installed OS details, the preceding advertisement, elapsed waiting time, or the outcome of navigation/recovery attempts.

## Follow-up verification

Record a privacy-safe reproduction from lesson completion through ad dismissal and the celebration screen, including time spent waiting. Check whether the control is absent, delayed, off-screen, or obscured at the actual display/font settings. Compare a different lesson, UI language, and device, and test system Back and reopening while checking that completed lesson progress is preserved. An ad SDK failure, layout/inset issue, network delay, or state-transition problem is not established by this evidence.

## Release reference

[Google — Android 17 is here](https://android-developers.googleblog.com/2026/06/Android-17.html), stable release announced June 16, 2026; checked November 5, 2026. This reference does not verify installation on the affected Samsung device.
