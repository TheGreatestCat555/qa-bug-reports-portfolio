# [CHATGPT-WEB-001] Copied response contains unexpected hidden characters after hyphens and periods

> **Status:** Draft — observed once; the exact characters and browser version were not recorded.

## Summary

A long response copied from ChatGPT contained unexpected characters or formatting that was not visible in the conversation. After I pasted the response into a text field on another website, the issue appeared after hyphens inside compound words and after the periods in many sentences.

## Product and platform

- Product: ChatGPT
- Source: ChatGPT conversation
- Destination: Multiline text field in a website form
- Platform and browser: Not recorded

## Preconditions

1. A ChatGPT conversation contains a long generated response with compound words written with hyphens and multiple sentences.
2. Another website provides a multiline text field for submitting a problem description.

## Steps to reproduce

1. Generate a long response in ChatGPT.
2. Copy the response from the conversation.
3. Paste it into a multiline text field on another website.
4. Review the pasted text around hyphens and sentence-ending periods.

## Actual result

The pasted text contains unexpected characters or formatting that was not visible in ChatGPT. The issue appears after hyphens inside compound words and after the periods in many, but not all, sentences. I had to remove the affected content manually before submitting the form.

## Expected result

Plain text copied from ChatGPT should paste into a website form without adding hidden or unexpected characters. The pasted text should match the visible response.

## Reproducibility

Observed in one long response. The exact reproduction rate was not recorded.

## Severity

**Medium.** The text can still be submitted after manual cleanup, but a long response may require many corrections and the copied content cannot be trusted to match what is visible in ChatGPT.

## Category

Content / Copy and paste / Text encoding

## Evidence

Not available. The exact characters were removed manually before they were recorded.

## Follow-up

- Reproduce the issue and inspect the pasted text at the Unicode code-point level.
- Compare copying from ChatGPT Web and the native applications.
- Test plain-text and rich-text destination fields in multiple browsers.
- Determine whether the extra content originates in the copied HTML, clipboard plain text, or the destination form's parser.
