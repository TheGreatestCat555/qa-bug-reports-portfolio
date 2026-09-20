# CHATGPT-IOS-006: Russian numeric values written as digits are frequently unintelligible in Read Aloud

> **Status:** Draft

## Summary

When Read Aloud plays an assistant response in Russian, numeric values written with digits are frequently pronounced incorrectly, awkwardly, or too unclearly to identify. Equivalent numeric content written out as Russian words is generally pronounced normally.

The contrast between digit and word forms suggests that the issue occurs while numeric text is being prepared for speech rather than being a general loss of Russian-language audio quality. The responsible component has not been confirmed.

## Product and platform

- Product: ChatGPT for iOS
- Component: Assistant response / Read Aloud / Russian numeric speech
- Platform: iOS

## Environment

| Field | Value |
|---|---|
| Device | iPhone 14 Pro Max |
| OS version | iOS 26.6, based on the contemporaneous device record |
| ChatGPT version | 1.2026.188 |
| Build | 29133674010 |
| Language | Russian |
| Selected voice | Not recorded |
| Network | Not recorded |
| Date documented in the source | August 23, 2026 |

The app and OS versions come from the owner's recorded environment for the same device and period; they were not repeated numerically in the individual observation.

## Preconditions

- An assistant response contains one or more numeric values written with digits.
- Read Aloud is available for the response.
- The response is read in Russian.

## Steps to reproduce

This sequence reconstructs the recurring field observation. A controlled comparison has not yet been recorded.

1. Open an assistant response containing a numeric value written with digits.
2. Start Read Aloud.
3. Listen to the spoken numeric value.
4. Compare the spoken result with the value displayed in the response.
5. Repeat with equivalent numeric content written out as Russian words.

## Actual result

- Digit-form numeric values are frequently pronounced incorrectly or unclearly.
- In some occurrences, the spoken value cannot be identified from the audio.
- Numeric content written as Russian words is generally understandable.

The source did not preserve a specific input and audio output pair, so no example pronunciation is reconstructed in this report.

## Expected result

Read Aloud should pronounce Russian numeric values intelligibly and preserve their meaning whether the values are written with digits or spelled out as words.

## Reproducibility

Recurring and frequent in ordinary use. The exact rate and controlled sample size are unknown.

The owner informally described the issue as affecting the large majority of encountered digit-form numbers. That estimate is not presented as measured evidence.

## Severity

**Medium candidate.** Numeric values can be essential to an answer, and unintelligible speech reduces the usefulness and accessibility of Read Aloud. The available observation does not establish that every number format, Russian voice, or response is affected.

## Priority

**To be assessed.** The affected formats, voices, versions, and population are not known.

## Category

Functional / Accessibility / Text to Speech / Localization / Numeric Normalization

## Evidence

- The report is based on a recurring firsthand observation.
- No privacy-safe audio or screen recording is available for public inclusion.
- The original conversation contains no exact digit/word test pair from which a spoken result can be independently verified.

## Investigation notes

Potential investigation areas include Russian number expansion before speech synthesis and the handling of punctuation, separators, percentages, units, dates, times, currencies, and ranges. These are hypotheses, not established causes.

A controlled follow-up should test identical values in digit and word forms while recording:

- exact response text;
- selected voice;
- app and iOS builds;
- number category;
- punctuation and surrounding characters;
- a privacy-safe audio recording.

