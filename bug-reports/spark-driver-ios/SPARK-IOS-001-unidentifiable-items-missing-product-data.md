# SPARK-IOS-001: Unidentifiable items with missing product data appear during an active shopping order

> **Status:** Draft

## Summary

During an active Shop & Deliver order, at least two shopping-list entries appeared without enough product information to identify or purchase them. The entries retained a quantity and a UPC, but the visible name, usable image, package details, location, and valid price were missing.

## Product and platform

- Product: Spark Driver
- Component: Shop & Deliver shopping list and item details
- Platform: iOS

## Environment

| Field | Value |
|---|---|
| Device | iPhone 14 Pro Max |
| OS version | iOS 26.6, as shown in the source evidence |
| Spark Driver version/build | Not recorded |
| Network | Not recorded |
| Environment | Production / active Shop & Deliver order |
| Store, account, and region | Withheld for privacy |
| Date and time | Not recorded |

## Preconditions

- A Shop & Deliver order is active.
- The shopping list contains at least one product that is unavailable in the store.
- Spark presents one or more suggested substitutions.

The exact required preconditions are not known because the issue has been observed only once.

## Steps to reproduce

The following sequence documents the field observation and is not yet a deterministic reproduction:

1. Open an active Shop & Deliver order.
2. Locate a requested bakery product that is unavailable.
3. Mark the product unavailable and review the substitution proposed by Spark.
4. When a proposed substitution is also unavailable or does not match, continue through the normal unavailable-item or substitution flow.
5. Repeat the process as Spark presents additional suggested products.
6. Scan and add a later suggested replacement that is available.
7. Return to the active shopping list.
8. Open an entry that has no visible product identity.

## Actual result

At least two entries cannot be identified from the information presented to the driver.

The captured shopping-list and item-detail states include:

- no product name;
- no usable product image, only a generic placeholder;
- no product description or package-size information;
- no aisle or section information;
- `Item location unavailable` in the detail view;
- `$0/lb` in the list and `$0.00` in the detail view;
- quantity retained as `1`;
- a UPC retained despite the missing human-readable product identity;
- an `Added` state on at least one affected list entry;
- an `Item not found` message on one affected detail view.

The two captured entries display different UPC values, so they are not simply two captures of the same item.

Because the expected products cannot be determined, the affected entries have to be treated as unavailable rather than shopped normally.

## Expected result

Every actionable shopping-list entry should display enough consistent information for the driver to identify and verify the requested product. This should include a meaningful product name and quantity, together with available image, package, price, and store-location data.

If Spark cannot resolve a product record, it should present a clear non-actionable error or recovery state rather than require the driver to shop an unnamed item with a zero price.

## Reproducibility

Observed once. A controlled reproduction has not been completed.

The owner did not inspect the full list before the substitution sequence, so it is not known whether the unidentified entries already existed. The preceding substitutions are context, not a confirmed trigger.

## Severity

**High candidate.** The missing information prevents the affected products from being identified and fulfilled correctly. It may also add shopping time or cause an intended product to be removed from the order for reasons outside the driver's control.

No actual customer charge, driver-metric change, or backend-data corruption was verified.

## Priority

**To be assessed.** The affected population, occurrence rate, responsible component, and current reproducibility are unknown.

## Category

Functional / Shopping Workflow / Product Data Presentation / Error Handling

## Evidence

- Screenshots of the shopping list, substitution context, and two affected detail views were supplied in the original field discussion.
- The screenshots are not included publicly because the surrounding production-order interface may contain customer, store, route, order, account, or location information.
- The distinct UPC values are retained in the private source record but are not required to demonstrate the public issue.
- An unrelated delivery screenshot from the same source was excluded.
- Application logs and network traces are not available.

## Notes and follow-up

- Repeated substitution attempts, a customer-side order update, an unresolved catalog record, stale local data, or a partial server response are possible investigation areas, not established causes.
- A future occurrence should capture the initial list before any substitution, the exact Spark build, network state, whether refresh or restart changes the entries, and a privacy-safe screen recording.
- Reproduction should not be forced by making false unavailable selections or otherwise disrupting a live customer order.
- Verification should confirm that every actionable item maps to a valid product identity and that unresolved records produce a recoverable error instead of a blank item.
