# MOBILE-IOS-001: An unrelated Chinese character appears in an automatically generated Russian chat title

> **Status:** Draft

## Summary

ChatGPT for iOS generated the Russian conversation title `Шансы перев乏ки в Prius`. The Chinese character `乏` appears inside the word that should read `перевозки`, producing a visibly corrupted mixed-script title.

The conversation itself appeared unaffected. The issue was observed once in the automatically generated title shown in chat history.

## Product and platform

- Product: ChatGPT for iOS
- Component: Automatic conversation-title generation and chat-history display
- Platform: iOS

## Environment

| Field | Value |
|---|---|
| Device | Not recorded in the source for this occurrence |
| OS version | Not recorded in the source for this occurrence |
| Application version/build | Not recorded |
| Conversation language | Russian |
| Interface language | Not recorded |
| Date documented | Not recorded |

## Preconditions

- The user is signed in to ChatGPT for iOS.
- A conversation contains Russian-language discussion about transporting an item in a Toyota Prius.
- ChatGPT automatically assigns a title to the conversation.

## Steps to reproduce

These steps reconstruct the recorded workflow; the issue has not been reproduced under controlled conditions:

1. Open ChatGPT for iOS.
2. Start a conversation in Russian.
3. Discuss whether an item can be transported in a Toyota Prius.
4. Allow the application to generate the conversation title automatically.
5. Open the chat-history sidebar.
6. Inspect the generated title.

## Actual result

The title appears as:

```text
Шансы перев乏ки в Prius
```

The character `乏` (Unicode `U+4E4F`, CJK Unified Ideograph) appears inside an otherwise Russian word. It replaces the expected Cyrillic sequence and makes the title incorrect.

## Expected result

The automatically generated title should preserve the intended Russian text without inserting an unrelated writing system. A correct title for the recorded context would be:

```text
Шансы перевозки в Prius
```

## Reproducibility

Observed once. No controlled attempt count or stable trigger was recorded.

## Severity

**Low candidate.** The defect is visible and reduces title quality, but the conversation content and core chat workflow remained usable. No search, synchronization, or data-loss impact was observed.

## Priority

**To be assessed.** Frequency, affected languages, version range, and whether the stored title or only its display was affected are unknown.

## Category

Localization / Generated Content / Unicode / Mixed Script

## Workaround

No workaround was documented in the source. Manually renaming the conversation may be a possible recovery path, but it was not verified as part of the observation.

## Evidence

- Firsthand report with the exact generated and expected title: available.
- Screenshot of the corrupted title: reported as available.
- The original screenshot is not included in the public repository because adjacent chat titles or account information may require redaction.
- Raw title data, application logs, network responses, and a copy/paste Unicode capture from the original UI are not available.

## Notes and limitations

- The visible character is identified as `乏` from the recorded title text. A future reproduction should copy the title directly from the app to confirm the stored code point.
- The source does not establish whether the corruption originated during title generation, storage, synchronization, or rendering.
- Effects on search, sorting, copying, accessibility, and cross-device synchronization were not tested.
- The report does not claim that unexpected script mixing should always be rejected; multilingual titles can be valid when supported by the conversation. The defect here is that the inserted character breaks the intended Russian word.
