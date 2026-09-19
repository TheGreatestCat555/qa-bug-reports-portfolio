# VEHO-IOS-001: An active driver account moves to the waitlist while offer navigation remains intermittently accessible

> **Status:** Draft

## Summary

A driver account that had completed the available activation flow and could use the Offers area later began opening on a waitlist screen. The change was not accompanied by a clear reason or recovery path.

The restriction is not applied consistently. Offer notifications continue to arrive, and opening one of them can expose the Offers area. On some launches, tapping a bottom-navigation item immediately after the notification opens also allows movement between app sections before the waitlist screen takes over. The account remains waitlisted throughout.

## Product and platform

- Product: Veho Driver
- Component: Driver eligibility state, offer notifications, deep-link routing, and bottom navigation
- Platform: iOS

## Environment

| Field | Value |
|---|---|
| Device | iPhone 14 Pro Max |
| OS version | iOS 26.5, as reported during the field observation |
| Application version | 3.3.4, as shown in the source evidence |
| Notification permission | Enabled when requested after a mandatory application update |
| Network conditions | Not recorded |
| Date documented | June 18, 2026 |

## Preconditions

- The account has completed every activation step presented by Veho Driver.
- The account previously opened the Offers area and did not display a waitlist restriction.
- The app now shows `You're on the Waitlist` when launched normally.
- Offer notifications are enabled.

## Steps to reproduce

The account-state change itself was observed in normal use and was not reproduced under controlled conditions. The following steps describe the repeatable entry path available after that change:

1. With the account showing the waitlist screen on normal launch, wait for an offer-related push notification.
2. Open Veho Driver by selecting the notification.
3. Observe the screen reached from the notification.
4. On a subsequent notification launch, immediately select one of the visible bottom-navigation items.
5. If a section opens, select other bottom-navigation items before the waitlist restriction takes over.
6. Close the app and launch it normally again.

## Actual result

- An account that previously had access to Offers opens on a waitlist screen during a normal launch.
- Offer-related push notifications continue to arrive for that account.
- Selecting a notification can open the Offers area instead of the waitlist screen.
- Pull-to-refresh is available in Offers, but no offer appeared during the recorded observation.
- On some attempts, an immediate tap on the bottom navigation opens a section and permits further tab changes for a short period.
- If the tap is not made quickly enough, the navigation opportunity is lost.
- Closing and reopening the app normally returns the account to the waitlist screen.

## Expected result

The app should present one clear account state across normal launch, notifications, and deep links.

If the account is eligible to receive offers, the Offers area should remain available during a normal launch. If the account is waitlisted, offer notifications and notification-driven navigation should respect that restriction. Any legitimate eligibility change should be explained to the driver and provide an appropriate next step.

## Reproducibility

The waitlist state is visible on normal launch. Notification-based access was observed more than once, but the brief bottom-navigation access is intermittent and depends on tapping immediately after the notification opens. An exact timing window and success rate were not measured.

## Severity

**High candidate.** A previously active driver loses normal access to the area used to obtain work, while other app entry paths continue to expose parts of the restricted workflow. The conflicting states leave the driver unable to determine whether the account is active, waitlisted, or partially accessible. The report does not quantify lost work or financial damages.

## Priority

**To be assessed.** The effect is substantial for the affected driver, but the number of affected accounts, the eligibility decision behind the state change, the version range, and the availability of a support-side recovery path are unknown.

## Category

Functional / Account State / Access Control / Deep Linking / Notifications / Navigation

## Workaround

No workaround that restores normal account access was verified. Opening an offer notification may temporarily expose app sections, but it does not remove the waitlist state and should not be treated as a reliable recovery path.

## Evidence

- Firsthand field account covering the active state, later waitlist state, notification entry path, and timing-sensitive navigation behavior.
- Screenshot confirming the waitlist screen and its instruction to await an email update.
- Screenshots showing the application version and the Offers area reached from the notification.
- Original screenshots are withheld because account, notification, region, schedule, or other identifying details may be present.
- Application logs, account-state history, notification payloads, server responses, and internal eligibility records are not available.

## Notes and limitations

- The sequence occurred after a mandatory application update, but the available evidence does not prove that the update caused the account-state change.
- The prior ability to use Offers and the later waitlist screen establish a visible state regression. They do not reveal whether Veho intentionally changed the account's eligibility or whether the state changed in error.
- Veho's internal rule for when an activated account may be placed on a waitlist was not independently verified.
- The timing-sensitive navigation could result from state initialization order, cached navigation, delayed eligibility enforcement, or another implementation detail. This report does not assign a root cause.
- Reaching Offers or another tab does not establish that the account could accept and complete an offer.
- Legal claims, correspondence, and alleged damages are outside the scope of this technical report.

## Suggested verification

1. Compare the account's authoritative eligibility state with the state returned during cold launch and notification launch.
2. Test notification delivery and deep-link routing for active, waitlisted, suspended, and partially onboarded accounts.
3. Verify that access checks complete before bottom navigation becomes interactive.
4. Repeat with the app terminated, backgrounded, and already open.
5. Capture timestamps for notification receipt, deep-link handling, eligibility response, navigation rendering, and waitlist presentation.
6. Confirm that a legitimate eligibility transition is communicated consistently in the app and by email.
