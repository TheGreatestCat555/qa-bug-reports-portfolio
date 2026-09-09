# [CHATGPT-IOS-004] Voice transcription returns text unrelated to the uploaded recording

> **Status:** Draft — historical observation; application build, exact source speech, and current behavior need verification.

## Summary

ChatGPT produced a confident transcription that was unrelated to the speech in an uploaded `.m4a` recording. The response presented invented text as the recording's contents instead of reporting that transcription was unavailable or uncertain.

## Product and platform

- Product: ChatGPT
- Platform: iOS application
- Feature: Audio file understanding / transcription
- File type observed: `.m4a`

## Environment

| Field | Value |
|---|---|
| Device | iPhone 14 Pro Max |
| iOS version at time of observation | Not recorded |
| ChatGPT version/build | Not recorded |
| Account state | Not recorded |
| Interface language | Not recorded |
| Network | Not recorded |
| Date and time | Not recorded |

## Preconditions

1. Have an `.m4a` file containing intelligible human speech.
2. Open a conversation in the ChatGPT iOS application.

## Steps to reproduce

1. Attach the `.m4a` recording to the conversation.
2. Ask ChatGPT to transcribe the recording.
3. Wait for the assistant response.
4. Compare the returned text with the original recording.

## Actual result

ChatGPT states that the recording says `Продолжение следует...`, although that phrase is not present in the recording. Similar historical failures reportedly produced nonexistent words, names, attribution-style phrases, or responses unrelated to the supplied speech.

## Expected result

ChatGPT should return a transcription that reflects the audible speech. If the audio cannot be transcribed reliably or audio processing is unavailable, it should state that limitation instead of presenting fabricated text as a verified transcription.

## Reproducibility

Frequently observed historically with voice and audio processing. An exact attempt count was not recorded, and the problem now appears to occur rarely or not at all.

## Severity

**Medium.** A fabricated transcription can misrepresent user-provided content and may be trusted, copied, or acted upon as though it accurately reflects the recording.

## Priority

**To be assessed.** The issue had meaningful historical impact, but the current application may already contain a fix.

## Category

Functional / Content / Error Handling

## Evidence

- A historical conversation contains the uploaded file interaction, the returned phrase, and the user's confirmation that the transcription was incorrect.
- Original audio and public comparison transcript: Not available in the repository.
- Logs: Not available.

## Notes and follow-up

- The source recording was described as approximately eight seconds long and did not contain the phrase returned by ChatGPT.
- The exact intended transcript was not preserved and must not be reconstructed from memory.
- Retest with privacy-safe recordings that have known reference transcripts.
- Include clear speech, quiet speech, background noise, names, and multiple languages in follow-up coverage.
- Verify whether the current interface communicates confidence or inability to process the attachment.
