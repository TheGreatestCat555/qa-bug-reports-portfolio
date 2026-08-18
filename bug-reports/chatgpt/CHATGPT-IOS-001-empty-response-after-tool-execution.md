# [CHATGPT-IOS-001] Completed tool-enabled turn renders as an empty response

> **Status:** Ready

## Summary

After ChatGPT completes a long-running task with a connected tool, the iOS application may display only the processing-duration indicator while the final assistant response is missing. The task appears to finish, but I cannot see the result, summary, preview, link, or error message.

## Product and platform

- Product: ChatGPT
- Platform: iOS application
- Feature: Tool-enabled assistant turns
- Connected tool used when observed: Canva

## Environment

| Field | Value |
|---|---|
| Device | iPhone 14 Pro Max |
| Hardware identifier | iPhone15,3 |
| OS | iOS 26.6 |
| ChatGPT version | 1.2026.188 |
| Build | 29133674010 |
| Account | ChatGPT Plus |
| Interface language | Russian |

## Preconditions

1. Open a long existing conversation in the ChatGPT iOS application.
2. Connect a third-party tool such as Canva.
3. Open or reference an existing item that ChatGPT can modify with the tool.

## Steps to reproduce

1. Ask ChatGPT to edit an existing Canva design.
2. Allow the assistant to run the required tool operations.
3. Wait for processing to complete.
4. Review the completed assistant turn.

## Actual result

The turn displays a processing-duration indicator such as `Processing took 43s` or `Processing took 1m 2s`, but no final assistant response appears below it. There is no result text, edit summary, Canva preview, design link, confirmation, or error message.

## Expected result

After tool execution completes, the application should display the final assistant response and any available result, preview, or link. If the response cannot be delivered or rendered, the application should show an explicit error and provide a recovery option.

## Reproducibility

Intermittent; reproduced at least twice in the same conversation after long-running Canva operations.

## Severity

**High.** A connected tool may complete or modify an external resource while the result remains inaccessible in the conversation. I cannot verify what changed and may repeat the request, causing duplicate operations.

## Category

Functional / Conversation rendering / Tool-enabled turns

## Evidence

Two screenshots captured the affected conversation states. They are not included in the public repository.

## Notes

The visible processing-duration indicator shows that the turn reached a completed state. Canva is one observed reproduction condition; the user-visible failure occurs in the ChatGPT iOS conversation after tool execution.
