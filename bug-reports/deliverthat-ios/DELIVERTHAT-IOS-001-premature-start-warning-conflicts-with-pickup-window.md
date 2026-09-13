# DELIVERTHAT-IOS-001: Escalating start warnings appear before the stated delivery-start window

> **Status:** Draft

## Summary

For an accepted delivery, the driver received an in-app no-show warning and a dispatch SMS requiring the order to be started within five minutes approximately 25 minutes before the scheduled pickup. The driver's understood and displayed operating window allowed starting approximately 15 minutes before pickup. The SMS also warned of order recall and a possible app-misuse policy violation, pressuring the driver to begin earlier than the stated window.

## Product and platform

- Product: DeliverThat driver application and dispatch SMS service
- Platform: iOS and SMS

## Environment

| Field | Value |
|---|---|
| Device | iPhone; exact model not retained in this account |
| OS version/build | Not recorded |
| Official release context | iOS 26.4 was the latest standard release for compatible current-generation iPhones on March 26; released March 24, 2026. The exact device and installed build were not retained, so this is release context rather than an environment identification. |
| Application version/build | Not recorded |
| Workflow | Accepted delivery awaiting its scheduled pickup window |
| Network | Not recorded |
| Date observed | March 26, 2026 |

## Preconditions

- The driver has accepted a delivery and it remains assigned in the application.
- The scheduled pickup time is visible.
- The driver has not yet selected the control that begins the delivery because the stated start window has not begun.

## Steps to reproduce

The escalation condition cannot currently be reproduced on demand. The observed field sequence was:

1. Accept a delivery with a scheduled pickup time.
2. Keep the assigned delivery available in the application before the pickup window.
3. Do not begin the delivery approximately 25–30 minutes before pickup.
4. Observe an in-app warning stating that the delivery has not been started and requesting status confirmation to avoid a no-show.
5. Approximately five minutes later, observe a dispatch SMS requiring the driver to start within the next five minutes to avoid recall and warning of a possible app-misuse policy violation.
6. Compare the resulting deadline with the stated or understood start window of approximately 15 minutes before pickup.

## Actual result

- Penalty-style escalation began approximately 25–30 minutes before the scheduled pickup.
- The in-app message warned about a possible no-show.
- The dispatch SMS imposed a five-minute start deadline and mentioned possible order recall and an app-misuse policy violation.
- Following the SMS deadline required beginning the delivery approximately 20 minutes before pickup, earlier than the stated 15-minute start window.
- The driver began the delivery early to protect the assignment and account standing.

## Expected result

- The application, documented or displayed start window, dispatch messages, and recall/no-show enforcement should use one consistent timing rule.
- No no-show, recall, or policy-violation warning should be issued before the driver is actually expected and permitted to begin the delivery.
- If beginning the delivery earlier is required, the application should state the correct deadline clearly before the escalation occurs.

## Reproducibility

Observed once for one assigned delivery. The timing behavior has not been reproduced in a controlled test across multiple orders.

## Severity

**High.** The messages use account-enforcement and order-recall language while apparently conflicting with the expected action window. A driver may begin too early, travel or wait unnecessarily, or risk losing the assignment and receiving an account consequence by following the other timing instruction. No actual recall or policy violation was recorded in this observation.

## Priority

**High candidate.** The financial and account-standing risk warrants investigation, but frequency and the authoritative timing policy still require confirmation.

## Category

Functional / Cross-Channel Consistency / Timing Logic / Notification Escalation / UX

## Evidence

- A historical field account records the scheduled pickup offset, the in-app no-show warning, the later five-minute SMS deadline, and the driver's early start response.
- The original screenshots and SMS contained personal and assignment-specific information and are not included in the public report.
- Application logs and dispatch records: Not available.

## Notes and limitations

- The report does not assert that the application and dispatch service are separate or unsynchronized systems; that was an earlier hypothesis without internal evidence.
- The authoritative DeliverThat policy text and the exact UI text defining the 15-minute window have not yet been preserved in a safely reviewable attachment.
- The exact warning times were reported approximately, so the report focuses on the relative offsets from pickup rather than publishing assignment-specific clock times.
- It is unknown whether dispatch applied a route-specific travel-time rule, restaurant-specific requirement, experiment, timezone conversion, or another unpublished condition.
- No actual recall, no-show classification, policy violation, or loss of earnings was recorded after the driver started early.
- A future verification should retain the app and OS versions, privacy-safe screenshots of the permitted start window and both warnings, exact timestamps, timezone, pickup deadline, travel-time estimate, location state, final assignment outcome, and any relevant support explanation.
- Release timing is based on Apple's [official security-release history](https://support.apple.com/en-ca/100100). Automatic Updates were reportedly enabled on the reporter's iPhone, but the device model, rollout timing, and actual installation remain unverified.
