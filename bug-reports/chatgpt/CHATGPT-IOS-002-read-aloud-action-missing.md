# [CHATGPT-IOS-002] Read Aloud action is missing for an assistant response

> **Status:** Draft — platform, environment, reproduction rate, and comparison behavior still need verification.

## Summary

The Read Aloud action was not available for a long assistant response, preventing the response from being played as audio from the conversation interface.

## Product and platform

- Product: ChatGPT
- Platform: iOS application (to be confirmed)
- Feature: Assistant message actions / Read Aloud

## Environment

| Field | Value |
|---|---|
| Device | Not recorded |
| OS version | Not recorded |
| ChatGPT version/build | Not recorded |
| Account state | Not recorded |
| Interface language | Not recorded |
| Network | Not recorded |
| Date and time | Not recorded |

## Preconditions

1. Open a ChatGPT conversation containing an assistant response.
2. Ensure that the response has finished generating.

## Steps to reproduce

1. Ask ChatGPT to generate a long text response.
2. Wait until generation is complete.
3. Inspect the actions available for the completed assistant message.
4. Attempt to locate the Read Aloud action.

## Actual result

The Read Aloud action is not displayed for the assistant response, so the response cannot be played from the conversation interface.

## Expected result

The completed assistant response should expose the Read Aloud action consistently with other supported assistant messages, allowing the user to play the response as audio. If the response is not eligible for playback, the interface should communicate that limitation.

## Reproducibility

Not recorded. The issue was observed once in an existing conversation.

## Severity

**Low.** The text remains readable, but the missing action removes an alternative way to consume a long response and may have a greater impact on users who rely on audio output.

## Priority

**Low, to be reassessed after reproduction.** The core conversation remains usable, but inconsistent message actions reduce usability and accessibility.

## Category

Accessibility / UI

## Evidence

- Shared conversation records the user's observation that the playback button was unavailable.
- Screenshot or video: Not available in the public repository.
- Logs: Not available.

## Notes and follow-up

- Confirm that the observation occurred in the ChatGPT iOS application rather than on the web.
- Record the device, OS version, ChatGPT version, account state, and interface language.
- Compare the affected response with shorter and similarly sized assistant responses in the same conversation.
- Check whether Read Aloud appears after reopening the conversation or restarting the application.
- Check whether the action is absent only while a response is still generating.
- Measure the reproduction rate and add redacted visual evidence before changing the report to Ready.
