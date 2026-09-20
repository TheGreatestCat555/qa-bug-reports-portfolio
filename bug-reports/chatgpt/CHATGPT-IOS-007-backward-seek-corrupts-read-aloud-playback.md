# CHATGPT-IOS-007: 15-second backward seek corrupts Read Aloud playback while forward seek works normally

> **Status:** Draft

## Summary

During Read Aloud playback, selecting the 15-second backward control repeatedly disrupts the audio. Playback may stutter, emit short fragments of words or phrases, hang, stop completely, or recover only after a delay.

The 15-second forward control works promptly and resumes coherent audio in the same workflow. This comparison isolates the observed failure to backward seeking rather than seeking in both directions.

## Product and platform

- Product: ChatGPT for iOS
- Component: Assistant response / Read Aloud / playback controls
- Platform: iOS

## Environment

| Field | Value |
|---|---|
| Device | iPhone 14 Pro Max |
| OS version | iOS 26.6, based on the contemporaneous device record |
| ChatGPT version | 1.2026.188 |
| Build | 29133674010 |
| Response language in the source workflow | Russian |
| Selected voice | Not recorded |
| Network | Not recorded |
| Date documented in the source | August 23, 2026 |

The app and OS versions come from the owner's recorded environment for the same device and period; they were not repeated numerically in the individual observation.

## Preconditions

- An assistant response is eligible for Read Aloud.
- Read Aloud playback is active.
- The 15-second forward and backward controls are available.

## Steps to reproduce

The following sequence documents the repeated field observation. A controlled test run has not yet been captured.

1. Open an assistant response in ChatGPT for iOS.
2. Start Read Aloud.
3. While the response is playing, select the 15-second backward control.
4. Observe playback immediately after the seek.
5. Restart or recover playback if necessary.
6. Select the 15-second forward control from an active playback state.
7. Compare the backward and forward transitions.

## Actual result

After a 15-second backward seek, one or more of the following occurs:

- playback stutters or hangs;
- short fragments of words or phrases play repeatedly or out of sequence;
- unclear audio fragments are produced;
- playback stops and does not continue;
- less commonly, playback resumes normally only after a delay.

By comparison, the 15-second forward control advances promptly and continues normal playback without the same corruption.

## Expected result

Both seek controls should move playback by approximately 15 seconds and resume coherent audio promptly. Seeking backward should not fragment, freeze, or terminate the playback stream.

## Reproducibility

Consistently reproduced by the owner in repeated ordinary use. The exact number of trials is unknown.

The owner's statement that it happened every time describes their repeated experience; it is not evidence of a documented 100-trial test run.

## Severity

**High candidate.** A primary playback control can leave Read Aloud severely degraded or unusable and may require the user to restart playback. The final severity may be lower if the issue is limited to a particular voice, language, response type, or historical build.

## Priority

**To be assessed.** The affected versions, occurrence scope, and current reproducibility are not known.

## Category

Functional / Audio Playback / Seek Control / State Management / Accessibility

## Evidence

- The report is based on a repeatedly observed firsthand comparison.
- Forward seek provides a working control case in the same feature.
- No privacy-safe screen/audio recording, player log, or network trace is available for public inclusion.

## Investigation notes

The asymmetry between forward and backward seeking is a strong isolation signal, but it does not prove a particular implementation fault. Potential investigation areas include backward position calculation, reconstruction across audio segment boundaries, synchronization between generated speech segments and player time, and recovery after requesting an earlier position.

A controlled follow-up should record:

- exact response text and approximate audio duration;
- selected voice and response language;
- app and iOS builds;
- repeated forward and backward trials from comparable positions;
- whether pausing before seeking changes the outcome;
- whether restarting Read Aloud or the application restores playback;
- a privacy-safe screen recording with audio.

