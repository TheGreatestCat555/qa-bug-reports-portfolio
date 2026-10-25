# SPARK-IOS-003: Offers and push notifications continue after Spark Now is turned off

> **Status:** Draft

## Summary

After the driver selected `TURN OFF` to stop Spark Now, Spark Driver continued sending offer notifications and displaying offers inside the application. Closing the app, reopening it, enabling Spark Now again, and turning it off again did not resolve the repeated notifications during the reported episode.

The screenshot shows the `SPARK NOW` start control together with offer cards, a Spark notification, and an in-app new-offers message. This is a visible availability/offer-state inconsistency; it does not establish the driver's authoritative server-side online status.

## Product and platform

- Product: Spark Driver
- Platform: iOS
- Component: Spark Now availability, offer delivery, and push notifications

## Environment

| Field | Value |
|---|---|
| Device | iPhone 14 Pro Max |
| Application update state | Fully updated, as reported by the driver |
| Application version reference | 4.51.0, the latest version displayed by the US App Store when checked on October 25, 2026 |
| OS update state | Fully updated, as reported by the driver |
| OS version reference | iOS 27.0.1, the latest stable version listed by Apple for this device class when checked on October 25, 2026 |
| Installed build verification | Exact version/build screens were not supplied; the version numbers above combine the driver's update statement with current official release information |
| Network | Wi-Fi indicator visible at screenshot capture; connectivity during the full episode not recorded |
| Date observed and documented | October 25, 2026 |
| Screenshot clock | 2:12; AM/PM and exact onset time are not established by the image |

Apple's release page lists iOS 27.1 specifically for iPhone Duo, so that device-specific release is not substituted for the iPhone 14 Pro Max environment. No beta or release-candidate installation was reported.

## Preconditions

- The driver is signed in to Spark Driver and can receive offers.
- Spark Now has been enabled.
- Notifications are permitted.

## Steps to reproduce

This sequence records the driver's observed workflow. The trigger for entering the faulty state is unknown.

1. With Spark Now enabled, open the availability control.
2. Select `TURN OFF` to stop receiving offers.
3. Observe whether new offer notifications continue to arrive.
4. Check the Home screen for the `SPARK NOW` control and offer messages/cards.
5. Dismiss Spark Driver from the app switcher and observe subsequent notifications.
6. Reopen Spark Driver.
7. Select `SPARK NOW` to enable availability again.
8. Turn Spark Now off again.
9. Dismiss the application again and check whether further offer notifications arrive.

Turning off Spark Now is distinct from signing out of the account. A complete account sign-out was not reported.

## Actual result

- Offer notifications continued repeatedly after availability was turned off.
- Offers continued to appear in the application.
- Dismissing the application did not stop the notifications.
- Reopening the app and repeating the on/off availability cycle also did not resolve the behavior.
- The current episode lasted noticeably longer than the earlier occurrence, but its duration was not timed.

The screenshot contains all of the following at the same time:

- The blue `SPARK NOW` start control.
- A Spark Driver banner stating `You have offers to preview.`
- Offer cards with accept/reject controls.
- An in-app message stating `You have new offer(s) available.`

The Dynamic Island online label belongs to **Uber**, not Spark Driver, and is not evidence of Spark availability.

## Expected result

After `TURN OFF` is applied successfully, Spark Driver should stop sending new offer notifications and maintain a consistent availability state. Walmart's Spark Now help article explicitly identifies `TURN OFF` as the action used to stop receiving offers.

This expectation does not require the immediate removal of every previously delivered notification or cached card. Repeated arrivals after turning off availability, rather than the mere presence of an old card, are the reported failure.

## Reproducibility

Intermittent, with at least two episodes on the same device. The driver remembers one short episode approximately a month earlier and the longer current episode on October 25. The earlier installed versions are unknown; the driver recalls an intervening iOS update but is not certain. No exact failure rate or duration was measured.

## Severity

**Medium candidate.** The availability control does not reliably stop offer interruptions, and the conflicting interface leaves the driver unable to tell whether the request took effect. No acceptance-rate penalty, automatic offer acceptance, financial loss, or ongoing server-side online state is established.

## Priority

**To be assessed.** The same driver has experienced the issue more than once and the attempted recovery did not help, but prevalence and affected versions are unknown.

## Category

Functional / Availability State / Offer Delivery / Push Notifications / State Synchronization / Application Lifecycle

## Workaround

No successful workaround was verified. App dismissal, reopening, and repeating the Spark Now on/off cycle were unsuccessful in this episode.

## Evidence and privacy

- Firsthand description and one supplied screenshot.
- The screenshot supports simultaneous display of the start control, offers, and notification; the repeated arrivals and recovery attempts are supported by the driver's account.
- The original image remains private because it includes a map, store/location information, offer amounts, and other operational details.
- No original image, customer information, private file path, account identifier, or exact location is included in the public report.
- No push-payload timestamps, availability requests/responses, application logs, or server-state records are available.

## Notes and follow-up

Differentiate delayed pushes generated before `TURN OFF` from newly generated offers after the availability change. Record the installed version screens, availability acknowledgement, notification arrival times, and offer identifiers in a private diagnostic session. Compare foreground, background, and terminated-app states. Verify whether the Home start control reflects the authoritative availability state.

Stale UI state, delayed notifications, or a failed availability update are possibilities for investigation, not confirmed causes. The current evidence does not prove a regression caused by the recent iOS update.

## Reference checks

- [Spark Driver — US App Store](https://apps.apple.com/us/app/spark-driver/id1483998235): version 4.51.0, checked October 25, 2026.
- [Apple security releases](https://support.apple.com/en-us/100100): stable iOS version and device applicability, checked October 25, 2026.
- [Walmart Spark Driver help — Using Spark Now](https://sparkdriverapp-walmart.helpdocs.io/l/en/article/dy45ht4rgm-turning-on-spark-now): turning off availability to stop receiving offers, checked October 25, 2026.
