# GMAIL-IOS-001: The cursor usually cannot be placed after a line-initial `I` or `i`

> **Status:** Draft

## Summary

While composing or editing an email in Gmail for iOS, the insertion cursor usually cannot be positioned immediately after `I` or `i` when the letter is the first character on a line. Tapping, pressing and holding, or dragging near that boundary generally places the cursor before the letter instead.

The user must delete the first character, make the intended edit, and type the character again. Cursor placement has succeeded occasionally, so the failure is intermittent rather than absolute.

## Product and platform

- Product: Gmail for iOS
- Component: Message editor and cursor placement
- Platform: iOS

## Environment

| Field | Value |
|---|---|
| Device | iPhone 14 Pro Max |
| OS version | iOS 26.5, as reported in the field account |
| Gmail version/build | Not recorded |
| Keyboard language/layout | Not recorded |
| Text size and Display Zoom | Not recorded |
| Date documented | June 20, 2026 |

## Preconditions

- Gmail is open on the iPhone.
- A new message or editable draft is open.
- A line begins with uppercase `I` or lowercase `i`, with no leading whitespace.

## Steps to reproduce

1. Open Gmail for iOS.
2. Start a new message or open an editable draft.
3. Begin a line with `I` or `i`, without inserting a space before it.
4. Type additional text on the line.
5. Tap immediately after the first character.
6. Repeat using a long press and cursor dragging.
7. Observe the insertion-cursor position.

## Actual result

- The cursor usually appears before the line-initial `I` or `i` rather than after it.
- Tapping, long-pressing, and dragging do not reliably reach the intended position.
- Editing at that boundary often requires deleting and retyping the first character.
- The cursor can occasionally be placed correctly, so the result is not identical on every attempt.

## Expected result

The cursor should be placeable immediately before or after the first character through the standard iOS text-editing gestures, as it is at other character boundaries.

## Reproducibility

The failure was reported as occurring on nearly every attempt, with occasional successful placement. No controlled attempt count was recorded, so a percentage is not assigned.

## Severity

**Medium candidate.** A basic text-editing interaction repeatedly fails and requires destructive re-entry of text. Message composition remains possible through a workaround, and no message loss or unintended send was observed.

## Priority

**To be assessed.** The frequency appears high for the reported character position, but the affected Gmail version range, device range, keyboard configurations, account types, and broader user impact are unknown.

## Category

Functional / Text Editing / Cursor Placement / Input Handling

## Workaround

Delete the initial `I` or `i`, make the required edit or insert a space, and type the character again.

## Evidence

- Firsthand field account: available.
- A screenshot was supplied, but it captured one of the occasional successful placements rather than the failing state.
- The original screenshot is excluded because an email compose screen may expose message content, recipients, account information, or timestamps.
- A privacy-safe screen recording, editor diagnostics, Gmail logs, and exact gesture coordinates are not available.

## Notes and limitations

- Both uppercase `I` and lowercase `i` were reported, but they were not documented in separate controlled runs.
- The issue was observed in Gmail. It has not been established whether the same boundary behaves incorrectly in Apple Mail, Notes, other editors, or system-wide iOS text controls.
- Gmail editor behavior, iOS text selection, font hit-testing, keyboard state, and accessibility/display settings are possible investigation areas, not confirmed causes.
- A focused verification should compare `I`, `i`, `l`, `1`, punctuation, leading whitespace, and the same characters away from the beginning of a line.
