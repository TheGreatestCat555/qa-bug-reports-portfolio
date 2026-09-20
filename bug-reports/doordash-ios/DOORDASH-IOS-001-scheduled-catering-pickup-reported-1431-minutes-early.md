# DOORDASH-IOS-001: Scheduled catering pickup is reported as 1431 minutes early despite occurring nine minutes after the displayed target

> **Status:** Draft

## Summary

A completed scheduled catering delivery displays an expected pickup time of 5:25 PM and an actual pickup time of 5:34 PM, but classifies the pickup as `Early by 1431 min`. The same order also displays an expected completion time of `1901 min` and a total time difference of `-1435 min`.

The generated pickup difference contradicts the timestamps shown by the same application. Because 1431 minutes is 24 hours minus nine minutes, the result is consistent with a possible one-day date offset in the timestamp comparison. The stored timestamps are not available, so that explanation remains a hypothesis rather than a confirmed cause.

## Product and platform

- Product: DoorDash Dasher
- Component: Scheduled catering / Claim Ahead order history and on-time details
- Platform: Mobile; exact operating system not recorded

## Environment

| Field | Value |
|---|---|
| Device | Not recorded |
| OS version | Not recorded |
| Dasher app version/build | Not recorded |
| Network | Not recorded |
| Market | California, United States |
| Environment | Production / completed scheduled catering delivery |
| Date shown in the source | August 17, 2026 |
| Account, merchant, and location | Withheld for privacy |

## Preconditions

- The account has access to a scheduled catering or Claim Ahead-type order.
- The order is claimed before its pickup window.
- The pickup and delivery are completed.
- On-time details are available for the completed order.

The exact required preconditions are not known because only one affected order is documented.

## Steps to reproduce

The following sequence reflects the field observation and is not yet a deterministic reproduction:

1. Claim a scheduled catering order several hours before its pickup window.
2. Complete pickup near the displayed scheduled pickup time.
3. Complete the delivery.
4. Open the completed order's on-time details.
5. Compare the scheduled pickup and actual pickup timestamps with the calculated pickup difference.
6. Compare the expected and actual delivery timestamps with the calculated delivery difference.
7. Review the expected completion time and total time difference.

## Actual result

The completed-order details show:

| Event or metric | Displayed value |
|---|---:|
| Offer accepted | 10:07 AM |
| Scheduled pickup | 5:25 PM |
| Actual pickup | 5:34 PM |
| Pickup difference | `Early by 1431 min` |
| Expected delivery | 5:59 PM |
| Actual delivery | 5:55 PM |
| Delivery difference | `Early by 4 min` |
| Expected completion time | `1901 min` |
| Total time difference | `-1435 min` |

The pickup occurred nine minutes after the displayed target, but the application reports it as 1431 minutes early.

The total is arithmetically consistent with the two generated component values:

```text
-1431 + -4 = -1435
```

This indicates that the total may be aggregating the supplied differences correctly even though the pickup difference itself is invalid.

## Expected result

- The pickup difference should be calculated from the correct scheduled and actual pickup timestamps for the same order and calendar date.
- A 5:34 PM pickup compared with a displayed 5:25 PM target should not be represented as almost 24 hours early.
- Expected completion metrics should remain consistent with the order's displayed pickup and delivery timeline.
- If claiming a scheduled order and beginning active delivery work are separate events, the UI should label them distinctly.

## Reproducibility

Observed once. Controlled reproduction has not been completed.

The exact numerical relationship makes the incident appear calculation-related rather than a simple visual formatting issue, but the affected population and current reproducibility are unknown.

## Severity

**High candidate.** The completed-order record presents an impossible pickup delta and an implausible expected-completion value. This may undermine the reliability of delivery-performance history and any downstream feature that consumes the same calculated values.

No compensation error, rating change, enforcement action, or statutory violation was established by the available evidence.

## Priority

**To be assessed.** Priority depends on whether the invalid timestamp is limited to historical presentation or is also consumed by performance, eligibility, or earnings systems.

## Category

Functional / Data Integrity / Scheduled Orders / Time Calculation / Order History

## Evidence

- The source includes a completed-order on-time detail screen containing the conflicting timestamps and calculated minute differences.
- A separate earnings view supplies contextual Active Time information, but does not establish that compensation was calculated incorrectly.
- The observation and screenshots originated from another Dasher and were shared in a private driver discussion.
- Public screenshots are omitted because the original material contains third-party, merchant, market, earnings, and potentially account-related information.
- Application logs, API responses, raw timestamps, and time-zone metadata are not available.

## Investigation notes

The reported pickup difference has a precise relationship to a one-day shift:

```text
1440 minutes in one day - 9 minutes = 1431 minutes
```

If the expected 5:25 PM pickup were internally associated with the following calendar day while the actual 5:34 PM pickup remained on the correct date, the calculated result would be 23 hours 51 minutes, or 1431 minutes, early. This is a useful debugging hypothesis, not proof of the backend value.

Engineering could compare the raw order date and time-zone values associated with:

- offer claim and acceptance;
- scheduled pickup;
- actual pickup;
- scheduled delivery;
- actual delivery;
- expected-completion generation;
- transition from a claimed scheduled order to active delivery work.

The source also shows `38 min` of California Active Time. That value should be investigated separately from the confirmed pickup-delta contradiction. The evidence does not establish whether the morning claim event should count as engaged time, and it does not demonstrate an underpayment or legal violation.

