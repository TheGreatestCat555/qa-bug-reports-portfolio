# IOS-SYSTEM-001: Notifications remain suppressed after Focus is disabled

> **Status:** Draft

## Summary

After Sleep or Do Not Disturb Focus was disabled following overnight use, notifications from multiple applications did not resume. The user reported missing banners, notification sounds, app badges, and folder badge counts, including ChatGPT completion notifications.

## Product and platform

- Product: iOS
- Component: Focus transitions and notification presentation
- Platform: iPhone

## Environment

| Field | Value |
|---|---|
| Device | iPhone 14 Pro Max, carried over from the same-device observation context |
| OS version | Not independently verified; the contemporaneous report lists iOS 26.6.2 |
| Focus mode | Sleep and/or Do Not Disturb; exact mode in the affected episode not isolated |
| Affected application builds | Not recorded |
| Network | Not recorded |
| Date documented in the observation | October 7, 2026 |
| Time of occurrence | After overnight Focus use; exact time not recorded |

## Preconditions

- The user normally receives notifications from multiple applications.
- Sleep or Do Not Disturb Focus is used overnight.
- The user turns the Focus mode off before expecting normal notifications again.

## Steps to reproduce

The sequence below reconstructs the reported episode. It is not a verified procedure for consistently triggering the defect.

1. Enable Sleep or Do Not Disturb Focus.
2. Leave it enabled overnight.
3. Disable the Focus mode from Control Center.
4. Observe notification presentation during subsequent normal use, including after ChatGPT completes a response.
5. Check notification sounds, banners, app badges, and folder badge counts across applications.

## Actual result

The user reported that visual and audible notifications did not return after Focus was turned off. App and folder notification counts also remained missing. ChatGPT did not present its usual completion notification, and the issue appeared to affect other applications as well.

## Expected result

New eligible notifications should follow the normal per-application and system settings once no suppressing Focus is active. Badge visibility should follow those settings as well. This expectation does not require iOS to replay every sound or banner for notifications received while Focus was enabled.

## Reproducibility

Observed once. The user regularly follows this overnight routine and had not previously encountered this result. A controlled repeat attempt was not recorded.

## Severity

**Medium candidate.** The reported loss of notification presentation across applications can make incoming messages and completed tasks easy to miss. Duration, affected notification types, and recovery have not been measured.

## Priority

**To be assessed.** The breadth and recurrence of the issue are unknown.

## Category

Functional / Focus / Notifications / State Management / Badge Presentation

## Evidence and limitations

- Firsthand description of the overnight routine and the subsequent notification failure.
- No screen recording, notification-delivery logs, or settings captures are available.
- No account details, notification contents, or private conversation links are included.
- Delivery failure and presentation suppression have not been distinguished.
- The exact Focus configuration, scheduled reactivation, other devices sharing Focus, Silent mode, and per-app notification settings were not captured.
- The scope does not establish a specific iOS root cause or prove that every application was affected.

## Follow-up verification

Send a controlled new notification after disabling Focus and record the visible Focus state, notification permissions, badge settings, and arrival/presentation timestamps. Compare notification delivery with presentation, check for automatic Focus reactivation, and record whether toggling Focus or restarting the device restores behavior.
