# CHATGPT-IOS-008: Read Aloud distorts words, hangs, and stops during ordinary playback

> **Status:** Draft

## Summary

Read Aloud intermittently repeated or omitted fragments of words in a predominantly Russian response, making the speech difficult to understand. Restarting playback reproduced the distortion in the reported episode. Playback also hung and stopped by itself approximately a minute after a later restart.

## Product and platform

- Product: ChatGPT for iOS
- Component: Read Aloud playback of an assistant response
- Platform: iOS

## Environment

| Field | Value |
|---|---|
| Device | iPhone 14 Pro Max |
| OS version | Not independently verified; the contemporaneous report lists iOS 26.6.2 |
| Installed ChatGPT version/build | Not verified for this episode; an earlier session record was reused in the contemporaneous report |
| Response language | Predominantly Russian, with some English words and numbers |
| Selected voice and audio output | Not recorded |
| Network | Described by the user as good; no measurements available |
| Date documented in the observation | October 2, 2026 |

## Preconditions

- An assistant response is available for Read Aloud.
- The user starts playback of a long response.

## Steps to reproduce

The trigger is unknown. This sequence records the observed usage and recovery attempt.

1. Open a long assistant response, predominantly in Russian.
2. Start Read Aloud.
3. Continue listening until the speech becomes distorted or hangs.
4. Close playback and start it again.
5. Observe whether the distortion returns and whether playback continues to the end.

No backward seek was reported in this episode. A title or filename referring to ordinary playback describes that distinction, not a controlled test proving that seek state was absent internally.

## Actual result

- Playback interrupted words and restarted them from the beginning or from a fragment.
- Some sounds or word fragments were omitted, producing garbled speech.
- The affected passage reportedly distorted nearly every word and lasted beyond a brief isolated glitch.
- Distortion recurred on at least two consecutive listening attempts.
- Playback also hung. After another restart, it distorted speech again and stopped by itself approximately a minute later.

A crash of the entire application was not reported.

## Expected result

Read Aloud should play the response coherently to completion. If audio cannot continue, it should show a clear loading or error state rather than garbled speech or an unexplained stop.

## Reproducibility

Intermittent and unpredictable. Similar behavior had occurred earlier, while most listening sessions worked normally. Multiple consecutive failures were reported in this episode; no controlled failure rate was measured.

## Severity

**Medium candidate.** The response becomes difficult or impossible to understand by listening, and restarting did not restore it in the reported episode. Reading the text remained an alternative.

## Priority

**To be assessed.** The affected response, audio output, installed build, and broader occurrence rate are unknown.

## Category

Functional / Audio Playback / Accessibility / Error Handling / Intermittent Failure

## Evidence and limitations

- Firsthand description of the speech distortion and consecutive playback attempts.
- The actual audio, exact response text, diagnostic logs, and message identifier are unavailable.
- Private response content and conversation links are not published.
- Good perceived signal does not exclude network or buffering effects.
- The comparison to damaged packets describes how it sounded; it does not prove packet loss.
- A separate same-day report describes unstable media loudness across applications. A common cause has not been established.

## Relationship to existing reports

- [CHATGPT-IOS-007](CHATGPT-IOS-007-backward-seek-corrupts-read-aloud-playback.md) records playback corruption after using the 15-second backward seek control. This episode did not identify seeking as the trigger. The reports may ultimately share a cause, but that is unverified.
- [CHATGPT-IOS-006](CHATGPT-IOS-006-russian-digits-unintelligible-in-read-aloud.md) concerns pronunciation of numeric text. The distortion here also affects ordinary word fragments and includes hanging and stopping.

## Follow-up verification

Repeat the same response with no seek input, record the installed build and audio route, and capture the audible failure and UI state. Compare another response, voice, network, and device. Correlate any interruption with competing audio events before assigning a root cause.
