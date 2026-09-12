# [CHATGPT-IOS-003] Voice recording is lost after speech processing fails

> **Status:** Draft — historical observation; application build and current behavior need verification.

## Summary

After a long voice recording is completed in the ChatGPT iOS conversation composer, speech processing may fail and the recording disappears without producing a message or recoverable draft. The user must recreate the entire recording.

## Product and platform

- Product: ChatGPT
- Platform: iOS application
- Feature: Voice input in the conversation composer

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

1. Open an existing conversation in the ChatGPT iOS application.
2. Allow ChatGPT to access the microphone.

## Steps to reproduce

1. Start voice input from the ChatGPT conversation composer.
2. Record a long spoken message.
3. Stop the recording and allow ChatGPT to process it.
4. Observe the conversation after speech processing fails.

## Actual result

ChatGPT reports that it could not understand or process the input. The recording, transcription, and message draft are not available in the conversation, leaving an empty gap between the surrounding messages. No recovery or retry option for the original recording is provided.

## Expected result

If speech processing fails, ChatGPT should preserve the recording or draft and offer a retry, review, or recovery option. A processing failure should not irreversibly discard a long user recording.

## Reproducibility

Frequently observed historically. An exact attempt count was not recorded, and the problem now appears to occur rarely or not at all.

## Severity

**Medium.** The failure does not block text conversations, but it can permanently discard substantial user input and require the user to reconstruct a long, spontaneous message.

## Priority

**To be assessed.** The issue had a high historical impact when it occurred frequently, but the current application may already contain a fix.

## Category

Functional / Error Handling / Data Loss

## Evidence

- A historical conversation records the failed input and confirms that no recording or transcription appeared between the surrounding messages.
- Screenshot or video: Not available in the public repository.
- Logs: Not available.

## Notes and follow-up

- The specific foreground or background application state was not recorded and is not treated as a required reproduction condition.
- A separate historical account describes the interface switching to a voice/call-style screen during or immediately after an attempt to send a long recording, followed by loss of the recording. It is unknown whether the mode switch occurred automatically, resulted from an unintended touch, or shared the same trigger as the processing-failure scenario.
- Do not assign the device's current iOS version to this historical observation.
- Retest on the current ChatGPT build with recordings of several durations.
- Verify behavior after transcription errors, network interruption, backgrounding, returning to the conversation, and switching between composer voice input and realtime voice mode.
- Check whether a failed recording survives conversation reload or application restart.
