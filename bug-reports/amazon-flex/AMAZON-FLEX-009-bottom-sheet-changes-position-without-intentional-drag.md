# AMAZON-FLEX-009: Delivery-map bottom sheet changes position without an intentional drag

> **Status:** Draft — intermittent UX candidate

## Summary

The lower information panel on an Amazon Flex delivery-map screen can change between collapsed and expanded positions without a clearly intentional drag gesture, causing the map layout and visible delivery information to shift unexpectedly.

## Product and platform

- Product: Amazon Flex driver application
- Platform: iOS

## Environment

| Field | Value |
|---|---|
| Device | iPhone 14 Pro Max |
| iOS version | 26.3.1, reported for the source session |
| Application version/build | Not recorded |
| Workflow | Active delivery; map and stop information visible |
| Network | Not established as relevant |
| Route, address, stop, package, and account data | Excluded |

## Preconditions

- An active delivery stop is open on the Amazon Flex map.
- The lower information panel is visible.

## Observed sequence

1. Open an active delivery stop in Amazon Flex.
2. Interact normally with the map or delivery screen without intentionally dragging the lower panel.
3. Observe the position of the lower information panel.

## Actual result

The bottom sheet can move between panel positions or appear to react as draggable without a clearly intended panel gesture. The movement changes the amount of visible map and delivery information without explanatory feedback.

## Expected result

The panel should remain in its current state until the user performs a deliberate supported gesture or another clearly communicated application state requires a layout transition.

## Reproducibility

Intermittent. The exact input or state transition that triggers the movement was not isolated, and the issue has not been reproduced on demand.

## Severity

**Low–Medium candidate.** The behavior disrupts interface predictability and may obscure map or delivery information, but no blocked delivery or data loss was established.

## Priority

**To be assessed.** A video or controlled gesture comparison is needed to distinguish unintended movement from an accepted sheet gesture or automatic state transition.

## Category

UX / Gesture Handling / Bottom Sheet / State Management

## Evidence

- Private screenshots document different panel positions, but static images do not prove that the transition occurred without a gesture.
- The screenshots are excluded because delivery and location information may be visible.
- Video and logs: Not available.

## Notes and limitations

- The report does not claim a race condition, React Native state bug, or gesture-handler defect; those were unverified hypotheses in the source discussion.
- Normal automatic transitions tied to arrival, navigation, or delivery-state changes have not been ruled out.
- Incidental taps, scrolling, orientation changes, and edge gestures were not isolated.
- This is retained as a Draft UX candidate until the trigger can be distinguished from expected bottom-sheet behavior.

