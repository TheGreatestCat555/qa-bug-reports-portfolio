# [DASHER-MOBILE-001] Scheduled catering pickup is calculated as 1,431 minutes early

> **Status:** Draft — based on third-party screenshots; independent reproduction, application build, platform, and redacted evidence are not available.

## Summary

The DoorDash Dasher application calculates a scheduled catering pickup completed at 5:34 PM against a displayed 5:25 PM expected pickup as **1,431 minutes early**, although the visible timestamps place the pickup approximately **9 minutes late**. The same order displays an implausible 1,901-minute expected completion time, indicating a likely one-calendar-day offset in the scheduled-order timestamp data or comparison logic.

The report also records a potentially related discrepancy between the displayed 10:07 AM offer-acceptance time and 38 minutes of California Active Time. Whether this is a compensation defect cannot be determined from the available evidence because Claim Ahead reservation time may be distinct from active delivery time.

## Product and platform

- Product: DoorDash Dasher
- Feature: Scheduled catering / Claim Ahead order; On Time details; earnings details
- Platform: Mobile application; iOS or Android not recorded

## Environment

| Field | Value |
|---|---|
| Device | Not recorded |
| OS and version | Not recorded |
| Application version/build | Not recorded |
| Network | Not recorded |
| Account state | California Dasher eligible for a scheduled catering offer; exact tier and settings not recorded |
| Region and language | California, USA; application UI shown in English |
| Date observed | August 17, 2026 |
| Merchant | Dos Coyotes / Dos Coyotes Border Cafe |
| Order status | Completed; displayed as `On time` |

## Source and evidence limitations

This report is based on screenshots shared by another Dasher in a driver chat. The account does not belong to the portfolio owner, and the behavior was not independently reproduced.

The screenshots are not committed because the originals are unavailable for a complete privacy, ownership, and redaction review. All observations below are limited to values visible in the supplied material. Missing technical details are marked as not recorded rather than inferred.

## Preconditions

1. A California Dasher account is eligible for scheduled catering / Claim Ahead offers.
2. A catering offer is claimed or accepted several hours before its scheduled pickup window.
3. The order remains associated with the account until fulfillment.

## Steps to reproduce

These steps reconstruct the observed workflow and require independent verification:

1. Claim a scheduled catering offer several hours before its pickup window.
2. Start or continue the Dash as instructed by the application.
3. Arrive at the merchant near the scheduled pickup time.
4. Mark the order as picked up.
5. Complete the delivery.
6. Open the completed order's **On Time** details.
7. Compare the expected and actual pickup times with the displayed pickup difference.
8. Compare the expected-completion value and total time difference with the visible order timeline.
9. Open the daily earnings details.
10. Compare **Dash Time**, **Active Time**, **Active Time in California**, and the displayed offer-acceptance timestamp.

## Actual result

The application displays the following timeline and calculated values:

| Event or metric | Displayed value |
|---|---:|
| Offer accepted | 10:07 AM |
| Expected pickup | 5:25 PM |
| Actual pickup | 5:34 PM |
| Pickup difference | **Early by 1,431 min** |
| Expected delivery | 5:59 PM |
| Actual delivery | 5:55 PM |
| Delivery difference | Early by 4 min |
| Expected completion time | **1,901 min** |
| Total time difference | **-1,435 min** |

The daily earnings details display:

| Metric | Displayed value |
|---|---:|
| Start Time | 8:24 AM |
| End Time | 5:55 PM |
| Dash Time | 9 hr 30 min |
| Active Time | 38 min |
| Active Time in California | 38 min |
| Offers / deliveries | 1 / 1 |
| Earnings | $30.47 |

## Expected result

- An actual pickup at 5:34 PM compared with an expected pickup at 5:25 PM should be represented as approximately **9 minutes late**, subject to any documented catering grace period.
- Expected-completion duration should be derived from valid timestamps for the same order lifecycle and should not show 1,901 minutes without a corresponding 31-hour-41-minute interval.
- The total time difference should be calculated from valid per-step differences.
- If claiming an offer and beginning active delivery work are different events, the UI and data model should label them distinctly—for example, **Offer claimed** and **Active delivery started**.
- California Active Time should be calculated from the documented active-work event and the correct scheduled-order timestamps.

## Timestamp analysis

The pickup values reveal a precise one-day-offset pattern:

```text
Expected visible comparison:
5:34 PM actual - 5:25 PM expected = 9 minutes late

Displayed comparison:
1,431 minutes early = 23 hours 51 minutes early

One day minus the expected nine-minute lateness:
1,440 - 9 = 1,431 minutes
```

The displayed result would be produced if the system compared an actual pickup on August 17 at 5:34 PM with an incorrectly dated expected pickup on August 18 at 5:25 PM. This is a debugging hypothesis, not a confirmed root cause.

The total `-1,435 min` is internally consistent with the application's two displayed step differences:

```text
-1,431 min pickup + -4 min delivery = -1,435 min total
```

This suggests that aggregation may be functioning as implemented while an upstream expected-pickup timestamp or pickup-difference calculation is incorrect.

## Active Time observation

The visible interval from **Offer accepted at 10:07 AM** to **delivery at 5:55 PM** is 7 hours 48 minutes, while the application reports 38 minutes of California Active Time.

This is a user-visible semantic inconsistency requiring investigation, but the current evidence does not prove an earnings defect. For Claim Ahead orders, the 10:07 AM event may represent an advance reservation rather than the start of active delivery work. Engineering should verify which internal event is rendered as `Offer accepted` and which event starts the 38-minute interval.

## Reproducibility

Not recorded. One affected completed order is documented.

## Severity

**High.** The application creates materially incorrect performance history for a completed order and may be using a scheduled timestamp assigned to the wrong calendar day. If the same data enters California Active Time or earnings calculations, the defect could affect compensation records. That downstream impact is a risk requiring verification, not an observed fact.

## Priority

**High for investigation.** Engineering should promptly determine whether the corrupted timestamp is consumed only by On Time analytics or also by eligibility, performance, or California earnings pipelines. Priority may be reduced if the defect is conclusively isolated to a non-consequential display.

## Category

Functional / Data integrity / Date and time handling

## User and business impact

- A pickup approximately 9 minutes after the expected time is recorded as almost 24 hours early.
- Order-performance history becomes unreliable and internally contradictory.
- Incorrect timing data may affect driver trust, support investigations, and operational analytics.
- Potential impact on California Active Time, earnings adjustments, or related calculations requires backend verification.

## Evidence

- Third-party screenshot — earnings details: reviewed, not included in the repository.
- Third-party screenshot — completed order On Time details: reviewed, not included in the repository.
- Third-party driver-chat context: reviewed as secondary evidence, not included in the repository.
- Application logs and API payloads: not available.

## Suggested engineering investigation

Retrieve the affected delivery's raw event timeline and compare:

- `offer_created_at`, `offer_claimed_at`, and `offer_accepted_at`;
- `scheduled_pickup_at` and `actual_pickup_at`;
- `scheduled_dropoff_at` and `actual_dropoff_at`;
- `active_time_start` and `active_time_end`;
- order, scheduling, and fulfillment calendar dates;
- market timezone and UTC-to-local conversion;
- Claim Ahead state transitions;
- API timestamps against the locally rendered timestamps.

Specifically check whether `scheduled_pickup_at` resolves to August 18 at 5:25 PM while the order was fulfilled on August 17. That mismatch would reproduce the observed 1,431-minute result exactly.

## Acceptance criteria

1. For expected pickup at 5:25 PM and actual pickup at 5:34 PM on the same date, the calculated result is approximately 9 minutes late, subject to documented tolerance.
2. Expected-completion duration matches the order's valid scheduled lifecycle.
3. Step differences and total difference use timestamps from the same order date and timezone.
4. Claim time and active-delivery start time are stored and labeled unambiguously.
5. California Active Time uses the intended state transition and is unaffected by the date-offset defect.
6. Regression coverage includes scheduled catering orders claimed in advance, timezone conversion, and adjacent-day boundaries.

## Follow-up

- Reproduce with a test account and record the application build, OS, device, timezone, and network.
- Capture redacted screenshots and relevant API/log timestamps with permission to publish.
- Test same-day and next-day Claim Ahead offers around midnight and daylight-saving transitions.
- Verify whether On Time analytics and California earnings calculations share the same scheduled timestamp source.
